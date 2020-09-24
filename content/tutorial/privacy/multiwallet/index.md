---
title: Running multiple wallets
subtitle: Separate your funds into multiple wallets, for different purposes
slug: multiwallet
weight: 1
tags:
  - multiwallet
  - privacy
---

{{< toc >}}

You might want to create and use multiple wallets for different usage. The goal is to separate your finances, so they won't mix up. This approach will also help you gain a bit [more privacy](/tutorial/privacy/tips/) (never linking all of your available funds).


## Multiwallet setup

### Particl Desktop

{{< image class="side-thumb" src="multiwallet-particl-desktop.png" alt="Wallet switcher in Particl Desktop 3.0" >}}

Multiwallet functionality for [Particl Desktop](/tutorial/wallets/particl-desktop/) is baked into the wallet itself (and very user-friendly).

All you need to do is to click _New wallet_ in the wallet switcher in the left sidebar to add (or restore) a new wallet. After your new wallet is set up, you can easily switch between wallet in the same wallet switcher, without the need to restart the wallet.


### Particl Core

Same as on Bitcoin core wallet, launching multiple wallets on [Particl Core](/tutorial/wallets/particl-core/) is as easy as adding few `-wallet=` parameters - depending on your setup and location of your wallet files.

For example, if your wallets are in these locations:

```
.particl/
    primary-wallet.dat
    market/
        wallet.dat
    savings/
        wallet.dat
```

You would use these parameters:

```
$ particl-qt -wallet=primary-wallet.dat -wallet=market -wallet=savings
```

{{< image class="side-thumb" src="multiwallet-particl-qt.png" alt="Wallet switcher in Particl Core" >}}

Notice that for the `primary-wallet.dat` in the root folder, we added `.dat` to the parameter, which tells Particl Core that it's directly a wallet file, not its folder (as in case of `market/wallet.dat` and `savings/wallet.dat`).

This will open one Particl Core client with all 3 wallets loaded. You can then easily switch between them by choosing active wallet from the new dropdown (see screenshot).


## Autostart multiwallet

### Particl Desktop

{{< hint info >}}
**Particl Desktop launches with all available wallets loaded by default.**\
Therefore no extra configuration or setup is needed.
{{< /hint >}}

### Particl Core

#### Linux

Create a new custom application launcher in `~/.local/share/applications`:

```
$ nano ~/.local/share/applications/"Particl Core".desktop
```

Then paste and edit these lines (mainly `Exec=`) to match your setup:

```
#!/usr/bin/env xdg-open

[Desktop Entry]
Encoding=UTF-8
Name=Particl Core
GenericName=Particl Core
Comment=PART Wallet
Exec=/home/xxxxxx/particl/bin/particl-qt -wallet=xxxxxx.dat -wallet=xxxxxx
Terminal=false
Icon=particl
Keywords=Finance
Type=Application
Categories=Others
Name[en_US]=Particl Core
```

Save the changes via `CTRL-X` and then `Y`, confirm with `Enter`.