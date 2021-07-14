---
title: "FAQ: PART coin"
subtitle: PART is the cryptocurrency designed to be the heart of the Particl ecosystem and acts as the fuel that makes it run
slug:
weight: 1
tags:
  - faq
---

{{< toc >}}

## What is PART?

It’s a technically advanced [privacy coin](/learn/privacy/transaction-types), a voting ticket, a [moderation token](/learn/marketplace/governance), a [source of passive income](/learn/staking/intro), and much more. It is multi-purpose.

## Can I store PART on a hardware wallet?

Yes, PART is officially supported by [Ledger wallet](/learn/wallets/hardware) with [cold staking capabilities](/learn/staking/intro#cold-staking) enabled. You can [set up your hardware Particl wallet](/tutorial/wallets/ledger) and start safely earning staking rewards.

Particl is also currently working on a [Trezor](/tutorial/wallets/trezor) integration.

## Where can I buy PART coins?

[You can buy PART coins on these exchanges](https://particl.io/part-exchanges)

### Will PART be added to other exchanges?

The Particl team is in constant discussion with many exchanges, however, the decision to list PART or not is entirely up to the exchanges themselves.

## What is PART's codebase?

PART is built on the [Bitcoin Core codebase](/learn/blockchain/bitcoin-codebase) and is **always kept up-to-date with Bitcoin's latest version** within days. Updating the codebase to the most recent version allows the platform to benefit from the latest security, performance and stability development made on the Bitcoin Core codebase as well as stay compatible and easy to integrate with the ever-evolving Bitcoin ecosystem.

## What are the transactions fees for PART?

The default fee for public transactions is 0.002 PART per kb but you can adjust the limit to your needs (higher fee = better confirmation times).

[Privacy transactions](/learn/privacy/transaction-types) (RingCT + Bulletproofs) default to around 0.005 PART per transaction, although that fee varies depending on the number of ring signatures (degree of privacy) used by the user when making a transaction.

## What are PART's transactions sizes?

|   | Size without Segwit & Bulletproofs  | With Segwit | With Bulletproofs |
|---|-------------------------------------|-------------|-------------------|
| Public                        | 255 B   | 202 B       | -                 |
| Confidential Transaction (CT) | 5,485 B | 2,865 B     | ~1,706 B          |
| RingCT (4 ring members)       | 5,723 B | 3,009 B     | ~1,949 B          |


## What is PART's inflation rate?

Current annual inflation of PART coins is 2 %. You can see historical rates below:

| Period | Staking rewards / inflation rate |
|--------|----------------------------------|
| July 2017 – July 2018               | 5 % |
| July 2018 – July 2019               | 4 % |
| July 2019 – July 2020               | 3 % |
| July 2020 onwards                   | 2 % |

## Why has PART different privacy states?

{{< hint info >}}
**Learn more** about [Transaction types](/learn/privacy/transaction-types)
{{< /hint >}}

  * Freedom of choice.
  * To keep the process of coin minting transparent and have a fully auditable supply. If a bug or exploit were to occur at the staking level, it would be instantly detected whereas with a 100% private chain, it could go unnoticed for an extended period of time.
  * To raise the probability and lower the technical barrier to get adopted by third-party services (easier to integrate).
  * As fees are higher for privacy transactions, some users might not want to execute private transactions if they do not require it.

## Are whitepapers available for the CT and RingCT privacy protocols?

While there is currently no whitepaper available as it relates to our own integration onto the Bitcoin Core codebase, there are whitepapers available for the original privacy protocols themselves:

* [Confidential Transactions (CT)](https://elementsproject.org/elements/confidential-transactions/investigation.html)
* [RingCT](https://eprint.iacr.org/2015/1098.pdf)

## Is Segwit enabled?

**Particl is natively integrated with Segwit**, meaning it has been activated since Block 1 and is enabled by default on all transactions. It is not possible to make non-Segwit transactions on Particl.

## What are atomic swaps?

[Atomic swaps](https://github.com/particl/atomicswap) are decentralized and trustless trade between two users of different cryptocurrencies. It makes trading cryptocurrencies without any third-party (i.e. trading exchange) and have blockchains directly interact between each other (i.e. cross-chain smart-contracts) possible.

## What is Particl's transaction-per-second (TPS) capabilities?

Calculating this metric is pretty hard as greatly depends on the ratio of public, blinded and anonymous transactions. Several other factors can impact the results such as smart-contracts and multisig address transactions.

In the end, a more accurate metric would be to calculate each transaction size. Regardless, it is still possible to calculate a very approximative estimate of Particl's TPS by assuming all transactions are either public or private, and by disregarding smart-contracts and multi-signatures. In reality, this metric is pretty innacurate, but interesting nonetheless if only to observe the purely coin-related theoretical performance of the blockchain:


|                                | Bitcoin        | Particl               |
|--------------------------------|----------------|-----------------------|
| Block Size                     | 1 MB           | 2 MB                  |
| Block Time                     | 10 min         | 2 min                 |
| TPS (100% public transactions) | ~7 (no Segwit) | ~85 (Default Segwit)  |
| TPS (100% RingCT transactions) | -              | ~8.80 (Default Segwit + Bulletproofs) |

(The ring signature is calculated with 4 ring members)

## Where can the debug logs be found?

### Particl Core

| OS              | Network   | Path
|-----------------|-----------|----------------------------------------------
| Linux           | mainnet   | `~/.particl/debug.log`
| Linux           | _testnet_ | `~/.particl/testnet/debug.log`
| Windows         | mainnet   | `C:\Users\{YourUserName}\Appdata\Roaming\Particl\debug.log`
| Windows         | _testnet_ | `C:\Users\{YourUserName}\Appdata\Roaming\Particl\testnet\debug.log`
| OSX             | mainnet   | `~/Library/Application Support/Particl/debug.log`
| OSX             | _testnet_ | `~/Library/Application Support/Particl/testnet/debug.log`


### Particl Desktop

| OS              | Network   | Path
|-----------------|-----------|----------------------------------------------
| Linux           | mainnet   | `~/.config/particl-desktop/application.log`
| Linux           | _testnet_ | `~/.config/particl-desktop-testnet/application.log`
| Windows         | mainnet   | `C:\Users\{YourUserName}\AppData\Roaming\Particl Desktop\application.log`


### Particl Market

| OS              | Network   | Path
|-----------------|-----------|----------------------------------------------
| Linux           | mainnet   | `~/.particl-market/market.log`
| Linux           | _testnet_ | `~/.particl-market/testnet/03/market.log`
| OSX             | mainnet   | `~/Library/Application Support/particl-market/market.log`
| Windows         | mainnet   | `%userprofile%\AppData\Roaming\particl-market\market.log`

