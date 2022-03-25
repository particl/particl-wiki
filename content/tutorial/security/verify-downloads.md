---
title: Verify integrity of downloads
subtitle: Validating downloads makes sure you have what the developers released – and not installing any fake or malware-infected software
slug: 
weight: 4
tags:
  - security
aliases:
  - /tutorial/verify-downloads
---

## About checksums

While compiling from source is the recommended and most secure way to build the Particl platform, the team realizes this is an advanced technique that a large number of users aren't comfortable with. For most users, each release is distributed with source code and pre-compiled distributions for Windows, Mac & Linux.

For Particl Core, the latest release can be found here: https://github.com/particl/particl-core/releases/latest

For Particl Desktop, the latest release can be found here: https://github.com/particl/particl-desktop/releases/latest

For Particl Electrum, the latest release can be found here: https://github.com/particl/particl-electrum/releases/latest


**To ensure the highest level of security, the Particl Project team provides `sha256sums` for all of these releases.**

You should generate the sha256sum of your downloaded file, and make sure it matches with the sha256 hashes listed on the corresponding release pages above.

{{< hint alert >}}
**It is recommended to always validate** the Particl build releases with the provided sha256sums.
{{< /hint >}}


## Validating checksums

{{< tabs "checksums" >}}

{{< tab "Web-based (Windows etc.)" >}}
There are a number of hash generators online, this tutorial will highlight Hash Online Convert:

1. Download preferred [Particl release from GitHub](https://github.com/particl/particl-core/releases/latest) e.g. Windows client
2. Visit [Hash Online Convert](http://hash.online-convert.com/sha256-generator)
3. Find **Or upload and generate a SHA-256 checksum of a file:** section
4. Select **Choose File** button
5. Find downloaded Particl release file
6. Select **Open** button
7. Select **Convert file** button
8. Hash converter: File gets submitted to the website and loads a new page showing _"Your hash has been successfully generated."_ This page shows the hash of the uploaded file in a variety of hash outputs; hex, HEX, h:e:x & base64 – **value to look for: hex**


Or, you can manually genearate the sha256 checksum in terminal.

1. Open terminal.
2. Type in:

```
certUtil -hashfile C:\Users\<your username>\Downloads\<file name of downloaded Particl Release> SHA256
```

{{< /tab >}}

{{< tab "Linux" >}}
Most Linux distributions come with the `sha256sum` by default


Generate the sha256sum in terminal:

```
cd /home/<your username>/Downloads

sha256sum <file name of downloaded Particl Release>
```

{{< /tab >}}

{{< tab "Mac" >}}

1. Open terminal
2. type in: 

```
shasum -a 256 
```

(with a space after the 6) then drag the file from your downloads folder into terminal, and it will write the file path for you, so you do not have to.

Alternately, you can write:

```
cd /Users/<your username>/Downloads

shasum -a 256 <file name of downloaded Particl Release>
```

{{< /tabs >}}


### Compare checksums

When you found out the hash of your downloaded file, visit release page of your downloaded [Particl wallet](/learn/wallets/overview) on Github:

- link to [Particl Desktop release page](https://github.com/particl/particl-desktop/releases/latest)

- link to [Particl Core release page](https://github.com/particl/particl-core/releases/latest)

Find the version you've downloaded and **compare the checksum on your computer with the one published on GitHub**.


**Ensure both checksums are identical before installing software!**

{{< hint alert >}}
**If the checksums aren't matching, you have a bad/malicious download and you shouldn't install the wallet!**\
If this happens, make absolutely sure you're checking the right versions and correct variant for your OS. If you're in doubt, it's always better to [seek assistance in the community](/support/overview).  If you are unsure, do **not** install the wallet.
{{< /hint >}}


## Checking PGP Signed Hashes

Technically, there is a possibility that the hashes you are viewing on the release page, are not the real hashes.

Instead, they could be hashes of a malicious version of the download, so if you were to check the hash of your malicious download, it would seem okay.

This could be because you are victim of a man in the middle attack, or perhaps you clicked a malicious link that was sent to you to get to the release pages.

{{< hint alert >}}
**Do not click on download links sent to you in discord or other chat rooms**
{{< /hint >}}

For your Particl Core download, there is an additional step you can take to ensure you are checking the actual hashes.

This is not yet available for Particl Desktop.

1. Go here: https://github.com/particl/particl-core/blob/master/contrib/builder-keys/keys.txt#L55 to download tecnovert's pgp key.
2. Copy his fingerprint (8E517DC12EC1CC37F6423A8A13F13651C9CF0D6B) into a public pgp keyserver of your choosing.
3. You can search for one, or visit https://pgp.mit.edu
4. Search for tecnovert's full key by copying and pasting his fingerprint into the search box

{{< hint alert >}}
you need to add a "0x" in front of his fingerprint when searching on the keyserver
So paste in "0x8E517DC12EC1CC37F6423A8A13F13651C9CF0D6B"
{{< /hint >}}

Click on the key ID that pops up "C9CF0D6B" (this matches the end of his fingerprint), and that will take you to his full key.

Copy/import this full public key into the pgp software of your choice.

For Windows, it is recommended to use: https://gpg4win.org

For Linux, most versions come with gpg installed

For Mac, it is recommended to use: https://gpgtools.org


Now, head to https://github.com/particl/gitian.sigs and find the file name that matches the Particl Core version number and operating system you've downloaded for.

Click that file name.

Download the build.assert file and the build.assert.sig file (you can do this by right clicking and hitting save link as)


In your gpg software, verify that the build.assert is correctly signed by the build.assert.sig file.  If you are unfamiliar with pgp, instructions on how to do so can be found on the corresponding website of the pgp software you have downloaded.

{{< hint alert >}}
As long as the result says signature is good, you are okay.  It may say untrusted signature, this is because you have not set the trust level of tecnovert's public key, that is okay.  If the result says invalid signature, that means you have downloaded a malicious file.  Delete the downloaded files, clear history/cookies on your browser, and re-download.  If the problem persists, contact a community member.
{{< /hint >}}

Now that you have verified tecnovert has signed the build.assert file, you can trust it!

1. Open up the build.assert file and you will see a list of hashes at the top.
2. Check the hash for your corresponding operating system/downloaded version of Particl Core.
3. This hash should match the one listed on https://github.com/particl/particl-core/releases/latest and the sha256 hash you calculated on your downloaded file.

Now you are certain you are viewing the correct hashes, because they are signed by tecnovert's pgp key, and your file is not malicious because it matches those hashes!
