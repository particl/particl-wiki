---
title: Ledger Wallet
subtitle: Using Particl with Ledger hardware wallets (Nano S/X)
slug:
weight: 3
tags:
  - Ledger wallet
aliases:
  - /tutorial/ledger
---

{{< image class="side-thumb" src="ledger-wallet.jpg" alt="Ledger Nano S" >}}

{{< toc >}}

## About Ledger Wallet

[Ledger Nano (S/X)](https://www.ledger.com/) is a hardware wallet which stores user's private keys in a secure hardware device.

Hardware wallets have major advantages over standard software wallets: **private keys are stored in a secure chip, and cannot be transferred out of the device**. That means your funds are safe even when connected to an infected or malicious computer or a phishing/scam web page.

For these reasons, we highly recommend users to protect their funds by setting up a Ledger or other [compatible hardware wallet](/learn/wallets/hardware/).


## Requirements

Before starting the setup process, make sure you have:

- **Ledger Nano S/X** hardware wallet – initialized and [updated to latest firmware](https://support.ledgerwallet.com/hc/en-us/articles/360002731113-Update-Ledger-Nano-S-firmware)
- **Ledger Live** app [ready to use](https://support.ledger.com/hc/en-us/articles/360006395233)
- **[Particl Core](/tutorial/wallets/particl-core/) wallet** installed and fully synced to the Particl network

{{< hint warning >}}
**Linux users:** Make sure you have added the `udev` rules to allow device access – see [Fix connection issues](https://support.ledgerwallet.com/hc/en-us/articles/115005165269-Fix-connection-issues) (under Linux tab) for more info. If you already have a working Ledger wallet, you can skip this.
{{< /hint >}}


## Installation

### Ledger Particl app

First, we need to install Particl on your Ledger device (feel free to follow [official Ledger's guide](https://support.ledger.com/hc/en-us/articles/360007687153) though it's the same):

  1. open the **Manager** in Ledger Live
  2. connect and unlock your Ledger Nano S
  3. if asked, allow the manager on your device by pressing the right button
  4. find Particl app in the catalog
  5. click the **Install** button of the app

Note that if you're forced to uninstall Particl app from your Ledger (due to lack of space), you'll have to repeat these steps to access your funds. Don't worry, your coins will stay safe even if the app isn't installed in the meantime.

### Particl Core configuration

{{< hint alert >}}
**If you already have a Particl wallet on this computer**, make sure to [back up the wallet.dat file](/tutorial/security/backup-restore-wallet/) by renaming or moving it elsewhere!
{{< /hint >}}

{{< columns >}}
{{< image src="particl-ledger-install-01.png" >}}
<--->
{{< image src="particl-ledger-install-02.png" >}}
{{< /columns >}}

  1. launch [Particl Core](/tutorial/wallets/particl-core/) on your computer
  2. go to _Window → HD Wallet_ (if it's the first time you're setting up a wallet on this computer or if you don't have any `wallet.dat` file in your Particl config folder, then Particl Core will automatically bring you to this dialog)
  3. click on the **Hardware Device** tab
  4. connect your Ledger Nano S to your computer via USB
  5. make sure the device is properly unlocked (and already initialized via Ledger Live)
  6. click on **Import**
  7. when your Particl Core wallet says _Waiting for device_, follow the instructions displayed on your Ledger hardware wallet screen

Your Particl Core client is now ready to be used in conjunction with your Ledger hardware wallet!


## Usage

### Sending PART using Ledger

{{< columns >}}
{{< image src="particl-ledger-sending-01.png" >}}
<--->
{{< image src="particl-ledger-sending-02.png" >}}
{{< /columns >}}

  1. open your **Particl Core** client containing your Ledger hardware wallet (as set up in the steps above)
  2. connect your Ledger hardware wallet to your computer and unlock it using your PIN code
  3. select and start the Particl application on your Ledger hardware wallet
  4. click on Particl Core's **Send** tab
  5. enter your transaction details (PART amount and destination address)
  6. click **Send → Yes**
  7. Particl Core will prompt you to follow the steps displayed on your Ledger hardware wallet's screen – confirm the transaction on your device if the transaction details are correct

### Cold staking on Ledger

{{< hint info >}}
**Refer to dedicated [how to cold stake on Ledger](/tutorial/staking/ledger) guide** for information about securely [cold staking](/learn/staking/intro/#cold-staking) on Ledger wallet.
{{< /hint >}}