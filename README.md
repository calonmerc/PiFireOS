PiFireOS
==========

[![Version](https://img.shields.io/github/v/release/calonmerc/PiFireOS.svg?color=brightgreen&label=version)](https://github.com/calonmerc/PiFireOS/releases/latest)
[![Released](https://img.shields.io/badge/dynamic/json.svg?color=brightgreen&label=released&url=https://api.github.com/repos/calonmerc/PiFireOS/releases&query=$[0].published_at)](https://github.com/calonmerc/PiFireOS/releases/latest)
![GitHub Releases (all releases)](https://img.shields.io/github/downloads/calonmerc/PiFireOS/total.svg)
[![Build status](https://img.shields.io/github/actions/workflow/status/calonmerc/PiFireOS/buildRaspios.yml)](https://github.com/calonmerc/PiFireOS/actions/workflows/buildRaspios.yml)
[![Build status](https://img.shields.io/github/actions/workflow/status/calonmerc/PiFireOS/buildDietpi.yml)](https://github.com/calonmerc/PiFireOS/actions/workflows/buildDietpi.yml)

### PiFire Stats
[![GitHub last commit (branch)](https://img.shields.io/github/last-commit/nebhead/pifire/development)](https://github.com/nebhead/PiFire/commits/development)
[![Version](https://img.shields.io/github/v/release/nebhead/PiFire.svg?color=brightgreen&label=version)](https://github.com/nebhead/PiFire/releases/latest)
[![Released](https://img.shields.io/badge/dynamic/json.svg?color=brightgreen&label=released&url=https://api.github.com/repos/nebhead/PiFire/releases&query=$[0].published_at)](https://github.com/nebhead/PiFire/releases/latest)

<!--ts-->
* [PiFireOS](#pifireos)
   * [Where to get it?](#where-to-get-it)
   * [How to use it?](#how-to-use-it)
   * [Features](#features)
   * [Developing](#developing)
   * [Get help](#get-help)
<!--te-->

***
:information_source: You can find the PiFire documentation [here](https://nebhead.github.io/PiFire/)
***

***

A [Raspberry Pi](http://www.raspberrypi.org/) distribution for Pi based pellet smoker controllers. It includes the [PiFire](https://nebhead.github.io/PiFire/) software for managing and monitoring multiple Octoprint instances out of the box.

This repository contains the source script to generate the distribution out of an existing [Raspberry Pi OS](https://www.raspberrypi.org/software/) image.

## Where to get it?

Download the latest stable build (typically running latest stable [PiFire](https://github.com/nebhead/PiFire/releases):

[![Stable version](https://img.shields.io/github/v/release/calonmerc/PiFireOS.svg?color=brightgreen&label=version)](https://github.com/calonmerc/PiFireOS/releases/latest)

Download the latest nightly builds (latest image always runs newest code from [PiFire development branch](https://github.com/nebhead/PiFire/commits/development):

[![Nightly version](https://img.shields.io/badge/version-nightly-brightgreen)](https://github.com/calonmerc/PiFireOS/actions/workflows/build.yml)

## How to use it?

* Flash the image to an sd card using [Balena Etcher](https://www.balena.io/etcher) or [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
* Configure your WiFi by editing `pifireos-wpa-supplicant.txt` on the root of the SD card. **You may need to eject and reinsert the card.**
* Boot the Pi from the card
* Connect via web browser to [http://pifireos.local](http://pifireos.local).
    * Since the SSL certificate is self signed (and generated upon first boot), you will get a certificate warning at the latter location, please ignore it.
* Configure your smoker settings.
* OPTIONALLY:
  * Log into your Pi via SSH (it is located at `pifireos.local` [if your computer supports bonjour](https://learn.adafruit.com/bonjour-zeroconf-networking-for-windows-and-linux/overview) or find the IP address assigned by your router), default username is "pi", default password is "raspberry".
  * Change the password; run: `passwd`
  * Change the configured timezone; run: `sudo dpkg-reconfigure tzdata`
  * Change the hostname; run: `echo myhostname | sudo tee /etc/hostname`
    * Your PiFireOS instance will then no longer be reachable under `pifireos.local` but rather the hostname you chose postfixed with `.local`, so keep that in mind.
  * If WiFi is not available, a "PiFire-Hotspot" network will be started.
    * Connect any compatible device and connect to `192.168.50.1` to control your smoker.

:information_source: Supervisor is configured by default. Access at: [http://pifireos.local:9001](http://pifireos.local:9001) with username "pifire" and password "PiFire".

## Features

* [PiFire](https://nebhead.github.io/PiFire/) software for managing and controlling pellet smokers
* [Supervisor](http://supervisord.org/) software for managing gui and control processes
* [hostapd](https://w1.fi/hostapd/) software for managing automatic hotspot

## Developing

Code contribution would be appreciated!

## Get Help

### Discord

The [PiFire Discord server](https://discord.gg/JmzbCUcefS) has an #os-images channel. This is likely the best place for support for this image.

### Issue Tracker

PLEASE limit this to issues with the image, not to issues with PiFire itself.
