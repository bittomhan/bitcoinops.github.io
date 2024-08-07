---
layout: page
permalink: /en/compatibility/wasabi/

name: Wasabi
internal_url: /en/compatibility/wasabi
logo: /img/compatibility/wasabi/wasabi.png
rbf:
  tested:
    date: "2019-12-19"
    platforms:
      - macOS
    version: "1.1.10"
  features:
    receive:
      notification: "true"
      list: "false"
      details: "false"
      shows_replaced_version: "true"
      shows_original_version: "false"
    send:
      signals_bip125: "false"
      list: "false"
      details: "false"
      shows_replaced_version: "true"
      shows_original_version: "false"
  examples:
    - image: /img/compatibility/wasabi/rbf/send-screen.png
      caption: >
        Sending Transaction - Send transaction screen. No RBF options. Wasabi
        does signal for RBF randomly for 2% of transactions.
    - image: /img/compatibility/wasabi/rbf/transaction-list-sent.png
      caption: >
        Attempting Transaction Replacement - Transaction list screen showing
        sent transaction. No RBF bump options. Transaction not sent signaling
        RBF. While Wasabi does not support manual sending RBF signaling transactions,
        if a transaction replacement is done using the same seed in a different
        wallet, Wasabi shows only the replacement transaction in the transaction
        list.
    - image: /img/compatibility/wasabi/rbf/transaction-list-incoming-rbf.png
      caption: >
        Receiving Transaction Signaling RBF - Incoming RBF signaling
        transaction. No RBF flag.
    - image: /img/compatibility/wasabi/rbf/notification-incoming-rbf.png
      caption: >
        Receiving Transaction Signaling RBF - Incoming RBF signaling
        transaction notification notes that a transaction is replaceable. Wasabi
        also displays whether the transaction was a replacement transaction.
    - image: /img/compatibility/wasabi/rbf/transaction-list-incoming-replacement.png
      caption: >
        Receiving Replacement Transaction - Replacement transaction replaces
        original transaction after transaction fee bump. No RBF indicator.
segwit:
  tested:
    date: "2019-12-19"
    platforms:
      - macOS
    version: "1.1.10"
  features:
    receive:
      p2sh_wrapped: "false"
      bech32: "true"
      bech32m: "untested"
      default: "bech32"
    send:
      bech32: "true"
      bech32m: "true"
      change_bech32: "true"
      segwit_v1: "Fails on validation of the address."
      bech32_p2wsh: "true"
  examples:
    - image: /img/compatibility/wasabi/segwit/receive-screen.png
      caption: >
        Wasabi only generates bech32 receive addresses.
    - image: /img/compatibility/wasabi/segwit/send-screen.png
      caption: >
        Wasabi allows sending to any segwit v0 address.
    #- image: /img/compatibility/wasabi/segwit/send-screen-segwit-v1-error.png
    #  caption: >
    #    Wasabi displays a validation error when attempting to send to a segwit
    #    v1 address.
---

<!-- Wasabi -->

{% assign tool = page %}
{% include templates/compatibility-page.md %}
