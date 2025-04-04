---
title: 'Bitcoin Optech Newsletter #132'
permalink: /en/newsletters/2021/01/20/
name: 2021-01-20-newsletter
slug: 2021-01-20-newsletter
type: newsletter
layout: newsletter
lang: en
---
This week's newsletter summarizes posts to the Bitcoin-Dev mailing list
about payjoin adoption and making hardware wallets compatible with more
advanced Bitcoin features.  Also included are our regular sections with
overviews of changes to services and client software, new releases and
release candidates, and changes to popular Bitcoin infrastructure
software.

## News

- **Payjoin adoption:** Chris Belcher [posted][belcher payjoin] to the
  Bitcoin-Dev mailing list a request for people to look for ways to
  increase [payjoin][topic payjoin] adoption along with a [wiki
  page][payjoin wiki] tracking the projects that provide either sending
  or receiving support for payjoin.  One [suggestion][raw payjoin] by
  Craig Raw was to extend the protocol to allow it to work even when the
  receiver doesn't operate a server.

- **Making hardware wallets compatible with more advanced Bitcoin features:**
  Kevin Loaec [started a discussion][loaec hww] on the Bitcoin-Dev
  mailing list about how hardware wallets could be changed to allow them
  to handle scripts more complicated than single-sig or multisig.  For
  example, allowing a hardware wallet to handle in-channel LN payments
  or payments made from a [vault][topic vaults].  His post does a good
  job of describing various problems that current hardware wallets can't
  handle, but he notes that necessary "changes may be very difficult".

## Changes to services and client software

*In this monthly feature, we highlight interesting updates to Bitcoin
wallets and services.*

- **Blockstream announces Jade hardware wallet:**
  Blockstream's [new Jade hardware wallet][blockstream jade blog] is open source,
  supports Bitcoin and Liquid networks, and is compatible with Blockstream Green
  for Android.

- **Coldcard adds payjoin signing:**
  Coldcard's [3.2.1 release][coldcard 3.2.1] adds [BIP78][] payjoin signing
  support and various multisig improvements.

- **Mempool v2.0.0 released:**
  Open source [block explorer][topic block explorers] mempool, which backs the
  [mempool.space][mempool.space website] website, has released [version
  2.0.0][mempool v2]. Mempool supports Bitcoin Core, Electrum, and Esplora
  backends and also exposes block, transaction, and address information via APIs.

- **BlueWallet adds multisig:**
  Version [6.0.0 of BlueWallet][bluewallet 6.0.0. tweet] adds the ability to
  create and manage air-gapped, native segwit multisig vaults.

- **Sparrow supports connecting to Bitcoin Core:**
  [Sparrow 0.9.10][sparrow 0.9.10], using [Bitcoin Wallet Tracker v0.2.1][bwt
  0.2.1]'s Java Native Interface bindings feature, now supports connecting
  directly to a backing Bitcoin Core node.

## Releases and release candidates

*New releases and release candidates for popular Bitcoin infrastructure
projects.  Please consider upgrading to new releases or helping to test
release candidates.*

- [Bitcoin Core 0.21.0][Bitcoin Core 0.21.0] is a the next major version
  of this full node implementation and its associated wallet and other
  software.  Major new features include support for new Tor onion
  services using [version 2 address announcement messages][topic addr v2], the optional
  ability to serve [compact block filters][topic compact block filters],
  and support for [signets][topic signet] (including the default signet
  which has [taproot][topic taproot] activated).  It also offers
  experimental support for wallets that natively use [output script
  descriptors][topic descriptors].  For a complete list of changes, see
  the [release notes][bcc 0.21.0 notes].

- [Rust Bitcoin 0.26.0][] is a new release of this library.  Major new
  features include support for signet, version 2 address announcement messages,
  and improvements to [PSBT][topic psbt] handling.  See the
  [release notes][rb notes] for details.

- [BTCPay Server 1.0.6.7][] is the second maintenance release to
  [1.0.6.5][btcpay server 1.0.6.5] from last week, which added "support
  [for] a subset of output descriptors in the wallet setup" (see the
  *notable changes* section below).  Other features and bug fixes were
  also included.

- [C-Lightning 0.9.3rc2][c-lightning 0.9.3] is a release candidate for a
  new minor version of this LN node.

