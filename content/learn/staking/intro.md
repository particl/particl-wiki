---
title: About Particl's PoS
slug: intro
subtitle: The Particl platform uses a custom Proof-of-Stake protocol, Particl Proof-of-Stake (PPoS), as its consensus mechanism
weight: 3
tags:
  - staking
  - important
---

{{< toc >}}

## About Particl Staking

Proof-of-Stake (PoS) is a type of algorithm by which a cryptocurrency blockchain network aims to achieve distributed consensus. In PoS-based cryptocurrencies, the creator of the next block is chosen via various combinations of random selection of wealth and age. In contrast, the algorithm of Proof-of-Work (PoW) based cryptocurrencies such as bitcoin rewards participants who solve complicated cryptographical puzzles in order to validate transactions and create new blocks (i.e. mining).

PPoS is built and improved upon the popular PoS3 protocol on top of which were added several security and utility features.

{{< hint info >}}
**How to stake on Particl?**\
Follow our guides at [Tutorial: How to Stake](/tutorial/staking/)
{{< /hint >}}

## Passive Income

PPoS can serve as a great passive income tool. It rewards stakers a minmum rate of 5% per year for securing the network, then drops 1% every year until it plateaus at 2%:

| Period | Staking rewards / inflation rate |
| ------ | -------------------------------- |
| July 2017 – July 2018 | 5 % |
| July 2018 – July 2019 | 4 % |
| July 2019 – July 2020 | 3 % |
| July 2020 onwards     | 2 % |

{{< hint info >}}
**This staking reward rate is true if 100% of the total supply is put up for staking**, but gets higher as less coins are being staked. For example, if 50% of the total network is being put up for staking, the staking reward rate for the first year would be of 10%.
{{< /hint >}}

The Particl platform also redirects any fee generated from it directly to stakers, including but not limited to currency transactions, marketplace listing fees, extended messaging, privacy balance transfers and others, meaning staking becomes more profitable as the platform gets more traffic.


## Cold Staking

Cold staking is enabled by smart-contract functionality and lets users securely delegate staking powers to “staking nodes” which contain no coin. The purpose of these “staking nodes” is to provide a dedicated resource connected to the Particl blockchain and stake on behalf of another wallet without being able to spend its coins.

Cold staking nodes are intended to be used in combination with cold, hardware and multisig addresses, making it possible to stake “offline” coins with no risk of being hacked or exposing your public key to the network. Staking nodes can be set up on any device, secure or not, such as public/cloud servers, virtual machines or DSDs.

{{< hint info >}}
**How to cold stake on Particl?**\
Follow our guide at [Tutorial: Cold Staking setup](/tutorial/staking/cold-staking/)
{{< /hint >}}

### Cold Hardware Staking

It is currently possible to cold stake funds stored offline on a hardware wallet by setting up a Particl wallet on a [Ledger hardware wallet](/tutorial/staking/ledger/).

While cold staking does not store any password in memory and delegates staking powers to empty staking nodes, a cold wallet is still vulnerable when it's interacted with (i.e. when a transaction is executed) from an infected or untrusted computer. [Hardware wallets](/learn/hardware-wallets/) fix this issue by not requiring any exchange of private key between the hardware wallet and the device/computer it is connected to, thus making hardware wallets safe even when they are interacted with from an infected computer.

{{< hint success >}}
Combining **cold staking and hardware security effectively makes PPoS the most secure Proof-of-Stake protocol in the industry** and fixes several issues generally associated with the Proof-of-Stake consensus protocol in general.
{{< /hint >}}

### Quantum-resistance & Privacy

Current Proof-of-Stake implementations have a vulnerability not present in Proof-of-Work whereby they reveal the public key of staking addresses when they find and sign blocks. The most dangerous attack by quantum computers is against public key cryptography.

On traditional computers, it takes on the order of 2128 basic operations to get Bitcoin private keys associated with Bitcoin public keys. This number is so massively large that any attack using traditional computers is completely impractical. However, it is known for sure that it would take a sufficiently large quantum computer on the order of only 1283 basic quantum operations to be able to break a Bitcoin key using Shor’s algorithm. This might take some time, especially since the first quantum computers are likely to be extremely slow, but it is still very practical. It could be estimated that it is maybe 2 to 5 years until quantum computers become an issue, but any project that plans on staying relevant on a long period of time should tackle these vulnerabilities way before they become problematic.

It is worth mentioning that public keys are NOT public addresses. To reverse a private key from a public address, it would require more energy than what is available in the universe, therefore a quantum hacker cannot just go pick public addresses with large amounts and reverse those.

When a Particl block is staked from a cold staking node, the private key of the address on the staking node (which contains no coin) is broadcasted to the network instead of the private key of the address which contains the staking funds. Because cold staking nodes are able to sign staked blocks on behalf of any wallet, hot or cold, cold stakers can effectively remain anonymous and shielded from theoretical quantum computer attacks.