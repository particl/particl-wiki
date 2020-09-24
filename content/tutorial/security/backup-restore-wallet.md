---
title: Backup & Restore wallet
subtitle: Using wallet.dat to completely backup and restore your wallet
slug:
weight: 2
tags:
  - security
  - important
---

Your funds are backed up by [Recovery Phrase](/tutorial/security/recovery-phrase) (~ mnemonic seed) during wallet creation and that is enough to keep your coins safe. However if you want to backup all the additional data like addresses saved in Address Book and more, you'll need to backup your `wallet.dat` file.

{{< hint warning >}}
**Always backup your `wallet.dat` to a secure place** (USB, external drive etc.) – if anyone would get access to it and knew your wallet password, they could steal your coins! That is the main reason to encrypt your wallet right after you created one.
{{< /hint >}}

Keep in mind that this backup approach only saves data created up to that point. All data created after backup was made won't be included in the backup. You should backup your `wallet.dat` file periodically.


## Manual back-up

{{< hint info >}}
With [Particl Core](/tutorial/wallets/particl-core/), you can easily backup your `wallet.dat` file via _File_ → _Backup wallet..._
{{< /hint >}}

  1. close your wallet (if running)
  2. manually locate your `wallet.dat` file on disk (see below)
  3. copy the file to a safe and secure place manually (do not move – copy!)

When making backups, it's sane to name the backup files properly, e.g. including wallet name/type and date, like `part-wallet-personal_2019-06-03.dat`. This will help you greatly later, when you'll have many backup files.


### Where is wallet.dat?

Look in these folders (depending on your OS):

| OS                       | Path to directory                       |
|--------------------------|-----------------------------------------|
| {{< ico win >}} Windows  | `%AppData%\Particl`                     |
| {{< ico apple >}} macOS  | `~/Library/Application Support/Particl` |
| {{< ico linux >}} Linux  | `~/.particl`                            |

You should look for either a file called `wallet.dat` or a folder called `wallet` (or something else, if you chose a custom wallet name when creating it), in which you should find the `wallet.dat` file.


## Restoring existing wallet

Restoring from your `wallet.dat` file is the same as doing manual backups, only in reverse:

  1. close your wallet (if running)
  2. copy your backed up `wallet.dat` file to a correct folder depending on your OS
  3. rename the file to its original name (e.g. if you renamed `wallet.dat` to `personal-wallet_2019-06-03.dat`, rename it back to `wallet.dat`, otherwise it won't be recognized)
  4. launch your wallet again and unlock it with your wallet password