# Headless Raspberry Pi setup for development

## Raspbian

Download and flash debian onto an microSD card.

Follow instructions on https://www.raspberrypi.org/downloads/raspbian/ and use Etcher to flash the OS onto the SD card

## Enable SSH
Once SD card is flashed, place a file "ssh" into the root of the boot partition.

## Static IP for Pi

There are ways to setup the Pi completely headless, without the need for a keyboard or screen. Please go to this page to see how: https://hackernoon.com/raspberry-pi-headless-install-462ccabd75d0

We will use a keyboard and screen one time for setup, after setting it up, you can loose the peripherals.

First, plug the SD card into your Pi. Grab a keyboard and a screen (hook it up to the Pi via HDMI). You can now boot up the Pi.

To make sure the Pi always has the same IP address everytime you want to develop, no matter where you are, you can connect the Pi with an ethernet cable to your laptop/PC and setup a static IP.

To setup the static IP:
* Edit /etc/dhcpcd.conf with nano, vim or emacs.
* Disable commented out "interface eth0" and static ip v4 and/or v6, all in the example static IP config
* Give IP address you prefer
* Leave routers and dnservers commented out

Connect to wireless network so you can still access internet:
* Use wpa_passphrase to generate encrypted network key
* Use generated network stuff from wpa_passphrase, paste it into bottom of file /etc/wpa_supplicant/wpa_supplicant.conf
* Reboot Pi

Done! 

You can now ssh into your Pi and develop anything you want.

I use this setup to develop C/C++ on the Pi via Visual Studio (checkout Visual C++ extension, it's integrated into VS2017 by default)




