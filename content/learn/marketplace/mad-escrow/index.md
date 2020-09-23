---
title: MAD Escrow
subtitle: About Particl Marketplace's 2-party escrow mechanism for resolving disputes
slug: 
weight: 2
tags:
  - market
  - MAD escrow
---

{{< toc >}}

## About MAD Escrow

Marketplaces usually have mechanisms in place to resolve disputes between buyers and vendors. This is a vital part of e-commerce because trusting strangers, especially when money is involved, has never proven to be reliable. As buyers and vendors do not know and trust each other, there has to be protection against one of the party never honoring their end of the trade.

One common solution marketplaces and payment processors use is a mutually-trusted third party (in other words, an escrow agent). On decentralized marketplaces, not only does this represents scalability and privacy issues but it also does not offer any protection against collusion between the escrow agent and one of the party.

{{< hint success >}}
**Particl's Open Marketplace solves this problem without the need for a third party.**\
It uses what is called MAD escrow smart-contracts. This type of escrow does not cost any fee, is infinitely scalable and private by design.
{{< /hint >}}

## Game Theory

{{< image class="side-thumb" src="particl-mad-escrow.jpeg" alt="Particl's MAD Escrow logo" >}}

[Mutually Assured Destruction](https://en.wikipedia.org/wiki/Mutual_assured_destruction) (MAD) is a [doctrine of military strategy](https://blogs.cornell.edu/info2040/2016/09/09/mutually-assured-destruction-game-theory-and-the-cold-war/) and national security policy in which a full-scale use of nuclear weapons by two or more opposing sides would cause the complete annihilation of both the attacker and the defender, thus making their use not an option.

It is based on the [theory of deterrence](https://en.wikipedia.org/wiki/Deterrence_theory), which holds that the threat of using strong weapons against the enemy prevents the enemy's use of those same weapons. The strategy is a form of Nash equilibrium in which, once armed, neither side has any incentive to initiate a conflict or to disarm.

**Particl’s MAD escrow mechanism replaces the nuclear annihilation deterrence factor of the [MAD game theory](https://en.wikipedia.org/wiki/Game_theory) for a mutual financial loss should one party acts dishonestly.**


## How does it work?

Particl uses the [BIP 65](https://github.com/bitcoin/bips/blob/master/bip-0065.mediawiki) `opcode`, which allows a transaction output to be made unspendable until some point in the future, to enable MAD escrow contracts. It locks funds in a secure multi-signature address until all the parties sign off on the transaction.

The seller starts by depositing an amount they want the buyer to match. The deposit can be between 0–100 % of the purchased item’s price.

However, optimal MAD odds are achieved when the security deposit equals 100 % of the item’s price. The buyer then deposits an equal amount plus the price of the item they are buying. This double security deposit symbolizes a virtual handshake between the buyer and the vendor.

**The escrowed funds are not released to any party until both confirm that the transaction has been completed satisfactorily.** To avoid filibustering, the MAD smart-contract has a timer that runs for a pre-determined duration of time. This can be extended if both parties agree. Once it runs out of time, the funds are locked forever. This prevents both parties from willingly delaying and hindering the escrow process.

When both parties are satisfied with the outcome of the transaction, they have to confirm the transaction as complete. **The payment is then released to the vendor and the security deposits are refunded to both parties at no fee.**


## Private by design

> Particl’s MAD escrow system renders the marketplace fully fungible. That's because all transactions are untraceable by default.

In fact, not only is all marketplace content encrypted, but all currency transactions are made untraceable through the use of the [RingCT](/learn/transaction-types/) privacy protocol. This technique enhances privacy much more than if CT MAD escrow was optional because it dramatically increases the number of private transactions on the network.

**Another privacy-enhancing aspect of the MAD escrow mechanism is its lack of third-party acting as escrow agent.** In fact, in most centralized escrow system, conversations between the buyer and the seller are available to the escrow agent. This is so the escrow agent can step in if any problem arises and issue a resolution based on the context. This puts a lot of power into the agent's hands and assumes it is acting in an honest way.

By not requiring any third-party, the Open Marketplace's escrow system preserves the privacy of both parties. Any transaction detail or conversation is only available to the transacting parties and no one else.


## Scalability

> This form of decentralized escrow is infinitely scalable. It doesn't need any other party other than the ones transacting to function.

This means there is no friction whatsoever, and that as many escrow transactions can be opened as required by the users. No staff is required, no data can be mined, and no delay can be caused by outside parties. The Particl network can support an infinite number of escrow deals at the same time.