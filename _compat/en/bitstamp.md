---
layout: page
permalink: /en/compatibility/bitstamp/

name: Bitstamp
internal_url: /en/compatibility/bitstamp
logo: /img/compatibility/bitstamp/bitstamp.png
rbf:
  tested:
    date: "2018-11-06"
    platforms:
      - web
    version: "n/a"
  features:
    receive:
      notification: "false"
      list: "false"
      details: "false"
      shows_replaced_version: "false"
      shows_original_version: "false"
    send:
      signals_bip125: "false"
      list: "untested"
      details: "untested"
      shows_replaced_version: "untested"
      shows_original_version: "untested"
  examples:
    - image: /img/compatibility/bitstamp/rbf/send-screen.png
      caption: >
        Sending Transaction - Send transaction screen. No fee or RBF
        options. Transaction not sent via RBF.
    - image: /img/compatibility/bitstamp/rbf/transaction-list-sent.png
      caption: >
        Attempting Transaction Replacement - Transaction list screen with sent transaction. No bumping option since transaction was not RBF.
    - image: /img/compatibility/bitstamp/rbf/transaction-list-incoming-rbf.png
      caption: >
        Receiving Transaction Signaling RBF - No transaction listed when original transaction broadcast.
    - image: /img/compatibility/bitstamp/rbf/transaction-list-replacement-confirmed.png
      caption: >
        Receiving Replacement Transaction - Only saw a transaction after the
        replacement transaction confirmed. Didn’t see original.
segwit:
  tested:
    date: "2021-01-27"
    platforms:
      - web
    version: "n/a"
  features:
    receive:
      p2sh_wrapped: "true"
      bech32: "true"  # https://www.bitstamp.net/article/weve-added-support-bech32-bitcoin-addresses-bitsta/
      bech32m: "untested"
      default: "p2sh_wrapped_p2wsh"
    send:
      bech32: "true"   # https://www.bitstamp.net/article/weve-added-support-bech32-bitcoin-addresses-bitsta/
      bech32m: "untested"
      change_bech32: "untested"
      segwit_v1: "Address text input doesn’t allow bech32 addresses due to
      character limits."
      bech32_p2wsh: "true"
  examples:
    - image: /img/compatibility/bitstamp/segwit/receive-screen.png
      caption: >
        Bitstamp receives deposits to P2SH-P2WSH addresses.
---

<!-- BitStamp -->

{% assign tool = page %}
{% include templates/compatibility-page.md %}
