---
title: Anchor outputs

## Optional.  An entry will be added to the topics index for each alias
title-aliases:
  - Simplified commitments

## Required.  At least one category to which this topic belongs.  See
## schema for options
topic-categories:
  - Lightning Network

## Required.  Use Markdown formatting.  Only one paragraph.  No links allowed.
## Should be less than 500 characters
excerpt: >
  **Anchor outputs** are special outputs in LN commitment transactions
  that are designed to allow the transaction to be fee bumped.  An
  earlier name for the proposal was **simplified commitments.**

## Optional.  Produces a Markdown link with either "[title][]" or
## "[title](link)"
primary_sources:
    - title: Anchor outputs
      link: https://github.com/lightningnetwork/lightning-rfc/pull/688

    - title: Zero HTLC fee anchor outputs
      link: https://github.com/lightningnetwork/lightning-rfc/pull/824

## Optional.  Each entry requires "title", "url", and "date".  May also use "feature:
## true" to bold entry
optech_mentions:
  - title: Simplified fee bumping for LN
    url: /en/newsletters/2018/11/27/#simplified-fee-bumping-for-ln

  - title: LN simplified commitments discussion
    url: /en/newsletters/2019/10/30/#ln-simplified-commitments

  - title: Continued discussion of LN anchor outputs
    url: /en/newsletters/2019/11/06/#continued-discussion-of-ln-anchor-outputs

  - title: "2019 year-in-review: anchor outputs"
    url: /en/newsletters/2019/12/28/#anchor-outputs

  - title: "LND #3829 updates code & documentation to simplify adding anchor outputs"
    url: /en/newsletters/2020/01/15/#lnd-3829

  - title: "LND #3821 adds draft anchor commitments support"
    url: /en/newsletters/2020/03/18/#lnd-3821

  - title: "Using anchor outputs to ensure HTLC sends can be fee bumped"
    url: /en/newsletters/2020/04/29/#settlement-transaction-anchor-outputs

  - title: "LND 0.10 presentation: anchor outputs"
    url: /en/newsletters/2020/05/06/#lnd-v0-10

  - title: "Anchor outputs may help mitigate LN fee ransom attack"
    url: /en/newsletters/2020/06/24/#ln-fee-ransom-attack

  - title: "Eclair #1484 adds basic support for anchor outputs"
    url: /en/newsletters/2020/07/29/#eclair-1484

  - title: Discussion of solutions for attacks against LN, including anchor outputs
    url: /en/newsletters/2020/08/05/#chicago-meetup-discussion

  - title: "Eclair #1491 adds support for anchor outputs"
    url: /en/newsletters/2020/08/05/#eclair-1491

  - title: "C-Lightning #3830 adds experimental support for anchor outputs"
    url: /en/newsletters/2020/08/19/#c-lightning-3830

  - title: "BOLTs #688 adds support for anchor outputs to the LN protocol"
    url: /en/newsletters/2020/08/26/#bolts-688

  - title: "LND #4558 updates LND to the latest anchor outputs specification"
    url: /en/newsletters/2020/09/16/#lnd-4558

  - title: "Vulnerability disclosed against experimenal anchor outputs proposal"
    url: /en/newsletters/2020/09/16/#stealing-onchain-fees-from-ln-htlcs

  - title: "LND #4606 & #4592 improve LND's effectiveness at fee bumping anchor outputs"
    url: /en/newsletters/2020/09/23/#lnd-4606

  - title: Why do anchor outputs need to enforce an nSequence of 1?
    url: /en/newsletters/2020/09/30/#why-do-anchor-outputs-need-to-enforce-an-nsequence-of-1

  - title: "Eclair #1501 adds support for unilateral closes of channels using anchors"
    url: /en/newsletters/2020/09/30/#eclair-1501

  - title: "LND #4576 starts adding support for anchor outputs to LND’s watchtower"
    url: /en/newsletters/2020/09/30/#lnd-4576

  - title: Eclair 0.4.2 adds experimental support for anchor outputs
    url: /en/newsletters/2020/10/14/#eclair-0-4-2

  - title: "LND #4782 adds watchtower client support for channels using anchor outputs"
    url: /en/newsletters/2020/12/09/#lnd-4782

  - title: "LND #4779 allows sweeping HTLCs from anchor outputs"
    url: /en/newsletters/2020/12/16/#lnd-4779

  - title: "BOLT5 updated to prevent a pinning attack against anchor outputs"
    url: /en/newsletters/2020/12/16/#bolts-803

  - title: "2020 year in review: anchor outputs"
    url: /en/newsletters/2020/12/23/#anchor-outputs

  - title: "LND 0.12.0-beta adds watchtower support for channels using anchor outputs"
    url: /en/newsletters/2021/01/27/#lnd-0-12-0-beta

  - title: "LND #4908 reserves a balance for fee bumping when using anchor outputs"
    url: /en/newsletters/2021/01/27/#lnd-4908

  - title: "Eclair 0.5.1 adds and updates features preparing for anchor outputs"
    url: /en/newsletters/2021/03/10/#eclair-0-5-1

  - title: Request for feedback on using anchor outputs by default in LND
    url: /en/newsletters/2021/04/21/#using-anchor-outputs-by-default-in-lnd

  - title: "LND #5274 limits the maximum funds reserved for fee bumping anchor outputs"
    url: /en/newsletters/2021/05/19/#lnd-5274

  - title: "LND 0.13.0-beta begins using anchor outputs by default for all new channels"
    url: /en/newsletters/2021/06/23/#lnd-0-13-0-beta

  - title: "BOLTs #824 adds a variation on the anchor outputs protocol that prevents a fee-stealing attack"
    url: /en/newsletters/2021/09/08/#bolts-824

  - title: "Eclair #1932 implements the zero HTLC fee anchor outputs protocol"
    url: /en/newsletters/2021/09/22/#eclair-1932

  - title: Complications for HD wallet recovery in zero HTLC fee anchor outputs protocol
    url: /en/newsletters/2021/09/29/#challenges-recovering-ln-close-transactions-using-only-a-seed

  - title: "Rust-Lightning #1176 adds initial support for anchor outputs-style fee bumping"
    url: /en/newsletters/2021/12/01/#rust-lightning-1176

  - title: "Eclair #2134 enables anchor outputs by default"
    url: /en/newsletters/2022/01/26/#eclair-2134

  - title: Proposed relay of v3 transactions attempts to improve on anchor outputs
    url: /en/newsletters/2022/10/05/#proposed-new-transaction-relay-policies-designed-for-ln-penalty

  - title: Proposal to use multiple pre-committed fees to avoid needing anchor outputs in many cases
    url: /en/newsletters/2022/11/02/#anchor-outputs-workaround

  - title: Implementation of ephemeral anchors built on v3 transactions
    url: /en/newsletters/2022/12/07/#ephemeral-anchors-implementation

  - title: "LDK #1860 adds support for channels using anchor outputs"
    url: /en/newsletters/2023/02/01/#ldk-1860

  - title: "LDK #1841 implements a solution for the fee-stealing attack described in BOLTs #824"
    url: /en/newsletters/2023/05/24/#ldk-1841

  - title: "LDK #2368 allows manually accepting new channels created by a peer that use anchor outputs"
    url: /en/newsletters/2023/06/28/#ldk-2368

  - title: "Core Lightning #6334 updates and expands CLN's experimental support for anchor outputs"
    url: /en/newsletters/2023/07/05/#core-lightning-6334

  - title: Discussion about LN anchors and v3 transaction relay proposal
    url: /en/newsletters/2024/01/10/#discussion-about-ln-anchors-and-v3-transaction-relay-proposal

  - title: "Research about historic use of anchor outputs for possibly imbuing them with v3 properties"
    url: /en/newsletters/2024/02/14/#what-would-have-happened-if-v3-semantics-had-been-applied-to-anchor-outputs-a-year-ago

  - title: "Core Lightning #6785 makes anchor-style channels the default"
    url: /en/newsletters/2024/02/14/#core-lightning-6785

  - title: "Eclair #2816 allows the node operator to choose the max fee for an anchor output"
    url: /en/newsletters/2024/02/14/#eclair-2816

  - title: "Core Lightning #7388 removes the ability to create old non-zero-fee anchor-style channels"
    url: /en/newsletters/2024/06/28/#core-lightning-7388

  - title: "Eclair v0.11.0 stops accepting new non-anchor channels"
    url: /en/newsletters/2024/12/06/#eclair-v0-11-0

  - title: "Core Lightning #7832 spends from anchor outputs even when not urgent"
    url: /en/newsletters/2024/12/06/#core-lightning-7832

  - title: "LDK #3608 doubles the expected max blocks required to confirm an HTLC due to `1 CSV` delay"
    url: /en/newsletters/2025/03/14/#ldk-3608

