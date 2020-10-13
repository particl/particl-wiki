---
title: Cold staking on Ledger wallet
subtitle: This tutorial will walk you through the steps of setting your Ledger Nano S/X hardware wallet up for cold staking on the Particl blockchain
slug: 
weight: 4
tags:
  - staking
  - Ledger wallet
---

This tutorial assumes Particl has been [properly installed on your Ledger Nano S/X](/tutorial/wallets/ledger) hardware device and that your [Particl Core](/tutorial/wallets/particl-core/) wallet is set up for Particl on Ledger. 


## Requirements

Before starting the setup process, make sure you have:

* **Cold staking public key** – you can get it by either:
  - self-hosting a [cold staking node](/tutorial/staking/on-dedicated-device/) (on Raspberri Pi/Rock64 etc.)
  - or by joining one of the [available staking pools](/learn/staking/pools#available-staking-pools)
* A [Ledger hardware wallet with Particl installed on it](/tutorial/wallets/ledger)
* **Ledger Live** app [ready to use](https://support.ledgerwallet.com/hc/en-us/articles/360006395233)
* **[Particl Core](/tutorial/wallets/particl-core/)** wallet installed and fully synced


## Staking setup

### Get your staking public key

{{< tabs "pubkey" >}}

{{< tab "Staking Pool" >}}
#### Via staking pool

Choose one of the [available staking pools](/learn/staking/pools#available-staking-pools) and note somewhere its **staking public key** (they are usually right there on the top of the page).
{{< /tab >}}

{{< tab "Dedicated Staking Device" >}}
#### Via self-hosted staking node

1. [Set a staking node up](/tutorial/staking/on-dedicated-device/) (if you haven't already done so)
2. In your staking node's terminal screen, **create a new public key** by entering the following in partyman's folder: 

```bash
./partyman stakingnode new
```

3. Note the public key somewhere, you will need it for later
{{< /tab >}}

{{< /tabs >}}


### Connect Particl Core to your staking node

1. open and unlock **Particl Core**
2. plug your Ledger to your computer and make sure it is ready to transact (verify if there isn't any required update and that everything is okay on Ledger Live)
3. open the **Staking setup** window by going in **Window** → **Staking Setup**
4. enter the noted staking **public key** into _Cold staking change address_ field
5. confirm by clicking `Apply`

{{< image src="particl-core-staking-setup-01.png" alt="Opening Staking Setup window" >}}
{{< image src="particl-core-staking-setup-02.png" alt="Entering Staking node public key" >}}

### Initiate cold staking

> AKA "zapping" coins

To initiate cold staking on your Ledger using Particl Core, your coins need to be on a cold staking address (which at that point, they aren't yet). To do just that, you will need to: 

1. Enable **Coin Control**
    1. _Settings → Options_
    2. in **Wallet** tab, check “Enable coin control features”
    3. confirm by clicking `OK`
2. Generate new Receiving address and copy it
    1. _Receive_ → click `Request payment`
    2. copy generated address
3. Send some small amount to your newly generated address using all available non-staking outputs
    1. _Send_ → under **Coin Control Features** click on `Inputs...`
    2. check all available outputs with addresses starting with `P` and confirm with `OK` (note: if you have any addresses starting with `2`, those coins are already cold staking – don't select those)
    3. copy your previously generated receiving address to **Pay to** field
    4. set transaction **Amount** to some small value like **0.001 PART**
    5. click `Send` and confirm

{{< video webm="particl-core-coldstaking-zap.webm" alt="Zapping on Particl Core" >}}

This will send all but those 0.001 PART to your cold staking address(es). Once the sent coins mature for staking (about 8 hours), they will start staking automatically on your Ledger.


### Verify your setup

You can check that your coins are correctly sent to your staking node (or a pool).

#### Via Particl Core

In Particl Core, go to Staking setup again (_Window_ → _Staking Setup_) – you should see:

- Cold staking enabled: True
- Percent in cold staking script: 100.00 (or something really close like 99.81)

#### Via your staking node

If you're self-hosting your staking node, SSH into your device again and in partyman's folder run:

```
./partyman status
```

The output of that command should indicate `particld staking currently?: YES` as well as display the number of coins being staked by the staking node next to `particld staking wallet weight: <amount of your coins>`

Congratulations, you're now successfully (and safely!) staking your PART from Ledger hardware wallet!