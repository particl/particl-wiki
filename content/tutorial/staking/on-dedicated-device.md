---
title: Staking on DSD with Partyman
subtitle: DSD are ideal way for running Particl full node and getting staking rewards for securing the network 24/7
slug: 
weight: 3
tags:
  - staking
  - DSD
---

A Staking Node is a full blockchain node which has been configured to stake on behalf of your wallet (aka it has been delegated staking power over your wallet). The Staking Node is a computer running Particl that is always on and always connected to the internet. A Raspberry Pi 3 or comparable device (DSD) makes a perfect staking node as it consumes very little energy, is compact and easy to tailor for dedicated tasks.

{{< hint info >}}
Before you'll dive into this guide, **familiarize yourself with [Dedicated Staking Devices](/learn/staking/dedicated-devices/) and [Partyman utility](/learn/staking/partyman/)**.
{{< /hint >}}


## Requirements

Even though you could set up `particld` for staking on your DSD manually, we'll focus on using Partyman staking utility, thanks to all the automation and ease of use it offers.

- **Particl wallet** – your primary wallet with funds on it ([Particl Desktop](/tutorial/wallets/particl-desktop/), [Particl Core](/tutorial/wallets/particl-core/) or [Particl Copay](/tutorial/wallets/particl-copay/))
- **hardware for staking** – Raspberry Pi +3, Rock64 or other ("DSD")
  - older versions of RPi should work as well, but keep in mind that CPU performance does matter when staking, so you might not get ideal results
  - at least **32 GB of storage** (SD card)
  - **internet access** (wifi or cable) set up and working (follow guides for your device)
  - **SSH access** to device or connected monitor
  - **Debian/Ubuntu**-based OS (you can use any other distro, but you'll have to change following commands accordingly)

## Installation

{{< hint info >}}
**Visit [Partyman's Github repo](https://github.com/dasource/partyman)** for more information if needed.
{{< /hint >}}

1. SSH to your device (or connect your monitor)
2. Make sure your system is up-to-date:

```bash
sudo apt update && sudo apt upgrade
```

### Install Partyman

Download Partyman and install its dependencies:

```bash
sudo apt-get install python git unzip pv jq dnsutils
cd ~ && git clone https://github.com/dasource/partyman
```

Install Partyman:

```bash
cd partyman/
./partyman install
```

This will download, unzip and install the latest release Particl Core daemon (`particld`).

Start `particld` daemon:

```bash
./partyman restart now
```

Check `particld` status and verify everything is running correctly (you might need to wait a minute or two, before `particld` finishes starting up):

```bash
./partyman status
```

You should see a summary similar to this:

{{< image src="https://particl.news/glink/size/w1600/2020/10/image.png" alt="Output of './partyman status' command" >}}

Great! Your node is now managed by Partyman and you have the latest `particld` daemon running!


### Create a staking wallet

Generate a new wallet on the device by running:

```bash
./partyman stakingnode init
```

Follow instructions on screen to complete wallet setup.

{{< hint alert >}}
**Make sure you safely note node's [Recovery Phrase in a safe place](/tutorial/security/recovery-phrase/)!**\
This is the only key to your wallet in the unfortunate event that your device would got broken/stolen etc. Lose the key = lose the wallet!
{{< /hint >}}


### Generate staking public key

Next, we’ll create the public key which we will use within the Particl Desktop/Core to activate Cold Staking. We'll use Partyman utility for this as well.

To generate a new staking public key:

```bash
./partyman stakingnode new
```

Follow the directions to complete staking node public key creation. Public key label is just for you, so you know which key is connected to which wallet (in case you want to use multiple ones, e.g. staking on your desktop Particl Desktop _and_ your mobile Particl Copay).

You should see a Particl public key similar to this:

```
PPARTKVAobLsHTQpZ5LzFHcZw8LD4sEEVuUdmcuAqCjDaaNJgypRmUUpFKMxbmn1hZ5V2J9SaG1QusCrngC9iiBAA8LvxVRx9aLBPjGeY4PtrxzW
```

And there's your staking public key! Make note of it somewhere, you'll need it later (friendly reminder that `CTRL+C` in Terminal doesn't copy text, so use your mouse's right-click instead).

### Summary

So far, we've achieved to:

- setup Partyman utility for managing your node via Partyman
- downloaded and autoconfigured latest Particl Core daemon on your device
- created a new Particl wallet on the device, dedicated to staking
- generated public key for staking (so that we can connect our main wallet to this DSD)

That concludes all the "tedious work" via Terminal on your Staking Node! Let's now move onto your main wallet and connect it with your Staking Node.

### Connect your wallet

{{< hint info >}}
To connect your wallet, **follow our unified [Cold staking setup](/tutorial/staking/cold-staking#connect-your-wallet) guide.**
{{< /hint >}}


## Maintenance

When your node is successfully set up, here are some tips to keep your node healthy and up-to-date.

### Updating particld

**You should always keep your node up-to-date with latest Particl Core releases.**

To update your node:

1. SSH to your device (or connect your monitor)
2. Make sure your system is up-to-date: `sudo apt update && sudo apt upgrade`
3. To update partyman: `~/partyman/partyman update` and follow on-screen instructions
4. Wait a couple minutes for `particld` to restart and check status of your node with `~/partyman/partyman status` - look for `particld staking currently? : YES`

#### Updating to pre-release versions

In case you want to update your `particld` to pre-release version (ie. betas, not yet stable releases), you can do so by:

```bash
cd ~/partyman/
git pull
./partyman update -prer
```

### Updating partyman

In case partyman complains about updates available, you can install them simply by going to partyman's directory and getting the latest code from GitHub:

```bash
cd ~/partyman/
git pull
```
