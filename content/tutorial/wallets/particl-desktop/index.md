---
title: Particl Desktop
subtitle: Particl's main GUI wallet with most of the features, including Particl Open Marketplace 
slug:
weight: 1
tags:
  - Particl Desktop
---

{{< toc >}}

{{< hint success >}}
**Recommended** for beginners and majority of users
{{< /hint >}}

{{< image class="side-thumb" src="particl-desktop-3.0.png" alt="Preview of Particl Desktop 3.0" >}}


## About Particl Desktop

While it does not currently contain all advanced features (like [Particl Core](/tutorial/particl-core/)), Particl Desktop is a recommended wallet for majority of users.

This wallet is intended to be the centerpiece and default wallet of the Particl platform and is heavily under development. More features are added with every new release.


{{< button href="https://particl.io/downloads" class="primary" >}}Download Particl Desktop{{< /button >}}
{{< button href="https://github.com/particl/particl-desktop/issues" >}}Report bugs{{< /button >}}


## Features

[Browse & compare Particl Desktop's features](/learn/wallets/overview/#comparison) with other available wallets.


## Installation

{{< hint alert >}}
**Never download Particl clients from 3rd party websites!**\
Hackers and bad actors are constantly trying to distribute malware-infected versions of popular cryptocurrency wallets, so they could steal your coins! Always download from official sources only!
{{< /hint >}}

1. [**Download** the latest version](https://particl.io/downloads) of Particl Desktop
2. {{< label info >}}Recommended{{< /label >}} [**Verify** the downloaded wallet](/tutorial/security/verify-downloads/) to make sure you have the proper download and not a fake/malware-infected wallet
3. **Extract** the content of the ZIP file to any location on your computer
4. **Launch** Particl Desktop:

{{< tabs "pd-installation" >}}
{{< tab "Windows" >}}
Launch Particl Desktop by clicking the `Particl Desktop.exe` file.
{{< /tab >}}
{{< tab "macOS" >}}
Launch Particl Desktop by clicking the `Particl Desktop` executable file.
{{< /tab >}}
{{< tab "Linux" >}}
Open Terminal in extracted directory and launch Particl Desktop by executing `./"Particl Desktop"`.
{{< /tab >}}
{{< /tabs >}}

5. Wait for Particl Desktop to load and download the latest Particl Core daemon version – this will happen automatically on launch each time a newer version of daemon is available
6. Read and **accept the terms** and conditions if you agree with them to start using Particl Desktop

### Creating a new wallet

{{< image class="side-thumb" src="particl-desktop-create-wallet.png" alt="Creating a new wallet on Particl Desktop 3.0" >}}

When you launch Particl Desktop for the first time, you'll be prompted to create a new wallet. After all, without a working wallet, your Particl Desktop won't be very useful.

If you already have a working wallet and want to create another one, you can easily do so by clicking on the wallet switcher in the left sidebar and choose Create a new wallet.

1. Click on `Create new wallet`
2. Choose an encryption password for your wallet and click on `Continue`

{{< hint alert >}}
**This password is going to encrypt your `wallet.dat` file**.\
You will need it each time you want to unlock your wallet and will also be required if you want to restore a backup of your wallet file.
{{< /hint >}}

3. Carefully save the Recovery Phrase somewhere safe and click on `Continue`

{{< hint info >}}
**This 24-word seed allows you to [restore your wallet](/tutorial/security/backup-restore-wallet/)** without requiring the `wallet.dat` file nor your encryption password. [Keep this Recovery Phrase safe](/tutorial/security/recovery-passphrase/)!
{{< /hint >}}

4. To ensure you've properly saved your Recovery Phrase, enter the missing words in the empty fields
5. (Optional) Pick a [Recovery Password](/tutorial/security/good-password) and click on `Continue`

{{< hint warning >}}
**This password encrypts your Recovery Phrase**.\
If you opt to add a password and lose it, your seed becomes unusable. This password prevents someone to have access to your funds if they find your Recovery Phrase, but if you forget about the password, you will permanently lose access to your funds. It is advised to leave this field empty if you are not experienced.
{{< /hint >}}

6. Let Particl Desktop setup your wallet – this step shouldn’t take more than a few minutes

{{< hint info >}}
**If the client gets stuck and does not progress** to the next step after more than 10 minutes, you can close and reopen it. This will give you access to your wallet, but you will need to manually generate public and private addresses by going to the receive tab and click on `New public/private address`.
{{< /hint >}}

7. Click on `Finish setup` to have access to your newly created wallet.
8. Let the blockchain sync completely. You can track the progress by looking at the progress bar at the bottom left corner of the client.

Now when your new wallet is successfully created, it's time to [backup your wallet](/tutorial/security/backup-restore-wallet/) in case something terrible would happen e.g. with your PC. Never underestimate proper backups!


## Staking

Secure the Particl network and earn staking rewards:

- [★ How to stake](/tutorial/staking/intro/)
- [★ Cold staking setup](/tutorial/staking/cold-staking/)