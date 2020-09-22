---
title: Hardware wallets
subtitle: A hardware wallet is a special type of cryptocurrency wallet which stores the user's private keys in a secure hardware device 
slug: hardware
weight: 10
tags:
  - ledger
  - trezor
---

## Advantages

They have major advantages over standard software wallets: private keys are stored in a protected area of a microcontroller, and cannot be transferred out of the device in plaintext. That means your funds are safe even when connected to an infected or malicious computer or a phishing/scam web page.

## Supported hardware wallets

{{< columns >}}

### Ledger wallet

Particl is currently supported by **[Ledger Wallet](https://www.ledger.com/)** and has been integrated in such a way that it supports cold staking. That means PART coins can be stored offline on a Ledger wallet and still cold stake from any staking node. Both the facts that no password is stored in memory and that there is no required exchange of private key between the hardware wallet and the device/computer it is connected to make PPoS the most secure Proof-of-Stake protocol in the blockchain industry.

{{< hint info >}}
**Follow our guides**\
on how to [use Particl with Ledger Wallet](/tutorial/ledger/)
{{< /hint >}}

<--->

### Trezor

The Particl development team has also started working on a **[Trezor](https://trezor.io/)** integration.

{{< hint info >}}
**Follow our guides**\
on how to [use Particl with Trezor Wallet](/tutorial/trezor/)
{{< /hint >}}

{{< /columns >}}