- [LND 0.12.0-beta.rc5][LND 0.12.0-beta] is the latest release candidate
  for the next major version of this LN node.

## Notable code and documentation changes

*Notable changes this week in [Bitcoin Core][bitcoin core repo],
[C-Lightning][c-lightning repo], [Eclair][eclair repo], [LND][lnd repo],
[Rust-Lightning][rust-lightning repo], [libsecp256k1][libsecp256k1
repo], [Hardware Wallet Interface (HWI)][hwi repo],
[Rust Bitcoin][rust bitcoin repo], [BTCPay Server][btcpay server repo],
[Bitcoin Improvement Proposals (BIPs)][bips repo], and [Lightning
BOLTs][bolts repo].*

- [Bitcoin Core #19937][] adds a new standalone `bitcoin-util` executable and
  `miner` script for mining [signet][topic signet] blocks, making it easier to
  create and maintain new signet networks. Also included is extensive
  [documentation][signet miner tool docs] for the new tools.

- [LND #4917][] disables the use of [anchor outputs][topic anchor
  outputs] by default, a feature that was planned to be released in the
  upcoming 0.12.0-beta.  Advanced users can still opt-in to using
  anchors.  The commit messages notes that, "the plan is to enable
  anchors by default [in a later release]."

- [Rust-Lightning #742][] improves the signer API by providing per-transaction
  information necessary for the signer to perform additional checks and provide
  a signature. This PR is part of a larger effort to support external signers in
  Rust-Lightning tracked [here][Rust-Lightning #408].

- [BTCPay Server #2169][] adds functions that provide support for
  decoding [output script descriptors][topic descriptors] referring to
  wallets created following BIPs [44][BIP44] (P2PKH HD wallets),
  [45][BIP45] (P2SH multisig HD wallets), [49][BIP49] (P2SH-P2WPKH HD
  wallets), [84][BIP84] (native P2WPKH HD wallets), and a [proposed
  amendment to BIP44][bips #253] for other multisig derivations (which
  has undocumented extensions for the use of P2SH-P2WSH and native
  P2WSH).

{% include references.md %}
{% include linkers/issues.md issues="19937,4917,742,2169,253,408" %}
[bitcoin core 0.21.0]: https://bitcoincore.org/bin/bitcoin-core-0.21.0/
[bcc 0.21.0 notes]: https://bitcoincore.org/en/releases/0.21.0/
[lnd 0.12.0-beta]: https://github.com/lightningnetwork/lnd/releases/tag/v0.12.0-beta.rc5
[rust bitcoin 0.26.0]: https://github.com/rust-bitcoin/rust-bitcoin/releases/tag/0.26.0
[rb notes]: https://github.com/apoelstra/rust-bitcoin/blob/010068ba321268704bc9da9fe311b45b9c0937b6/CHANGELOG.md#0260---2020-12-21
[btcpay server 1.0.6.7]: https://github.com/btcpayserver/btcpayserver/releases/tag/v1.0.6.7
[btcpay server 1.0.6.5]: https://github.com/btcpayserver/btcpayserver/releases/tag/v1.0.6.5
[c-lightning 0.9.3]: https://github.com/ElementsProject/lightning/releases/tag/v0.9.3rc2
[belcher payjoin]: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-January/018356.html
[raw payjoin]: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-January/018358.html
[payjoin wiki]: https://en.bitcoin.it/wiki/PayJoin_adoption
[loaec hww]: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-January/018352.html
[blockstream jade blog]: https://blockstream.com/2021/01/03/en-secure-your-bitcoin-and-liquid-assets-with-blockstream-jade/
[coldcard 3.2.1]: https://blog.coinkite.com/version-3.2.1-released/
[mempool.space website]: https://mempool.space/
[mempool v2]: https://github.com/mempool/mempool/releases/tag/v2.0.0
[bluewallet 6.0.0. tweet]: https://twitter.com/bluewalletio/status/1338943580245790722
[sparrow 0.9.10]: https://github.com/sparrowwallet/sparrow/releases/tag/0.9.10
[bwt 0.2.1]: https://github.com/bwt-dev/bwt/releases/tag/v0.2.1
[signet miner tool docs]: https://github.com/bitcoin/bitcoin/blob/43f3ada27b835e6b198f9a669e4955d06f5c4d08/contrib/signet/README.md#miner
