---
title: Currency agnosticism
subtitle: Particl's vision is not one of tribalism – fact, the Open Marketplace is designed in such a way that almost any coin can be easily integrated as a form of payment
slug: 
weight: 6
tags:
  - market
  - atomic swaps
  - bitcoin
---

{{< toc >}}

## What's currency agnosticism?

That means buyers aren't limited to using the PART coin as a form of payment. They are able to use many currencies, including Bitcoin, among others. This provides a use-case for many different coins and gives them a fee-less and untraceable way to spend their cryptocurrencies **without having to either go through a third-party or sell their coins for fiat on exchanges**.

It's important to note that, even though many coins can be used as a form of payment, all non-PART transactions are automatically converted into PART transactions by the marketplace. This is because the escrow smart-contract needs to use PART in order to operate. The PART coin is also required for the escrow mechanism to execute transactions anonymously (it uses PART's [CT and RingCT privacy protocols](/learn/transaction-types/)).

The integration of other coins can be achieved in two ways:


## Atomic Swaps

**[Atomic swaps](https://github.com/particl/atomicswap) are decentralized and trustless trades between two users of different cryptocurrencies.**

They involve each party paying into a contract transaction, one contract for each blockchain. The contracts contain an output that is spendable by either party, but the rules required for redemption are different for each party involved.

One party (called counterparty 1 or the initiator) generates a secret key and sends the intended trade amount into a smart-contract. The second party (called counterparty 2 or the participant) can only redeem the funds by knowing the secret key. If a pre-determined period of time (typically 48 hours) expires after the smart-contract transaction has been mined or staked and the funds have not been redeemed by the participant, the funds can be refunded back to the initiator's wallet.

For simplicity, we assume the initiator wishes to trade Particl for Decred with the participant. The initiator can also trade Decred for Particl and the steps will be the same, but with each step performed on the other blockchain. At this point, the participant is unable to claim the funds from the initiator's Particl smart-contract because the secret key is unknown by them. If the initiator revealed their secret key at this moment, the participant could claim the funds from the contract without ever honoring their end of the trade, leaving the initiator at a loss.

To avoid this, the participant creates a similar smart-contract but on the Decred blockchain and sends the intended Decred amount into it. However, for the initiator to redeem the output, their own secret key must be revealed to the participant. For the participant to create their smart-contract, the initiator must reveal not the secret key (since the participant could stil claim funds and not honor their end of the deal), but a cryptographic hash of the secret key to the participant so that the smart-contract can be properly deployed. The participant's contract can equally be refunded after a pre-determined period of time.

The initiator then redeems the participant's Decred funds by revealing the secret key to the participant’s smart-contract. The secret key is then extracted from the initiator's redeeming Decred transaction providing the participant with the ability to redeem the initiator's Particl contract.

This procedure is atomic (with timeout) as it gives each party a set period of time to redeem their coins on the other blockchain before a refund can be performed. This is the best option for people requiring privacy, and is also probably going to be the cheapest to use.


## Third-Party Integrations

{{< image class="side-thumb" src="particl-swap-app.png" alt="Preview of built-in Swap app in Particl Desktop 3.0" >}}

Using the very flexible and modular Particl Desktop wallet, third-parties can easily be integrated to enhance the user experience and provide optional services. One such example is the **integration of non-custodial exchanges such as SimpleSwap, StealthEx or Changelly**.

While not as private and cheap as atomic swaps, third-party services do offer some benefits. Liquidity and volume, at this point in time, can be much better on centralized exchanges. Some of these services (i.e. SimpleSwap, StealthEx, Changelly) also offer fiat options and pairs. This would allow the Open Marketplace to offer in-wallet fiat payment options.

Particl will always prioritize decentralized solutions over ones that introduce third-parties. However, payment options need to have volume and liquidity for them to be efficient and cost-effective for the user.