---
title: "Nouveau"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
author: Bryanpwo
---

by Bryanpwo

# Nouveau

If your Nvidia card isn’t supported anymore by the proprietary nvidia driver, you can use the open-source driver provided by Linux.

Most of the time, you can use the nouveau driver provided by the package **[xf86-video-](https://www.archlinux.org/packages/extra/x86_64/xf86-video-nouveau/)[nouveau](https://www.archlinux.org/packages/extra/x86_64/xf86-video-nouveau/)**, but on older GPU’s it is most likely this package will cause tearing and bad performance, so it is better to use the modesetting driver shipped by default in the Linux kernel. To enable it you just have to uninstall the unneeded package and change the following configuration.

`sudo pacman -R xf86-video-nouveau`

sudo nano /etc/mkinitcpio.conf

Then go to the line

`MODULES=()`

And change it into:

`MODULES=(nouveau)`

Save it with \[CTRL+X\]

Then type:

`sudo mkinitcpio -p linux`

If you also have linux-lts installed then repeat the last process with linux-lts on the end of the line.

Reboot and your system is running with nouveau.

In some cases, the video quality has a delay or glitches, especially with DRM encoded videos on services as Netflix for example.

In that case try to install the nouveau-fw package (AUR) – after install reboot the system.