---
title: Voting on Proposals
subtitle: You can vote on CCS proposals using Particl’s on-chain voting system
slug: 
weight: 5
tags:
  - governance
  - voting
  - community
---

Voting on proposals requires you to hold Particl coins and to be actively staking on the network. If you’re voting, every block you stake within a particular voting period will register a vote.

{{< hint info >}}
**What are Proposals and CCS?**\
Learn more in **[Learn -> Proposals](/learn/misc/proposals/)** article!
{{< /hint >}}


## How to vote

To vote, first find the proposal you want to vote for on the CCS. Note down its [proposal ID](https://ccs.particl.io/), the number of the block at which the voting period starts, the number of the block at which the voting period ends, and the value associated with your voting preference (i.e. 1 = “Voting for the proposal”).

Once that is done, follow the instructions below, depending on what client you use to stake your coins on the network.


{{< tabs "how-to-vote" >}}
{{< tab "Partyman" >}}

### Partyman (Cold Staking Application)

1. Access your [Partyman](/learn/staking/partyman/) staking node and make sure it's on the latest version by typing the following command from inside the Partyman folder:

```
git pull
```

2. Enter your home folder: `cd ~/`
3. Find what proposal you want to vote for by entering the following command:

```
partyman/partyman proposal list
```

4. Vote on the proposal by typing the following command:

```
partyman/partyman proposal vote
```

5. Confirm that you want to vote for a proposal. This will clear all previous voting preferences if you’re already voting on a proposal.
6. Enter the ID of the proposal you want to vote for and press `Enter`
7. Enter the voting option you want to cast your vote for and press `Enter`

That is all! Every time you stake a block until the voting period ends, you’ll cast a vote. The system will tally the votes at the end of the voting period to determine the end result.

{{< /tab >}}
{{< tab "Particl Desktop" >}}

### Particl Desktop

1. Open your [Particl Desktop](/tutorial/wallets/particl-desktop/) client
2. Click on the debug console icon at the top right corner of the screen
3. In the console window, type the following command:

```
setvote proposal option height_start height_end
```

- `proposal` should be the ID of the proposal you want to vote for
- `option` should be the value of your voting option (i.e. 1 = “Voting for the proposal”)
- `height_start` is the block number when the voting period starts
- `height_end` is when it ends

In the end, the command should look similar to this, with different values depending on the proposal and your voting preferences:

```
setvote 1 1 300000 305040
```

In this example, you would be voting for Proposal ID number 1, with the voting option 1, and do so from block 300,000 to 305,040. 

That is all! Every time you stake a block until the voting period ends, you’ll cast a vote. The system will tally the votes at the end of the voting period to determine the end result.

{{< /tab >}}
{{< tab "Particl Core" >}}

### Particl Core

1. Open your [Particl Core](/tutorial/wallets/particl-core/) client
2. Click on the Window tab at the top of the client and then go to “Console”
3. In the console window, make sure that the wallet with your coins staking is selected in the dropdown menu. If you don’t select the wallet that is staking your coins, your vote will not register.
Enter the following command to register your vote:

```
setvote proposal option height_start height_end
```

- `proposal` should be the ID of the proposal you want to vote for
- `option` should be the value of your voting option (i.e. 1 = “Voting for the proposal”)
- `height_start` is the block number when the voting period starts
- `height_end` is when it ends

In the end, the command should look similar to this, with different values depending on the proposal and your voting preferences:

```
setvote 1 1 300000 305040
```

In this example, you would be voting for Proposal ID number 1, with the voting option 1, and do so from block 300,000 to 305,040. 

That is all! Every time you stake a block until the voting period ends, you’ll cast a vote. The system will tally the votes at the end of the voting period to determine the end result.

{{< /tab >}}
{{< /tabs >}}



## Tally Votes

To see the current results of a particular proposal, you can tally the votes. That can be done during or after a voting period.

{{< tabs "tally-votes" >}}
{{< tab "Partyman" >}}

### Partyman

1. Access your [Partyman](/learn/staking/partyman/) staking node
2. Enter your home folder: `cd ~/`
3. Find what proposal you want to tally the votes of by entering the following command:

```
partyman/partyman proposal list
```

4. Tally the proposal’s votes by typing the following command:

```
partyman/partyman proposal tally
```

5. Enter the ID of the proposal you want to tally the votes and press `Enter`.

{{< /tab >}}
{{< tab "Particl Desktop" >}}

### Particl Desktop

1. Open your [Particl Desktop](/tutorial/wallets/particl-desktop/) client
2. Click on the debug console icon at the top right corner of the screen
3. In the console window, type the following command:

```
tallyvotes proposal height_start height_end
```

- `proposal` should be the ID of the proposal you want to vote for
- `height_start` is the block number when the voting period starts
- `height_end is when it ends

{{< /tab >}}
{{< tab "Particl Core" >}}

### Particl Core

1. Open your [Particl Core](/tutorial/wallets/particl-core/) client
2. Click on the Window tab at the top of the client and then go to “Console”
3. In the console window, type the following command:

```
tallyvotes proposal height_start height_end
```

- `proposal` should be the ID of the proposal you want to vote for
- `height_start` is the block number when the voting period starts
- `height_end is when it ends

{{< /tab >}}
{{< /tabs >}}
