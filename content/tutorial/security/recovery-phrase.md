---
title: Securely storing Recovery Phrases
subtitle: Properly storing and securing your Recovery Passphrases is paramount to every crypto holder – learn some best practices
slug: 
weight: 1
tags:
  - security
  - important
---

Recovery Phrases (sometimes also called Mnemonic or just Seed) are strings of usually 12, 18 or 24 words, which are used to recover crypto wallets in cases of emergency. That being said, whoever gets access to your Recovery Phrase can access your coins as well. This presents a security risk if your Recovery Phrase gets stolen or discovered by some malicious actor.

## Finding the right balance

Each security layer used to protect your Recovery Phrase (and optionally Recovery Passphrase) makes it harder for everyone to get access to your coins – that includes both attackers and yourself. Browsing crypto Reddit communities, you can read almost each day about people thinking of such advanced and apparently ultra-secure mechanisms to protect their seeds, that they themselves got locked out of it in the end.

Storing your Recovery Phrase is about finding the right balance between security and convenience, considering all the different attack vectors that will apply to you etc.


### ✅ DO's

- make sure your seed is **protected against most/all elements** (fire, water, theft etc.) – nice way of achieveing this is via [metal seed storages](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-part-ii-d309e04aefeb) that are widely available on the market
- **have redundant backups** (at least two) **on different locations** – however keep in mind that with each new location and redundant backup, you also increase attack vector as attacker has a higher chance of finding at least one of them
- when possible, use **[Recovery Passphrase](/tutorial/security/good-passwords)** as well – they act as "another word" in your Recovery Phrase – so if your backup gets stolen, attacker won't get to your coins in case they don't know the Recovery Passphrase as well
- when using Recovery Passphrases, don't keep their backups together with Recovery Phrases (that would completely defeat its purpose)

### Consider using

- **[hardware wallets](/learn/wallets/hardware)** are great at keeping you much safer against digital attacks (malware-infected computers etc.)
- **multisignature wallets** when/if possible – then getting access to one of the wallets isn't enough, attacker would need to obtain multiple wallets at once to move your funds (note: [Particl Copay](/tutorial/wallets/particl-copay) wallet supports multisig)

### ❌ DON'Ts

- **don't store seeds digitally** (text files, screenshots etc.)
- **don't backup them to cloud** – same as previous point, but repeated for emphasis – seriously, don't backup your seeds to Google Drive, OneDrive etc.
- don't share them with anyone


## Keep in mind

> This will get a bit dark, but it's neccessary.

Making sure unauthorized persons don't access your crypto is only the first part of the journey. Don't forget, that ["Cryptocurrencies live forever. You won't."](https://www.youtube.com/watch?v=2XsoH4Okr_M) – make sure your loved ones _could_ access your coins if something happened to you. You don't need to exactly die, but it will help you even in case of some big accident – your memory might go "poof" and along with it your only memorized Recovery Passphrase. And there goes your holdings.


## Learn more

- **[Review & comparison of different metal seed storages](https://medium.com/@lopp/metal-bitcoin-seed-storage-stress-test-part-ii-d309e04aefeb)** (Part II) – incl. Blockplate 2.0, Blockstream Metal, Coldbit Passphrase, Coldbit Steel, Cold Storage Coins, CryptoTag, CryptoVault, The HODL wallet, Keyois Capsule, SeedSteel, Simbit, Steeldisk and Steelwallet
- **[Cryptocurrencies live forever; you won't](https://www.youtube.com/watch?v=2XsoH4Okr_M)** – great talk by Pamela Morgan from HCPP17