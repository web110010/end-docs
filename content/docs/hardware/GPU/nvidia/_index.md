---
title: "Nvidia"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
bookCollapseSection: true
# bookComments: false
# bookSearchExclude: false
---

# Nvidia

![](001.webp)

As most newer cards will work with the latest (called [nvidia](https://www.archlinux.org/packages/extra/x86_64/nvidia/)) driver, older cards are no longer supported by the latest driver. Nvidia is sorting out older GPU to legacy branch this cards are not supported by the latest driver.

The first thing you should do is get knowledge about your card and supported driver:

### GeForce 930~, 10-20, and Quadro/Tesla/Tegra K-series cards and newer (cards from around 2010 and later)

These are supported by the main (**495**xx) nvidia packages/Driver [nvidia](https://archlinux.org/packages/extra/x86_64/nvidia/) [nvidia-dkms](https://archlinux.org/packages/extra/x86_64/nvidia-dkms/)

If these packages do not work, [nvidia-beta](https://aur.archlinux.org/packages/nvidia-beta/)AUR may have a newer driver version that offers support.

See here: [about-legacy-gpu](https://www.nvidia.com/en-us/drivers/unix/legacy-gpu/)

EndeavouOS provides some check script to help you to find supported drivers:

    nvidia-driver-supported-branches

Included inside nvidia-installer-db package, simply run it from a terminal and you will get some useful information looking like so:

`» nvidia-driver-supported-branches ↵   NVIDIA card id: 128b   Series 470: supported`

## Overview over the legacy branches:

**(unsupported means no package for driver at the repositories)**

### 470xx (AUR): (new legacy branch oct. 2021)

install the [nvidia-470xx-dkms](https://aur.archlinux.org/packages/nvidia-470xx-dkms/)AUR package. (or [https://repo.m2x.dev/](https://repo.m2x.dev/) Repository)

**Affected cards:** GeForce 630-920 series cards \[GKxxx\] from around 2013-2014 (Kepler)

### 390xx

_unsupported_ but works with xorg 1.20 (current version)

**Affected cards:** GeForce 400/500/600 series cards \[NVCx and NVDx\]

The driver can be found in the AUR or use the default [Nouveau](https://discovery.endeavouros.com/nvidia/nouveau/2021/03/) driver shipped with the Linux kernel

There are prebuild packages available at the [m2x.dev repository](https://repo.m2x.dev/).

### 340xx

unsupported but works with xorg 1.20 (current version)

**Affected Cards:** GeForce 8/9, ION and 100-300 series cards \[NV5x, NV8x, NV9x and NVAx\]

The driver can be found in the AUR or us the default [Nouveau](https://discovery.endeavouros.com/nvidia/nouveau/2021/03/) driver shipped with the kernel

### 304xx

unsupported use [Nouveau](https://discovery.endeavouros.com/nvidia/nouveau/2021/03/) (no AUR build maintained anymore too)

**Affected Cards:**For GeForce 6/7 series cards \[NV4x and NV6x\]

### 173xx

unsupported use [Nouveau](https://discovery.endeavouros.com/nvidia/nouveau/2021/03/) (no AUR build)

**Affected Cards:**GeForce 5 FX series cards \[NV30-NV36\]

### 96xx

unsupported use [Nouveau](https://discovery.endeavouros.com/nvidia/nouveau/2021/03/) (no AUR build)

**Affected Cards:** GeForce 2/3/4 MX/Ti series cards \[NV11, NV17-NV28\]

[nvidia-installer](https://discovery.endeavouros.com/nvidia/nvidia-installer/2021/03/) only supports the **[latest driver](https://www.archlinux.org/packages/extra/x86_64/nvidia-dkms/)**

## To see what driver version support your card go here:

[Nvidia Driver Search](http://www.nvidia.com/Download/index.aspx)

Put in the info for your card, and choose Linux-64bit as OS.

Or see here main Nvidia packages supported card list: [https://www.nvidia.com/](https://www.nvidia.com/)

**All supported cards for nvidia-390xx:** (not supported by nvidia-installer)

[Nvidia 390xx Supported Cards List](https://www.nvidia.com/download/driverResults.aspx/134262/en-us)

**For GeForce it seems to show all drivers only on this page:**

[Nvidia-geforce](https://www.geforce.com/drivers/)

## You can also use our tool to check your card:

`nvidia-installer-check`

this will give you something like this if your card is supported by the latest NVidia-driver:

`Your graphics card (id: 128b) is supported by the nvidia-dkms driver.   To install a driver for this card, you can use nvidia-installer-dkms.`

If you have PC with a dedicated card plugged in you can use nvidia-installer-dkms to get latest driver installed, for more info go here:

[nvidia-installer-dkms](https://discovery.endeavouros.com/nvidia/nvidia-installer/2021/03/)

For other Nvidia settings choose the right article for your hardware:

[https://discovery.endeavouros.com/category/nvidia/](https://discovery.endeavouros.com/category/nvidia/)