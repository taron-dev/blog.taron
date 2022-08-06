---
layout: post
title:  "The 2nd step to own Nextcloud"
description: "Box installation"
categories: raspberry-pi box
permalink: "/raspberry-pi/box-installation/"
---
# Box installation

> Prerequisites
- [Order devices and facilities]({% post_url 2022-03-9-order %})

Prepare all items from the order: charger, box, fan, board, SSD disk and Raspberry Pi like we can see in the following image.
![order]({{ '/assets/images/unpacked_order.jpg' | relative_url }})

For the first steps we will need board, SSD disk, screws and Raspberry Pi. Other things we put aside for now.
![Raspberrz Pi, X825 board, screws and SSD disk]({{ '/assets/images/raspberry_board_screws_ssd.jpg' | relative_url }})

As the first step we will connect the X825 board with SSD disk.
![X825 board and SSD disk]({{ '/assets/images/board_and_ssd.jpg' | relative_url }})

Insert the SSD disk to the SATA port on the bottom side of the X825 board and use two screws to fix the SSD disk from the top of the X825 board. The following image shows the mounted SSD disk to X825 board form the bottom.
![Mounted SSD disk with X825 board]({{ '/assets/images/board_mounted_ssd.jpg' | relative_url }})

Use another four screws to fix the Raspberry Pi on top of the X825 board like in two following photos, if you want to play a bit with this setup. If not, just put the Raspberry Pi on top of the board.
![Mounted X825 board, SSD disk and Raspberry Pi]({{ '/assets/images/mounted_board_ssd_raspberry.jpg' | relative_url }})
![Side view of mounted X825 board, SSD disk and Raspberry Pi]({{ '/assets/images/mounted_board_ssd_raspberry_side.jpg' | relative_url }})

Prepare fan, screws and spacer nuts.
![Fan, screws, spacer nuts and Raspberry Pi]({{ '/assets/images/fan_screws_spacer_nuts_raspbery.jpg' | relative_url }})

Use spacer nuts to fix the Raspberry Pi and make space for placing fan on top of the spacer nuts. Don't forget to fix the fan with spacer nuts. Result should be similar to the following photo.
![Mouunted fan, screws, spacer nuts and Raspberry Pi]({{ '/assets/images/mounted_fan_screws_spacer_nuts_raspbery_front.jpg' | relative_url }})

It's time to open the box. We will find, like in the following picture, the small fan (which we will not need) and the button to turn on/off, or restart the device.
![Box content]({{ '/assets/images/box_content.jpg' | relative_url }})

Place carefully our setup into the box and fix it with screws from the bottom.
![Mounted setup in the box]({{ '/assets/images/mounted_raspberry_in_box.jpg' | relative_url }})

Do not forget to install the button to be able to control the device. For this, I recommend to check the installation video from [manofacturer](https://www.youtube.com/watch?v=JxUNhIxXgj4) or more detailed one from [DB Tech](https://www.youtube.com/watch?v=uh1_05AZmzI).

Cover the setup with lid and fix the box with screws. Do not forget to connect `X825 board` with the Raspberry Pi via USB interconnector.

We could check the final setup in the following photos.
![Box front view]({{ '/assets/images/box_front.jpg' | relative_url }})
![Box right view]({{ '/assets/images/box_right.jpg' | relative_url }})
![Box back view]({{ '/assets/images/box_back.jpg' | relative_url }})
![Box left view]({{ '/assets/images/box_left.jpg' | relative_url }})

> Following [post]({% post_url 2022-03-11-raspberry-pi-installation %}) is about Raspberry Pi installation.