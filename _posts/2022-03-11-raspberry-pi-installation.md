---
layout: post
title:  "The 3rd step to own Nextcloud"
description: "Raspberry Pi installation"
categories: raspberry-pi installatiion
permalink: "/raspberry-pi/installation/"
---
# Raspberry Pi installation

> Prerequisites
- [Order devices and facilities]({% post_url 2022-03-9-order %})
- [Installation all devices and facilities to the X825 V2.0 board]({% post_url 2022-03-10-box-installation %})

Before putting all things together I recommend to verify the Raspberry Pi if it works as expected. Check all ports, connection to the network, etc.

1. Burn OS(Lite 64bit) to SD card via `Raspberry Pi Imager` program. Add empty `ssh` file to boot partition in order to SSH connection when the Raspberry Pi is started.
2. Plug in SD card, wired internet and power (USB-C).
3. Log into router and wait until we see `raspberry` between connected devices. Copy the IP address of the device. We will need it for connection to device.
    - Optional (but recommended) step: Reserve IP address for the Raspberry Pi's MAC address. The MAC address reservation allows us to use the same IP address even when we will reinstall the Raspberry Pi OS, or after some restart or electricity outage.
4. Connect to Raspberry Pi via `ssh` command with user *pi* and password *raspberry*
```sh
ssh pi@<ip_addre> # e.g. ssh pi@192.168.0.111
```
Make sure the device is up to date with the latest updates.
```sh
sudo apt update && sudo apt dist-upgrade
```

Now we can play a bit with the device, check ports and have a fun.

### Tmux tool (Optional)

Install tmux to secure managing server via storing session.
```sh
sudo apt install tmux
# type tmux to activate
```
> Following [post]({% post_url 2022-03-12-raspberry-pi-projekt %}) is about finishing box installation and setup Nextcloud.