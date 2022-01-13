---
layout: post
title: "Raspberry Pi Headless"
date: 2021-12-10
categories: learn
---

# How to headless set up your raspberry pi

> Writing this because everytime I format the SD Card I forgot how to set the headless way.

***

## Table of Contents
  - [Setting Up](#setting-up)
  - [VNC access](#vnc-access)
  - [Troubleshoot](#troubleshoot)

***
## Setting Up
After installing the OS on the sd card, open the boot folder and create the two files on root:
- `ssh`
- `wpa_supplicant.conf`

At `wpa_supplicant.conf` save with the following code:

```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
scan_ssid=1
ssid="your_wifi_ssid"
psk="your_wifi_password"
}
```

Boot the sd card on the raspberry pi and wait a few minutes until it properly connects.

After it, access through terminal with `sudo ssh pi@raspberrypi.local`.

The default password is `raspberry`.

***
## VNC access

Inside the ssh access, configure the VNC with `sudo raspi-config` following:

- Interface Options
  - VNC
    - Yes to enable VNC Server

Then, open the connection with VNC Viewer with the credentials (if default):
```
user raspberrypi.local
passwd raspberry
```
***
## Troubleshoot

You may bump on some

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@       WARNING: POSSIBLE DNS SPOOFING DETECTED!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

or

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

In case of one of that or both, just access your ssh file with
`cd ~/.ssh/` 
and change the `known_hosts` file with
`sudo nano known_hosts`. In the file, just delete (`crtl+k`) the lines containing `raspberrypi.local`. And that's it!
