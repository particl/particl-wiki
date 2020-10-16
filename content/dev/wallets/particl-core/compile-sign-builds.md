---
title: Compile & Sign Particl Core builds
subtitle: How to compile own Particl Core builds via Gitian and sign them with PGP
slug:
weight: 1
tags:
  - dev
  - Particl Core
---

This guide will walk you through compiling your own Particl Core builds via Gitian and optionally signing the builds with your PGP key and uploading the signatures to [particl/gitian.sigs](https://github.com/particl/gitian.sigs) repository.

{{< hint warning >}}
**The more people would compile their builds and sign them, the better.**\
If you can spare the time and processing power, please do!
{{< /hint >}}

{{< toc >}}

## Notes

- **This guide is focused on Ubuntu-based distros** - on other distributions, you might to install more dependencies etc. (also tweak the commands accordingly)
- **Be patient** - the builds can take up to few hours (about 3-4 hrs on systems we tested on) - luckily you can still use your PC for other things in the meantime
- **For PGP signing of Gitian builds**
  - make sure the PGP key you're using is not protected by a passphrase - if it is, signing will fail
  - you'll need to submit a PR to [particl-core/contrib/gitian-keys](https://github.com/particl/particl-core/edit/master/contrib/gitian-keys/keys.txt) with your PGP key, so that others can verify your signatures

## Preparation

{{< hint info >}}
**All these instructions in this "Preparation" section need to be run only once per machine.** After you have it all set up (and perhaps want to compile the next version), just skip ahead to "Compile" section.
{{< /hint >}}

Before we begin, we should make sure that `lxc-start` and `execute` and use `sudo` without a password (otherwise you'll need to enter your root password few times during the compilation, which would further prolong the whole process):

```bash
sudo -s
echo "%sudo ALL=NOPASSWD: /usr/bin/lxc-start" > /etc/sudoers.d/gitian-lxc
echo "%sudo ALL=NOPASSWD: /usr/bin/lxc-execute" >> /etc/sudoers.d/gitian-lxc
```

Install dependencies:

```bash
$ sudo apt-get install git curl wget
```

Grab the latest Particl Core code and gitian-builder from Github:

```bash
$ mkdir ~/gitian
$ cd ~/gitian
$ git clone https://github.com/particl/particl-core.git
$ cp particl-core/contrib/gitian-build.py .
$ git clone https://github.com/devrandom/gitian-builder.git
```

We need to add some extra space to our `lxc` image:

```bash
$ sed -i -- 's^10240^16000^g' gitian-builder/bin/make-base-vm
$ sed -i -- 's^12287^16000^g' gitian-builder/bin/make-base-vm
```

Get the macOS SDK for the ability to compile macOS builds as well:

```bash
$ mkdir gitian-builder/inputs
$ cd gitian-builder/inputs
$ wget https://bitcoincore.org/depends-sources/sdks/MacOSX10.11.sdk.tar.gz
$ cd ~/gitian
```

{{< hint warning >}}
**At this point, you'll need your PGP key. As mentioned in the Notes above, you'll need a key without a passphrase.** If you don't have one, [generate a new PGP key](https://help.github.com/en/articles/generating-a-new-gpg-key) now.
{{< /hint >}}

In the next step, replace `KEYNAME` by name of your key.

{{< hint info >}}
If you're not sure about its name, check your PGP keys and locate the one you want to use (in this example, the name is represented as `KEYNAME`):

```bash
$ gpg --list-secret-keys
/home/user/.gnupg/pubring.kbx
-------------------------------
sec   rsa4096 XXXX-XX-XX [SCA] [expires: XXXX-XX-XX]
      XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
uid           [ultimate] KEYNAME <email@example.com>
ssb   rsa4096 XXXX-XX-XX [E] [expires: XXXX-XX-XX]

```
{{< /hint >}}

Prepare the build process (replace `KEYNAME` by the key's name and `VERSION` by latest Particl Core version):

```bash
$ ./gitian-build.py --setup KEYNAME VERSION
# for example: $ ./gitian-build.py --setup allienworks 0.18.1.3

$ cd ~/gitian
```

Check `ifconfig` - if you see a `lxcbr0` interface, you'll need to rename it to `br0`. If you can locate `br0` right away, you're all good and can skip this step:

```bash
$ ifconfig

# if you see lxcbr0, then:
$ sudo sed -i s/lxcbr0/br0/ /etc/default/lxc-net
```

Congratulations, that concludes all the one-time preparations. Onwards to compilation!

## Compile

{{< hint info >}}
**Once you did the Preparation part of this guide, all you need to do from that point on is the compilation**. Even with new releases in the future, you just need to run this compile command, nothing else.
{{< /hint >}}

Running the build accepts quite a lot of parameters:

- again replace `KEYNAME` by name of your key
- replace `VERSION` by the version you want to compile
- `-j` - number of threads used for compilation (e.g. if you have 8 threads on your CPU, you can safely use `-j 7`)
- `-m` - allocated memory in MB (e.g. allocate 10 GB by `-m 10000`)

```bash
$ /usr/bin/time ./gitian-build.py --no-commit -j 5 -m 5000 -b KEYNAME VERSION
# for example: $ /usr/bin/time ./gitian-build.py --no-commit -j 5 -m 5000 -b allienworks 0.18.1.3
```

### Check progress

Once you hit Enter, the compilation will begin. You can check its status by running:

```bash
$ tail -f ~/gitian/gitian-builder/var/install.log
# and then
$ tail -f ~/gitian/gitian-builder/var/build.log
```

Linux builds will be first, followed by Windows and then macOS. Linux takes the most time (about half of the whole compilation process), so be patient.

### Post-compilation

After couple hours, when the compilations is done, you can find a new folder `~/gitian/particl-binaries/<VERSION>` with all the builds in it.

If the **PGP signing** was successfull, you should see signatures of the builds signed by your PGP key in `~/gitian/gitian.sigs/<VERSION>-<ARCH>/<KEYNAME>/`. Commit the changes (= addition of your signatures) and submit a PR to [particl/gitian.sigs](https://github.com/particl/gitian.sigs).