## Optional.  Same format as "primary_sources" above
see_also:
  - title: CPFP carve-out
    link: topic cpfp carve out

  - title: Package relay
    link: topic package relay

  - title: Ephemeral anchors
    link: topic ephemeral anchors
---
Each time the balance changes in an LN channel, a *commitment
transaction* is created and signed by the participating parties.  The
transaction is only broadcast if one party decides to
unilaterally close the channel (e.g. because the other party has
become unresponsive).  Because the broadcast of the commitment
transaction may occur a long time after it was created, the commitment
transaction may pay too much or too little in transaction fees.
Paying a too-low feerate may prevent the commitment transaction from
confirming before any timelocks contained within it expire, allowing
funds to be stolen.

The solution to this is for the commitment transaction to pay a
minimal amount of fees and then to allow either channel participant to fee
bump the transaction.  Early designs to accomplish this using [Replace-by-Fee
(RBF)][topic rbf] fee bumping ran into problems with [transaction
pinning][topic transaction pinning].  Later designs used
[Child Pays For Parent (CPFP)][topic cpfp] fee bumping and came to
depend on [CPFP carve-out][topic cpfp carve out] to circumvent the
pinning problem.

As of this writing, the most recent versions of the design add two
outputs to the commitment transaction---one for each LN party---and
require all other outputs in the commitment transaction to have their
scripts encumbered by a `1 OP_CHECKSEQUENCEVERIFY` (CSV) condition
that prevents them from being spent for at least one block.

To be fully effective, the protocol also depends on Bitcoin full nodes
implementing [package relay][topic package relay] so that there's a
way to CPFP fee bump commitment transactions even if their feerates
are below a node's minimum relay fee.  But until package relay is
available, it's possible for LN nodes to just pay a somewhat higher
feerate on their commitment transactions to ensure that they'll be
accepted by nodes.

{% include references.md %}
