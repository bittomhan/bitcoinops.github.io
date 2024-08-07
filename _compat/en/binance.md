---
layout: page
permalink: /en/compatibility/binance/

name: Binance
internal_url: /en/compatibility/binance
logo: /img/compatibility/binance/binance.png
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
    - image: /img/compatibility/binance/rbf/send-screen.png
      caption: >
        Sending Transaction - Default send (withdrawal) screen. No RBF options.
    - image: /img/compatibility/binance/rbf/transaction-list-sent.png
      caption: >
        Attempting Transaction Replacement - Transaction not sent via RBF. No fee bump options.
    - image: /img/compatibility/binance/rbf/transaction-list-incoming-rbf.png
      caption: >
        Receiving Transaction Signaling RBF - No unconfirmed transactions appear in transaction list.
    - image: /img/compatibility/binance/rbf/transaction-list-replacement-confirmed.png
      caption: >
        Receiving Replacement Transaction - Replacement transaction only shows up after confirmation. Neither transaction shows before.
segwit:
  tested:
    date: "2019-04-11"
    platforms:
      - web
    version: "n/a"
  features:
    receive:
      p2sh_wrapped: "false"
      bech32: "false"
      bech32m: "false"
      default: "p2pkh"
    send:
      bech32: "true"
      bech32m: "false"
      change_bech32: "untested"
      segwit_v1: "Does not pass front end javascript validation"
      bech32_p2wsh: "false"
  examples:
    - image: /img/compatibility/binance/segwit/receive-screen.png
      caption: >
        Binance receives via P2PKH addresses.
    - image: /img/compatibility/binance/segwit/send-screen.png
      caption: >
        Default send screen accepts a bech32 address.
    - image: /img/compatibility/binance/segwit/send-address-error.png
      caption: >
        While Binance allows bech32 P2WPKH withdrawals, you cannot add a bech32 address
        to your address book _from the send screen_. While attempting to add a bech32 address, after
        the two-factor authentication code, an address error message appears.
    - image: /img/compatibility/binance/segwit/send-p2wsh-error.png
      caption: >
        Bech32 P2WSH addresses cause a validation error from the send screen and address
        book screens.
    - image: /img/compatibility/binance/segwit/address-book-add.png
      caption: >
        Bech32 P2WPKH addresses can be successfully added using the address book functionality.
---

<!-- Binance -->

{% assign tool = page %}
{% include templates/compatibility-page.md %}
