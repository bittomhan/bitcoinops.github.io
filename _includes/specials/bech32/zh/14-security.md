有一类多重签名用户不仅通过使用 bech32 地址来[节省费用][bech32 fee savings]，还因提高了对一种称为*哈希碰撞*的潜在攻击的安全性而受益。这类用户包括许多交易所和其他企业用户。

为了提供一些背景信息，目前比特币上的所有常见单签名地址都是通过将公钥转换为 160 位的 RIPEMD160 哈希摘要而生成的。理论上，攻击者可以生成第二个他们控制的公钥，对其进行哈希并生成相同的地址。然而，如果我们假设哈希函数产生的输出是完全不可预测的，那么使用像 RIPEMD160 这样的 160 位哈希函数时，每次攻击者尝试生成哈希碰撞的成功概率为 1/2<sup>160</sup>。

<!-- $ bitcoin-cli getmininginfo | jq .networkhashps
     65134463000474080000

    log2(65134463000474080000 * 60 * 60 * 5)
    79.95576417220315 -->

作为比较，当前比特币矿工大约每 5 小时执行 2<sup>80</sup> 次哈希操作。虽然矿工执行的 SHA256d 哈希操作与此 RIPEMD160 碰撞攻击使用的哈希操作不同，因此他们的设备无法被重新利用来进行这种攻击，但我们可以用此作为一个参考，以了解当前真实世界系统可以执行的暴力破解操作数量（虽然代价昂贵）。按此速度，执行 2<sup>159</sup> 次操作以获得 50% 成功率的攻击将需要大约 2500 万倍于宇宙至今的估计年龄的时间。<!-- 2**79 * 5 / 24 / 365.25 / 14e9 / 1e9 -->

然而，当使用多重签名地址时，攻击者可能是参与生成地址的一方，因此可能有能力操纵最终选择的地址。例如，Bob 将他的公钥发送给 Mallory，期望 Mallory 也将她的公钥返回给他。然后他们各自将公钥放入一个多重签名脚本模板中，哈希成一个地址，并有人将资金存入该地址。

然而，Mallory 采用了脚本模板和 Bob 的公钥，在没有告知 Bob 的情况下插入了她的一个公钥，并将其哈希成一个地址。这样，Mallory 可以在她承诺使用该公钥之前查看 Bob 将接受的地址。然后，Mallory 可以将该地址与她的数据库中仅支付给她的脚本生成的地址进行比较。如果两个地址匹配（碰撞），她就将公钥返回给 Bob，等待资金存入该地址，然后使用她数据库中的脚本来窃取资金。如果没有匹配，Mallory 可以一次又一次地尝试不同的公钥，直到她成功（假设她有无限的时间和资源）。

虽然这似乎与之前描述的具有每次尝试 1/2<sup>160</sup> 成功概率的暴力攻击类似，但我们必须考虑 Mallory 数据库的大小。如果我们假设该数据库有 100 个地址，那么她每次尝试不同的公钥时的成功概率为 100/2<sup>160</sup>，因为只要它与 Mallory 数据库中的任何一个地址匹配就可以成功。

这种攻击类型称为[碰撞攻击][collision attack]。碰撞攻击有几种在 CPU/内存方面进行权衡的算法，但安全研究人员遵循的通用规则是，针对完美哈希函数的碰撞攻击将其安全性降低到其组合数的平方根，即将其位数减半。这意味着我们可以大致认为 RIPEMD160 的安全性降低到 80 位——这与我们之前提到的当前技术下比特币矿工每 5 小时执行的操作次数相同。再一次，比特币挖矿设备无法用于此攻击，并且攻击者设计和构建足够的定制设备以在五小时内找到碰撞可能需要花费数十亿美元——但这是一个理论上可能的攻击，应该引起那些在 P2SH 中存储大量价值的人的关注，尤其是在定制硬件变得更快和更便宜的时候。此外，RIPEMD160 函数中可能存在的弱点也可能导致有更简单和更便宜的碰撞攻击变体。

可以设计多重签名设置协议，使其没有这个问题，从而保持 160 位的碰撞抵抗性。然而，segwit 的开发者[认为][sipa collision resistance]，对于 segwit 的 P2SH 类似物——P2WSH——使用稍长的哈希函数更为合适，这样用户就不需要担心这些密码学细节。因此，segwit P2WSH 使用了比特币中其他地方使用的相同的 SHA256d 函数，该函数为单方情况下提供 256 位安全性，为多方情况下提供 128 位的最差安全性。为了继续我们的粗略比较，如果我们认为 80 位相当于五小时的比特币挖矿，那么 128 位相当于 1600 亿年的挖矿。<!-- 128-80=48, 2**48 * 5 / 24 / 365 / 1e9 -->

在我们总结这一部分之前，我们想确保几件事情是清楚的：

1. 我们认为目前没有人能够执行所描述的攻击（但我们不能排除这种风险）。

2. 该攻击只能在创建地址时使用（尽管实际盗窃可能会在很长时间后发生）。

3. 该攻击仅适用于多方多重签名地址。如果你是使用仅自己信任设备的 P2SH 多重签名单方用户，或者你使用的是 P2SH-P2WPKH（单签名地址），则你不会受到此攻击的威胁。

4. 该攻击适用于 P2SH 包装的 segwit P2WSH 地址以及常规 P2SH 地址。要消除风险，你必须使用原生 segwit（bech32）地址或安全的密钥交换协议。

总结来说，希望获得最高安全性的多方多重签名用户应该迁移到 bech32 P2WSH 地址，以利用其额外的碰撞抵抗性。随着用户进行这种迁移，各服务确保他们实现 bech32 发送支持以便能够向这些注重安全的用户发送支付将变得更加重要。

[bech32 fee savings]: /zh/bech32-sending-support/#使用原生-segwit-节省费用
[sipa collision resistance]: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2016-January/012205.html
[collision attack]: https://en.wikipedia.org/wiki/Collision_attack
