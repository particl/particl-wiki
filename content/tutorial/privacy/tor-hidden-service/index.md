---
title: Particl as Tor Onion Service
subtitle: Tor onion service conceals your IP address and thus your privacy 
slug: tor-hidden-service
geekdocHidden: true
weight: 3
tags:
  - tor
  - privacy
---

{{< toc >}}

It also protects your machine from geolocation and its possible ugly consequences, and automatically sets you up for both incoming and outgoing connections, helping the Particl network. It is recommended to **always run the Particl through Tor**.

{{< hint >}}
This guide is written purely for Linux (specificaly Ubuntu-based distributions).
{{< /hint >}}


## Download Particl wallet

If you don't have a Particl wallet yet, [download it](learn:wallets:) (we highly recommend [verifying wallet checksums](tutorial:verify-downloads) before installing) and then install it.


## Install Tor

At a command prompt just enter `tor`.

    $ tor

If it is already running, you should get an error message that says something like “Is tor already running?” That's good if you do.

If not, install Tor with these commands:

    $ sudo apt-get install tor


## Define Onion Service in Tor config

    $ sudo nano /etc/tor/torrc

We need to add our config to the Tor configuration file which will signal Tor to create a hidden service.

    HiddenServiceDir /var/lib/tor/particl-service/
    HiddenServicePort 51738 127.0.0.1:51738

Save the file with `CTRL-X`, type `y` to overwrite and confim by `Enter` – the text editor will exit.

    $ sudo service tor restart


## Find your IP for Onion Service

At a command prompt enter:

    $ sudo cat /var/lib/tor/particl-service/hostname

It should return an .onion address, which we'll refer to as `[yourexternalip].onion`

{{< hint info >}}
It is recommended to always run the Particl build releases through Tor.
{{< /hint >}}


## Modify particl.conf

In the [.particl directory](/tutorial/security/backup-restore-wallet/) there will be a `particl.conf` file. The wallet can run without that but you can include a lot of startup and operating instructions with it.

    $ nano ~/.particl/particl.conf

{{< hint info >}}

**If nano returns the following error:**

    Error writing ~/.particl/particl.conf: No such file or directory

Then you'll have the make the directory yourself (because the Particl wallet hasn't ever ran on the system yet)!

    $ mkdir ~/.particl
    $ nano ~/.particl/particl.conf

{{< /hint >}}

Your `particl.conf` file will need to contain at least the following. Replace `[yourexternalip].onion` with the onion domain you got from step 3!

```
externalip=[yourexternalip].onion
onion=127.0.0.1:9050
addnode=7vusex6gv5eerqi2.onion
addnode=quf7tm4gk3xn3aee.onion
addnode=46fvsrrq75dx5vq4.onion
addnode=ciikdjtoop7l6p6h.onion
addnode=frlfghlielxq2ncy.onion
addnode=partusq5qad6jd2c.onion
addnode=x6fxdwpq2krxzmr3.onion
addnode=amu2ck7lyw26fiqs.onion
addnode=kfyopkn3shigcneh.onion
onlynet=onion
listen=1
bind=127.0.0.1:51738
maxconnections=30
```

## Start wallet

Now you're ready to go, start it up. You should start making connections. If you use the `getpeerinfo` command you'll see the addresses of the peers and they should all be _.onion_ addresses. Some of the peers will show your external IP .onion address and that's normal, those are incoming connections.
