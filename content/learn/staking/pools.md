---
title: Cold Staking Pools
slug: pools
subtitle: Cold staking pools are to Proof-of-Stake coins what mining pools are to Proof of Work coins (like Bitcoin)
weight: 3
tags:
  - staking
  - pools
---

{{< toc >}}

> In the context of cryptocurrency mining, a mining pool is the pooling of resources by miners, who share their processing power over a network, to split the reward equally, according to the amount of work they contributed to the probability of finding a block. — Wikipedia

In fact, cold staking pools allow you to “team up” with other stakers and combine your staking powers in order to earn more frequent staking rewards. All rewards earned while staking from a pool are sent over to the pool operator, which then executes payouts proportional to how much you’ve contributed to the total amount of rewards the pool earned. This is particularly useful if you own fewer coins and still want to stake your coins as it means you’ll earn more frequent, but smaller, staking rewards.

{{< hint info >}}
**How to cold stake on a Pool?**\
Follow our guide at [Tutorial: Cold Staking setup](tutorial:staking:cold-staking)
{{< /hint >}}

## The importance of decentralization

{{< hint warning >}}
It is **highly recommended** to be careful about which cold staking pool you choose to stake your funds with. In fact, because you are effectively delegating your staking power to a third-party, **staking from a cold staking pool tends to centralize the staking weight of the network**. 
{{< /hint >}}

In order to be as secure as possible, Proof-of-Stake blockchains need to both have as many coins being staked as possible and as many staking nodes online as possible. The reason behind this is actually similar to [Proof of Work's 51% attack](https://www.investopedia.com/terms/1/51-attack.asp) where an attacker could get full control over the blockchain if he held more than 50% of all the hashing power (mining power) on the network.

On Particl, this attack vector is still possible, although a bit different. **For such an exploit to be successful, an attacker, like a malicious pool operator, would need to be in possession of more than 50% of all staking coins.** This is the reason you should always be careful not to delegate your staking power to a pool that already holds a considerably high amount of staking weight.

{{< hint alert >}}
**The Particl team is not responsible for the management, user support, and debugging of any pool.**\
While we will offer support for the cold staking pool code itself, we won’t be offering support for any of its implementation made by third-parties; this responsibility should lie within the pool operator himself.
{{< /hint >}}

## Available Staking Pools

| Pool name             | Link                          | Pool fees |
| --------------------- | ----------------------------- | --------- |
| **Particl.Page Pool** | https://pool.particl.page     | 2.5 %     |
| **Crymel's Pool**     | https://particl.crymel.icu    | 2.5 %     |
| **CoinRollin**        | https://coinroll.in           | 1 %       |
| **Arcadia's Pool**    | https://stake.arcadia.agency/ | 3 %       |

_Last update: 2020/08/24_

## Advanced

### Running your own Pool

{{< hint info >}}
**If you're confident enough to run your own Pool**, visit [official Particl Coldstake Pool repo](https://github.com/particl/coldstakepool) and follow instructions in its [doc folder](https://github.com/particl/coldstakepool/tree/master/doc).
{{< /hint >}}