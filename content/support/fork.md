---
title: Chain forks
subtitle: Trouble syncing after hardfork with seemingly lost coins? Don't worry!
slug:
weight: 3
tags:
  - support
---

If you're experiencing that [Particl Desktop](/tutorial/wallets/particl-desktop/) or [Particl Core](/tutorial/wallets/particl-core/) wallet is not syncing any further, then it might be because you got caught on a fork due to the latest hardfork.

If you execute any transaction during this time, it will appear as if you've lost the coins, but don't worry. Nothing has left your wallet.


## Getting on the right chain

Getting your client back to a working state requires a bit of work.

### 1. Update to the latest version of the wallet

Updating to the [latest version](https://particl.io/downloads) will ensure that you have the latest list of "checkpoints".
These checkpoints are known blockhashes of the correct chain, which help guide the client guide itself to the right fork.

### 2. List all banned nodes and clear them

Sometimes the client will ban others nodes for misbehaving. It might be that your client has banned all legitimate nodes because you were on an older version. Open up the debug console and check whether you have any banned peers by `listbanned`. If that's the case, consider clearing the list by executing `clearbanned`.

### 3. Wait a few minutes

Sometimes the client will detect that it has made a mistake and will automatically get itself back on track.

### 4. Find out where your client got stuck

Open up the debug console in Particl Desktop or Particl Core and execute the following command `getchaintips`. Look for any chains that are marked `invalid`. Get the corresponding `hash` of that chain and execute: `reconsiderblock HASH_HERE`, where `HASH_HERE` is value that was returned previously.

### 5. Make sure you're fully synced

Take a look at the [block explorer](https://explorer.particl.io/) and verify that your client is syncing to the latest height indicated there. `getblockchaininfo` will return the height to which you're synced. You might have to repeat step 4 again. 