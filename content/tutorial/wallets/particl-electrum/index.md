---
title: Particl Electrum
subtitle: Light wallet with advanced features focused on ease of use and accessibility
slug:
weight: 2
tags:
  - Particl Electrum
aliases:
  - /tutorial/particl-electrum/start
---

{{< image class="side-thumb" src="particl-electrum.png" alt="Preview of Particl Electrum" >}}

Particl Electrum is a light wallet that doesn't require you to download the blockchain to use. Instead, it uses the SPV technique Satoshi Nakamoto [described in his Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf). This protocol lets the client verify that a transaction what successfully sent through the blockchain by only downloading the headers, which are many times smaller in size than the full blockchain.

The Particl Electrum light wallet lets you send and receive coins on desktop and Android devices and also enables a few advanced features such as multi-signatures and cold staking.

Additionally, its back-end is intended to become a cornerstone of Particl's broader accessiblity ambitions, notably by enabling Particl Marketplace and the BasicSwap DEX to be deployed on and accessed from the web. In other words, using Particl Electrum as an end-user wallet is only scratching the surface of what it's intended to be. 


{{< button href="https://particl.io/downloads" class="primary" >}}Download Particl Electrum{{< /button >}}
{{< button href="https://github.com/particl/electrum/issues" >}}Report bugs{{< /button >}}


## Features

[Browse & compare Particl Electrum's features](/learn/wallets/overview/#comparison) with other available wallets.


## Getting started

### Installation

{{< hint info >}}
Please note that even though some of these steps are optional/recommended, it is highly advised to follow all of them as it secures your funds from being lost.
{{< /hint >}}

  1. **Download** the [latest release](https://github.com/particl/electrum/releases/latest)
  2. {{< label info >}}Recommended{{< /label >}} [Verify the downloaded archive](/tutorial/security/verify-downloads/) (to make sure you haven't downloaded bad client, e.g. infected with malware)
  3. Launch the client (if you're on Linux, then make sure to carefully [follow these steps](https://github.com/particl/electrum/blob/master/README.rst)
  4. Follow through the steps contained in the setup wizard
  5. When prompted for it, check `Select server manually` and, in the page that follows, uncheck `Select server automatically`
  6. Enter either of these two Electrum servers: `164.92.93.20:50002` or `5.22.218.7:50002`
  7. {{< label alert >}}Warning{{< /label >}} Make absolutely sure to properly backup your Recovery Phrase safely (digital backups are not recommended)
  8. {{< label info >}}Recommended{{< /label >}} **Encrypt your wallet** with a secure password
  9. {{< label info >}}Recommended{{< /label >}} **Backpu your wallet** by opening up the `File` tab at the top of you client and clicking on `Save Backup`. In the window that appears, choose a location on your computer, or an external device, and click on `Ok` 