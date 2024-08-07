---
layout: page
permalink: /en/compatibility/samourai/

name: Samourai
internal_url: /en/compatibility/samourai
logo: /img/compatibility/samourai/samourai.png
rbf:
  tested:
    date: "2018-10-25"
    platforms:
      - Android
    version: "0.81"
  features:
    receive:
      notification: "false"
      list: "false"
      details: "na"
      shows_replaced_version: "true"
      shows_original_version: "true"
    send:
      signals_bip125: "true"
      list: "false"
      details: "na"
      shows_replaced_version: "true"
      shows_original_version: "false"
  examples:
    - image: /img/compatibility/samourai/rbf/settings-rbf.png
      caption: >
        Sending Transaction - Settings for sending RBF enabled transactions. RBF disabled by default.
    - image: /img/compatibility/samourai/rbf/send-screen-default.png
      caption: >
        Sending Transaction - Default send transaction screen. No RBF options.
    - image: /img/compatibility/samourai/rbf/send-stonewall-prompt.png
      caption: >
        Sending Transaction - Prompt during send transaction for “STONEWALL” feature.
    - image: /img/compatibility/samourai/rbf/transaction-list-sent.png
      caption: >
        Sending Transaction - Sent RBF enabled transaction. No RBF flag.
    - image: /img/compatibility/samourai/rbf/transaction-details-sent.png
      caption: >
        Attempting Transaction Replacement - Transaction details for RBF enabled transaction with Increase TX Fee option. Interesting note here - If there are no additional funds to pay for the bump, Samourai just fails silently here with no message and takes the user back to the transaction list screen.
    - image: /img/compatibility/samourai/rbf/sent-transaction-increase-fee.png
      caption: >
        Sending Transaction - Prompt when “increase tx fee” is chosen. Miner fee not customizable.
    - image: /img/compatibility/samourai/rbf/transaction-list-sent-replaced.png
      caption: >
        Sending Transaction - Send RBF replacement transaction replaces original RBF enabled transaction. No flag. Confirmation message does say “RBF transaction sent”.
    - image: /img/compatibility/samourai/rbf/transaction-list-incoming-rbf.png
      caption: >
        Receiving Transaction Signaling RBF - Transaction list screen for receiving RBF enabled transaction. No RBF flag.
    - image: /img/compatibility/samourai/rbf/transaction-details-incoming-rbf.png
      caption: >
        Receiving Transaction Signaling RBF - Transaction details prompt for received transaction. “View transaction” defaults to Smartbit explorer (explorer configurable in settings).
    - image: /img/compatibility/samourai/rbf/transaction-details-incoming-rbf-increase-fee.png
      caption: >
        Receiving Transaction Signaling RBF - Transaction details “Increase transaction
        fee” dialog which uses CPFP behind the scenes to increase the effective
        transaction feerate on the incoming transaction.
    - image: /img/compatibility/samourai/rbf/transaction-list-incoming-replacement.png
      caption: >
        Receiving Replacement Transaction - Transaction list screen showing both original and replacement transactions. Total reflecting sum of both transactions. No RBF flag or warnings.
    - image: /img/compatibility/samourai/rbf/transaction-list-replacement-confirmed.png
      caption: >
        Receiving Replacement Transaction - Transaction list screen updated to just show replacement transaction after a period of time. Even before either RBF signaling transaction was confirmed.
segwit:
  tested:
    date: "2019-07-25"
    platforms:
      - Android
    version: "0.99.82"
  features:
    receive:
      p2sh_wrapped: "true"
      bech32: "true"
      bech32m: "false"
      default: "bech32"
    send:
      bech32: "true"
      bech32m: "true"
      change_bech32: "true"
      segwit_v1: "Fails on broadcast of transaction to the network."
      bech32_p2wsh: "true"
  examples:
    - image: /img/compatibility/samourai/segwit/receive-screen.png
      caption: >
        By default, Samourai generates bech32 receive addresses.
    - image: /img/compatibility/samourai/segwit/send-screen.png
      caption: >
        Samourai can send to all segwit v0 addresses.
    - image: /img/compatibility/samourai/segwit/receive-screen-advanced.png
      caption: >
        Samourai allows the user to choose the type of their receive address.
    #- image: /img/compatibility/samourai/segwit/send-screen-segwit-v1-error.png
    #  caption: >
    #    Samourai wallet shows an error during broadcasting when trying to send
    #    to a segwit v1 address.
    - image: /img/compatibility/samourai/segwit/settings-transactions.png
      caption: >
        Samourai has setting options for 1. receive to segwit address and 2.
        receive change to like-typed outputs. Both of which are on by default.
    - image: /img/compatibility/samourai/segwit/settings-wallet.png
      caption: >
        Samourai has options to view the wallet's X/Y/ZPUBs.
---

<!-- Samourai -->

{% assign tool = page %}
{% include templates/compatibility-page.md %}
