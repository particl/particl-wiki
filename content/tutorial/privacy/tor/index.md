---
title: Particl with Tor
subtitle: Anonymize your IP address with Tor when using Particl Desktop and/or Open Marketplace
slug: 
weight: 1
tags:
  - tor
  - privacy
---

{{< toc >}}

The only privacy protocol that’s not enabled by default on Particl Desktop is the ability to hide your IP address using the Tor network.

While it could eventually be enabled by default or through the Settings page, Tor currently needs to be activated manually to route your Particl Desktop connection through its network. Don’t worry, it’s not complicated at all and will only take you a few minutes.

There are currently 3 ways of using Particl Desktop through Tor network. Choose the one that fits you best:


## a) Using the Tor Browser

The easiest way to enable the Tor network on Particl Desktop is probably by using the same connection being used by the Tor Browser. To do that, follow these steps:

1. Download, install and launch the **[Tor Browser](https://www.torproject.org/download/)**
2. Connect to the Tor network by clicking on `Connect` or configure your connection parameters by clicking on `Configure`
3. Once connected, leave the Tor Browser running in the background
4. Open a terminal and go to the folder you’ve installed your Particl Desktop executable file
5. Launch Particl Desktop with the `-proxy=127.0.0.1:9150` argument

| OS (package)                      | Launch parameter                                                               |
| --------------------------------- | ------------------------------------------------------------------------------ |
| {{< ico win >}} **Windows**       | `“Particl Desktop.exe” -proxy=127.0.0.1:9150`                                  |
| {{< ico apple >}} **MacOS**       | `./Particl\ Desktop.app/Contents/MacOS/Particl\ Desktop -proxy=127.0.0.1:9150` |
| {{< ico linux >}} **Linux**       | `./Particl\ Desktop -proxy=127.0.0.1:9150`                                     |
| {{< ico linux >}} **Linux** (DEB) | `particl-desktop -proxy=127.0.0.1:9150`                                        |


## b) Using the Tor Daemon

The Tor Browser method is quite easy, but if you don’t want to run the Tor Browser alongside Particl Desktop, you can only run the Tor daemon instead. This Tor daemon will run seamlessly in the background and won’t bother you with a browser that you need to keep open.

{{< tabs "tor-particl-desktop" >}}
{{< tab "Windows" >}}

### Windows

1. Download and install the [Tor Browser](https://www.torproject.org/download/)
2. Open the Windows File Explorer and navigate to the directory in which you’ve installed the Tor Browser (i.e. `C:\Tor Browser\`)
3. Go into the `Browser\TorBrowser\Tor` directory
4. Hold down the `Shift` key and right-click on the Tor folder → _Open command window here_
5. In the terminal that pops up, type `tor.exe –service install`
6. Tor should now be running as a Windows service. To verify, hold down the {{fa>windows}} key and press `R` key to open up the Run window. Then, type `services.msc` and then press `OK`
7. You should see Tor running as a service somewhere in the list
8. Go to the folder where your Particl Desktop executable is located
9. Hold down the `Shift` key and right-click on the Tor folder → _Open command window here_
10. Launch Particl Desktop and route its connection through Tor by typing `“Particl Desktop.exe” -proxy=127.0.0.1:9050`

{{< /tab >}}
{{< tab "macOS" >}}

### macOS

1. Open a terminal
2. Install Brew by typing `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
3. Go through the installation process
4. Install the Tor daemon: `brew install tor`
5. Enable Tor as a Brew service: `brew services start tor`
6. Navigate (using `cd`) to the folder where your Particl Desktop application icon is located (i.e. `cd /home/USER/Applications/`)
7. Launch Particl Desktop by routing its connection through the Tor network: `./Particl\ Desktop.app/Contents/MacOS/Particl\ Desktop -proxy=127.0.0.1:9050`

{{< /tab >}}
{{< tab "Linux" >}}

### Linux

1. Open a terminal
2. Install the Tor daemon: `sudo apt install tor` (for Debian/Ubuntu-based distributions)
3. Make sure Tor launches on startup: `sudo systemctl enable tor`
4. Navigate (using `cd`) to the folder where your Particl Desktop application icon is located (i.e. `cd ~/Particl/`)
5. Launch Particl Desktop by routing its connection through the Tor network: `./Particl\ Desktop -proxy=127.0.0.1:9050` (if you’ve installed Particl using the DEB package, then simply type this command: `particl-desktop -proxy=127.0.0.1:9050` from any folder)

{{< /tab >}}
{{< /tabs >}}


## c) Tor as a Hidden Service

You can also run Tor as a hidden service and connect your Particl Desktop to it. By running Tor as a hidden service, you allow other Tor users to use your node as an entry or exit point. This helps the Tor network being more decentralized, thus increasing its anonymity.

{{< hint info >}}
Please refer to **dedicated guide on [running Tor as Hidden Service](/tutorial/privacy/tor-hidden-service/)**
{{< /hint >}}