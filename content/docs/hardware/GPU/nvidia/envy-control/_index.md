---
title: "Envy Control"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Envy Control

![](001.webp)

EnvyControl is a **CLI** tool that provides an easy way to switch between GPU modes on Nvidia Optimus systems (i.e laptops with hybrid Intel + Nvidia or AMD + Nvidia graphics configurations) under Linux.

[https://github.com/bayasdev/envycontrol](https://github.com/bayasdev/envycontrol)

Features
--------

*   Written in Python 3+ for portability and compatibility
    
*   Supports GDM, SDDM and LightDM display managers

*   Save battery with integrated graphics mode

*   PCI-Express Runtime D3 (RTD3) Power Management support for Turing and later

*   Coolbits support for GPU overclocking

*   Fix screen tearing with ForceCompositionPipeline

*   works for both dracut and mkinitcpio

**The tool offers 3 Graphics modes:**

[](https://github.com/bayasdev/envycontrol/blob/main/README.md#integrated)**Integrated:** The integrated Intel or AMD iGPU is used exclusively

**Hybrid:** Enables PRIME render offloading

**Nvidia:** The Nvidia dGPU is used exclusively

detailed info here: [README.md#-graphics-modes](https://github.com/bayasdev/envycontrol/blob/main/README.md#-graphics-modes)

You will find an [AUR PKGBUILD](https://aur.archlinux.org/packages/envycontrol) and can install it over yay:

    yay -S envycontrol

to run it use this commandline and check the usage box for options (graphics modes):

    sudo envycontrol -s <MODE>

Usage:
------

    usage: envycontrol.py [-h] [-v] [-q] [-s MODE] [--dm DISPLAY_MANAGER] [--force-comp] [--coolbits [VALUE]] [--rtd3 [VALUE]] [--reset-sddm] [--reset] [--verbose]
    
    options:
      -h, --help            show this help message and exit
      -v, --version         Output the current version
      -q, --query           Query the current graphics mode
      -s MODE, --switch MODE
                            Switch the graphics mode. Available choices: integrated, hybrid, nvidia
      --dm DISPLAY_MANAGER  Manually specify your Display Manager for Nvidia mode. Available choices: gdm, gdm3, sddm, lightdm
      --force-comp          Enable ForceCompositionPipeline on Nvidia mode
      --coolbits [VALUE]    Enable Coolbits on Nvidia mode. Default if specified: 28
      --rtd3 [VALUE]        Setup PCI-Express Runtime D3 (RTD3) Power Management on Hybrid mode. 
                        Available choices: 0, 1, 2, 3. Default if specified: 2
      --reset-sddm          Restore default Xsetup file
      --reset               Revert changes made by EnvyControl
      --verbose             Enable verbose mode

for detailed help and info on how to use this awesome tool read the detailed wiki at the source:

[https://github.com/bayasdev/envycontrol/blob/main/README.md](https://github.com/bayasdev/envycontrol/blob/main/README.md)

EnvyControl [Frequently-Asked-Questions](https://github.com/bayasdev/envycontrol/wiki/Frequently-Asked-Questions) have also a lot of good information.

Thank’s [@VictorBayas](https://github.com/bayasdev) at the telegram chat to hint me on his helpful tool perfectly fitting for EndeavourOS indeed!