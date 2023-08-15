---
title: "Nvidia Optimus Notebooks Hybrid Graphics"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Nvidia Optimus Notebooks Hybrid Graphics

Find out if you are on such system run this from terminal:

`lspci -vnn | grep '\''[030[02]\]'`

if it gives out something like this with two devices:

`00:02.0 VGA compatible controller [0300]: Intel Corporation Haswell-ULT Integrated Graphics Controller [8086:0a16] (rev 09) (prog-if 00 [VGA controller])`

`01:00.0 3D controller [0302]: NVIDIA Corporation GK107M [GeForce GT 750M] [10de:0fe4] (rev ff) (prog-if ff)`

it will be that you have such hybrid system with a combination of nvidia and intel gpu.

Some basic information on that: [https://wiki.archlinux.org/index.php/Hybrid\_graphics](https://wiki.archlinux.org/index.php/Hybrid_graphics)

As of 2021 the proprietary Nvidia Driver supports handling of Optimus hybrid systems per default. It will boot on intel integrated per default, but only if Nvidia Modesetting DRM is enabled.

To do so follow the instructions here:

> [Nvidia Optional Enhancements and Troubleshooting](../nvidia-optional-enchancements-and-troubleshooting)

You can use the method to add the option to /etc/default/grub and regenare grub.cfg, or use the second method by integrating it into initramfs kernel image by editing /etc/mkinitcpio.conf and regenerate initramfs images.

To be able to switch between the two GPUs usage, you can use one of the options to have this available in different ways:

**Supergfxctl is a useful utility provided by [ASUS Linux](https://wiki.archlinux.org/title/ASUS_Linux). It helps with managing GPU switching functionality on hybrid laptops.** (While supergfxctl was originally designed with ASUS Optimus laptops in mind, it has since evolved into a standalone tool that functions with any laptops with hybrid graphics.)

[Supergfxctl](https://wiki.archlinux.org/title/Supergfxctl)

**EnvyControl is a CLI tool that provides an easy way to switch between GPU modes on Nvidia Optimus systems**:

[Envy-Control](../envy-control/)

**Optimus-manager is one solution currently where you can switch between the two GPU’s:**

[Optimus-Manager](https://discovery.endeavouros.com/nvidia/optimus-manager-for-nvidia/2021/03/)

**Optimus Switch is completely powerdown Nvidia GPU and will save more power, but needs to reboot system to do so:**

[Optimus-Switch](https://discovery.endeavouros.com/nvidia/optimus-switch-another-solution-for-optimus-laptops/2021/04/)

**Render Offload is a new mechanism build inside the Nvidia Driver:**

[Render-Offload](https://download.nvidia.com/XFree86/Linux-x86_64/435.17/README/primerenderoffload.html)

**Bumblebee is the very first Linux implementation to switch and manage Optimus systems GPU’s, but is not working on newer systems:**

[Bumblebee (older systems)](https://discovery.endeavouros.com/nvidia/bumblebee-for-nvidia-optimus-older-systems/2021/03/)

### Some helpful links to tutorials

[https://github.com/linesma/Optimus-indicator](https://github.com/linesma/Optimus-indicator)

[https://forum.endeavouros.com/t/optimus-manager-issues/7403/15](https://forum.endeavouros.com/t/optimus-manager-issues/7403/15)

[https://github.com/Askannz/optimus-manager](https://github.com/Askannz/optimus-manager)

[https://wiki.archlinux.org/index.php/PRIME](https://wiki.archlinux.org/index.php/PRIME)

[https://forum.endeavouros.com/t/optimus-switch-another-solution-for-optimus-laptops](https://forum.endeavouros.com/t/optimus-switch-another-solution-for-optimus-laptops)

https://discovery.endeavouros.com/community-contributions/how-to-enable-nvidia-optimus/2019/11/