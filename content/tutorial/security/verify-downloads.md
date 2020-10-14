---
title: Verify integrity of downloads
subtitle: Validating downloads makes sure you have what the developers released – and not installing any fake or malware-infected software
slug: 
weight: 4
tags:
  - security
---

## About checksums

While compiling from source is the recommended and most secure way to build the Particl platform, the team realizes this is an advanced technique that a large number of users aren't comfortable with. For most users, each release is distributed with source code and pre-compiled distributions for Windows, Mac & Linux.

**To ensure the highest level of security, the Particl Project team provides `sha256sums` for all of these releases.**

Each checksum is a hash of the download file that verifies that nothing has been added or taken away either in-transit or by a third party. By using sha256 encryption with these sums every computer will generate the same hash unless the file has been compromised, which in response, will generate a different hash.

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

```
659567323348e7240642629ea6356ded7246589acb37d3d02f8eade3f2e2d15e
```
{{< /tab >}}

{{< tab "Linux" >}}
Most Linux distributions come with the `sha256sum` by default (beginner hint – only copy code after "$"):

1. Download latest Linux release from Github (replace “0.14.2.1” with current version number, if newer):

```
$ cd Downloads ~/Downloads
$ wget https://github.com/particl/particl-core/releases/download/v0.14.2.1/particl-0.14.2.1-x86_64-linux-gnu.tar.gz
```

2. Run `sha256sum` on downloaded file:

```
~/Downloads$ sha256sum particl-0.14.2.1-x86_64-linux-gnu.tar.gz
sha256sum hash result: 5545cb7f2364ab773f3228ea1f0283fd389cc2ea43a886eb27d114f96ac54762
```
{{< /tab >}}

{{< /tabs >}}


### Compare checksums

When you found out the hash of your downloaded file, visit release page of your downloaded [Particl wallet](/learn/wallets/overview) on Github:

- link to [Particl Desktop release page](https://github.com/particl/particl-desktop/releases)
- link to [Particl Core release page](https://github.com/particl/particl-core/releases)

Find the version you've downloaded and **compare the checksum on your PC with the one published on GitHub**.

**Ensure both checksums are identical before installing software!**

{{< hint alert >}}
**If the checksums aren't matching, you have a bad/malicious download and you shouldn't install the wallet!**\
If this happens, make absolutely sure, you're checking the right versions and correct variant for your OS. If you're in doubt, it's always better to [seek assistance in the community](/support/overview).
{{< /hint >}}
