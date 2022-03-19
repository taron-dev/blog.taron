---
layout: post
title:  "4th step to own Nextcloud"
description: "Finish box installation and setup Nextcloud"
categories: raspberry-pi
permalink: "/raspberry-pi/nextcloud/"
---
# Finish box installation and setup Nextcloud

> Prerequisites
- [Order devices and facilities](../order/)
- [Installation all devices and facilities to the X825 V2.0 board](../box-installation/)
- [Installation and verification of Raspberry Pi device](../installation/)

### Setup X735 board with raspberry pi, case and fan.

In order to run PWN fan on X735 we need to run shell script.
<https://wiki.geekworm.com/X735_V2.5_Software>

> Tip: Latest verison of Rasppbian comes with v3 of python. This requires me to run python commands with `python3` instead of `python`.

### Setup Pi to mount disk always on boot.

List disk, partitions and mount points.
```sh
lsblk
```
For example `sda` has type disk and no mount point.

Verify if `parted` is already installed.
```sh
which parted

# in case of not installed parted type
sudo apt install parted
```

Set disk label type.
```sh
sudo parted /dev/sda mklabel gpt
```

Create partition type ext4 on disk `/dev/sda` 100% size of disk capacity.
```sh
sudo parted -a opt /dev/sda mkpart primary ext4 0% 100%
```

Format partition on path `/dev/sda1` with tool `mkfs.ext4` and name it (in my case kingstonepartition).
```sh
sudo mkfs.ext4 -L kingstonepartition /dev/sda1
```

Create folder for mount poin in `/mnt/kingstonedata` path.
```sh
sudo mkdir -p /mnt/kingstonedata
```

Get `partuuid` from:
```sh
blkid
```

Open `fstab` file.
```sh
sudo nano /etc/fstab
```

In order to mount the disk automatically during start up add line like this to `fstab` with partition path, label and uuid of `/dev/sda1`:
```sh
LABEL="kingstonepartiti" UUID="5ecdfe5d-1a23-4662-adfe-b59bb73aff3e" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="primary" PARTUUID="3bdd15b9-6386-4a4f-9103-c7a98ab951f5"
```

Mount all file-systems mentioned in `fstab`.
```sh
sudo mount -a
```

In the end reboot machine.
```sh
reboot
```

### Setup data folder

The main purpose of the disk connected to the board is data storage for our nextcloud. I created the `nextcloud_data` folder on the disk as the root folder for our nextcloud data.

Important thing is to update owner of this folder to `www-data` via:
```sh
sudo chown -R www-data:www-data /mnt/kingstonedata/nextcloud_data
```
When we will go through nextcloud web setup we will set the `/mnt/kingstonedata/nextcloud_data` as the data folder used by nextcloud.

## Nextcloud

Start tmux session with `tmux` command.
Verify if wget is installed:
```sh
which wget
# Output similar to
/usr/bin/wget
```

If not then:
```sh
sudo apt install wget
```

Download and unzip NC with wget
```sh
wget https://download.nextcloud.com/server/releases/nextcloud-23.0.0.zip
unzip nextcloud-23.0.0.zip
```

There is blog post <https://www.learnlinux.tv/nextcloud-complete-setup-guide/> and related video <https://www.youtube.com/watch?v=y4dtcr2NL5M> which contains all needed commands and almost all steps in order to install nextcloud on raspberry. Before we will setup the nextcloud we want to configure the data folder.