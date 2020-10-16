---
title: Trezor wallet
subtitle: This page is only relevant for developers working on Trezor wallet 
slug:
weight: 4
tags:
  - dev
  - Trezor wallet
---

{{< toc >}}

## Requirements

- **Python** 3.6+ (verify this by doing `python3 --version`)
- **Docker** (Trezor python package)
- **Protocol Buffers** (protoc)


## Build instructions

1. Plug in the Trezor.
2. Clone [Particl's Trezor firmware](https://github.com/particl/trezor-firmware) repository:

We also need to fetch the corresponding submodules.

```bash
git clone https://github.com/particl/trezor-firmware.git
cd trezor-firmware
git submodule update --init --recursive
```

Install the following udev rules:

```bash
cd trezor-firmware/common/udev/
cp 51.trezor.rules /etc/udev/rules.d/51.trezor.rules
```

And install `trezorctl`:

```bash
cd ./python
pip3 install .
trezorctl list
```

{{< hint warning >}}
**The list should not be empty** if your device is connected. Note, it could be that the installation fails due to missing libraries, or outdated versions.
{{< /hint >}}

Also, my device still shipped with the HIDAPI instead of WebUSB firmware. So it might be required to install the HIDAPI libs additionally.

```bash
sudo apt-get install python3-dev python3-pip cython3 libusb-1.0-0-dev libudev-dev
pip3 install --upgrade setuptools
pip3 install protobuf
pip3 install trezor[hidapi]
```

### Update bootloader

Update the bootloader and firmware to 1.8.0 and 1.8.1 respectively. The `webusb` support is enabled from 1.6.0 and 1.7.1 respectively.

This will at a certain stage require you to attach the Trezor device while pressing both buttons. Remember this, as it is a requirement
for flashing the firmware on device.

This also applies to trezorctl!

Note: this will display the bootloader version.

This will put a stock/official firmware on the device created and signed by SatoshiLabs.

```bash
./trezorctl firmware-update
```

### Trezor One firmware

Building the application is rather simple with docker.

```bash
./legacy/build.sh
```

### Trezor T firmware

This one is python based and gets compiled to C.

```bash
make build_fimware
```

### Emulator support

You can pretend to run a Trezor by using the emulator.

We have a special branch which is dedicated to having the emulator build enabled by default.

```bash
git checkout emulator
```

then just build & run for the **Trezor One**:

```bash
./legacy/build.sh
./build/trezor-emulator-v1.8.0-6372-ga2122471e.elf
```

For the **Trezor T**:

```bash
cd core
make build_unix
./emu.sh
```

### Initializing the device through trezorctl

When you see a warning "Go to trezor.io/start" on the screen then you could alternatively opt for resetting the device through trezorctl, using the reset-device command. This will also generate the 24 words without having to mess with the browser.

```bash
trezorctl reset-device
```


## Troubleshooting

### Can't find the device?

```bash
user@host:~$ lsusb
Bus 002 Device 108: ID 1209:53c1 InterBiometrics 
```

```bash
user@host:~$ sudo dmesg
[47525.049827] vhci_hcd vhci_hcd: pdev(0) rhport(0) sockfd(0)
[47525.049838] vhci_hcd vhci_hcd: devid(131087) speed(2) speed_str(full-speed)
[47525.255116] usb 2-1: new full-speed USB device number 108 using vhci_hcd
[47525.359079] usb 2-1: SetAddress Request (108) to port 0
[47525.379016] usb 2-1: New USB device found, idVendor=1209, idProduct=53c1
[47525.379052] usb 2-1: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[47525.379081] usb 2-1: Product: TREZOR
[47525.379097] usb 2-1: Manufacturer: SatoshiLabs
[47525.379178] usb 2-1: SerialNumber: 087481176AF508D78C503E04
[47525.391749] hid-generic 0003:1209:53C1.0011: hiddev0,hidraw1: USB HID v1.11 Device [SatoshiLabs TREZOR] on usb-vhci_hcd-1/input1
```

The firmware has the idVendor of 1209. If you see 534c then you haven't upgraded the firmware yet.
If you have the bridge installed because you also want to use the application of trezor itself, then make sure that
the communications of trezorctl go directly to the usb. I disabled the brigde, but it might prioritze the usb anyways (verify assumption?)

```bash
sudo service trezord stop
```

```bash
user@host:~$ sudo trezorctl --verbose version
0.11.0
```

```bash
user@host:~$ sudo trezorctl --verbose list
[2018-12-11 02:38:32,382] trezorlib.transport.hid INFO: HID transport is disabled: No module named 'hid'
[2018-12-11 02:38:32,392] trezorlib.transport INFO: Enumerating BridgeTransport: found 0 devices
[2018-12-11 02:38:32,392] trezorlib.transport INFO: Enumerating UdpTransport: found 0 devices
[2018-12-11 02:38:32,394] trezorlib.transport INFO: Enumerating WebUsbTransport: found 1 devices
webusb:002:1
```

```bash
user@host:~$ sudo trezorctl --verbose ping test
[2018-12-11 02:37:43,406] trezorlib.transport.hid INFO: HID transport is disabled: No module named 'hid'
[2018-12-11 02:37:43,416] trezorlib.transport INFO: Enumerating WebUsbTransport: found 1 devices
[2018-12-11 02:37:43,420] trezorlib.transport INFO: Enumerating BridgeTransport: found 0 devices
[2018-12-11 02:37:43,420] trezorlib.transport INFO: Enumerating UdpTransport: found 0 devices
[2018-12-11 02:37:43,420] trezorlib.client INFO: creating client instance for device: webusb:002:1
[2018-12-11 02:37:43,420] trezorlib.transport.protocol DEBUG: sending message: Initialize
Initialize (0 bytes) {
}
[2018-12-11 02:37:43,448] trezorlib.transport.protocol DEBUG: received message: Features (148 bytes)
[2018-12-11 02:37:43,449] trezorlib.transport.protocol DEBUG: sending message: Ping
Ping (6 bytes) {
    message: 'test',
}
[2018-12-11 02:37:43,453] trezorlib.transport.protocol DEBUG: received message: Success
Success (6 bytes) {
    message: 'test',
}
test
```

### What if I bricked my device somehow?

Flashing different version of firmware should be relatively harmless, be warned when messing with the bootloader however.

I haven't verified it but if you managed to brick the device by flashing a faulty bootloader, as a last resort the st-link might help you recover. See `/bootloader/combine/write.sh` for the single line flash.

The script is specifically for an ST-LINK but I don't know if you can't use other similar flashing devices.
