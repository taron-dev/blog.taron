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

Before putting all things together I recommend to verify the Raspberry Pi if it works as expected. Check all ports, connection to the network etc.

1. Burn OS(Lite 64bit) to SD card with Raspberry Pi Imager. Add empty ssh file to boot partition in order to ssh connection when pi is started.
2. Plug in SD card, wired internet and power (usb-c).
3. Log into you router and wait unitl you see `raspberry` between connected devices. Copy the ip adress of the device. You will need it for connection to device.
    - Optional (but recommended) step: Reserve ip address for the raspberry pi's mac address. The MAC adress reservation allows us to use the same ip address even when you will reinstall the Raspberry Pi OS, or after some restart or eletricity outage.
4. Connect to raspberry via ssh command with user *pi* and password *raspberry*
```sh
ssh pi@<ip_addre> # e.g. ssh pi@192.168.0.111
```
Make sure your device is up to date with latest updates.
```sh
sudo apt update && sudo apt dist-upgrade
```

Now you can play a bit with the device, check ports and have a fun.

### Tmux tool (Optional)

Install tmux to secure managing server via storing session.
```sh
sudo apt install tmux
# type tmux to activate
```
> Following [post]({% post_url 2022-03-12-raspberry-pi-projekt %}) is about finishing box installation and setup Nextcloud.