---
title: Scalability
subtitle: Particl's approach to scalability
slug: blockchain-scalability
weight: -10
tags:
  - bulletproofs
  - lightning
  - segwit
---

{{< toc >}}

## Native Segregated Witness (Segwit)

The Particl platform is the first blockchain in the industry to ever be deployed with a **native implementation of Segwit**.

This has the added benefit of making all transactions (including private ones) go through Segwit by default, resulting in **better scalability and cheaper transaction fees**.

Unlike forked Segwit implementations, 100% of Particl addresses are compatible with Segregated Witness.

Segwit grants additional features to the Particl platform such as transaction malleability vulnerability protection and block capacity increase, but its most notorious feature is that it renders Particl’s blockchain compatible with the Lightning Network.


## Bulletproofs

**RingCT** transactions are much heavier than regular transactions, meaning that as the number of RingCT transactions executed increases, so does the size of the blockchain. This can become a problem when the size of the blockchain becomes too big that most people start connecting on third-party nodes instead of their own. It is also highly impractical to store full nodes on personal computers when they are several GBs or even TBs.

One solution currently under development to increase the scalability of the RingCT privacy protocol is Bulletproofs, “a new, non-interactive zero-knowledge proof protocol with very short proofs and without a trusted setup”.

{{< hint info >}}
**This protocol is expected to reduce the RingCT and CT transaction sizes by around 80%** and as such, constitute a very important item in our scalability strategy.
{{< /hint >}}

Read the full [Bulletproofs whitepaper](https://eprint.iacr.org/2017/1066.pdf) co-authored by Benedikt Bunz, Jonathan Bootle, Dan Boneh, Andrew Poelstra, Pieter Wuille, and Greg Maxwell.


## Lightning Network

{{< hint info >}}
Lightning network for Particl is **not yet implemented**
{{< /hint >}}

The [Lightning Network](http://lightning.network/) is a decentralized payment channel protocol first proposed by Joseph Poon and Tadge Dryja in their [Lightning Network whitepaper](https://lightning.network/lightning-network-paper.pdf) and powered using smart-contract functionality in the blockchain to enable instant, near-zero fee payments across a network of participants.


### Instant Payments

Lightning-fast blockchain payments without worrying about block confirmation times. Security is enforced by blockchain smart-contracts without creating a on-blockchain transaction for individual payments. Payment speed measured in milliseconds to seconds.

### Scalability

Capable of millions to billions of transactions per second across the network. Capacity blows away legacy payment rails by many orders of magnitude. Attaching payment per action/click is now possible without custodians.

### Low Cost

By transacting and settling off-blockchain, the Lightning Network allows for exceptionally low fees, which allows for emerging use cases such as instant micropayments.

### Cross-Chain

Cross-chain atomic swaps can occur off-chain instantly with heterogeneous blockchain consensus rules. So long as the chains can support the same cryptographic hash function, it is possible to make transactions across blockchains without trust in 3rd party custodians.


## Data Storage Network (DSN)

{{< hint info >}}
Read more about Open Marketplace-related scalability with [Data Storage Network (DSN)](/learn/market/data-storage-network/)
{{< /hint >}}