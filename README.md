![image](https://github.com/user-attachments/assets/ad882ca7-a637-47aa-bfc2-5c65c82e7dc7)


# DeMoN


The DeMoN is hobby cartridge that was developed as a collaboration between three geeks who have a very healthy obsession with the Amiga, and skilled in both software and hardware development alike. It can be described as an Action Replay on steroids.

This project will give a brief introduction about DeMoN, how it came to be, its features and plans so that you can build your own.

## Contents

[A Brief History](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#a-brief-history) (the boring bit. In fact, skip over this bit).

[DeMoN features](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#features)

[Build Your Own](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#build-your-own-demon-cartridge)

* [Firmware](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#firmware) 
* [Cartridge Case](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#cartridge-case)
   
[Related Projects](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#related-projects)



## A Brief History

In a nutshell...

Since the 1990s I've been a massive fan of the Action Replay III cartridge (AR3) for the Amiga. Whenever I played games on the Amiga, the AR3 was always plugged in, and I had more fun finding infinite lives, infinite weapons, level skips, etc. I learnt so much from that device as well as other ways to use it. I wanted to have an AR3 with my own tools, but this was an impossibility for me at the time.

Fast forward a few years....

I learnt about a project where somebody (na103) had reverse engineered the original AR3 cartridge. The project can be found [here](https://github.com/na103/ar3). I built my own, reverse engineered the firmware, added my tool and the project was a success.

Shortly after this I learnt that another individual (REbEL) had reverse engineered the Action Replay III firmware, the Aktion Replay IV "firmware", and combined all the tools together into a ROM binary that worked as a "cartridge" for WinUAE (known as the Action Replay V). I got in touch to see if he wanted it working on real hardware and he agreed. We invited na103 to join us and and a collaborative hobby ensured.

Firmware evolved as extra tools were added which led the hardware to evolve too. And as the hardware evolved, so did the firmware.

And the healthy vicious circle continued!

DeMoN was born.


## Features

So what is so special about the DeMoN cartridge, and how does it compare against an original Action Replay 3 cartridge?
In a nutshell:

| FEATURE | Action Replay 3 | DeMoN Cartridge |
|---------|----------|----------|
| ROM size | 256kb | 256kb |
| ROM type | Static | Flashable |
| RAM size | 40kb | 1mb |
| Number of Tools | Loads | Even more! |
| Ramdisk? | No | Optional |
| Detection | Always hidden | Can be visible |
| Ability toggle? | Always On | Optional |

Other features of the DeMoN cartridge:

* **Backwards Compatibility** - The DeMoN firmware has also been designed to work with the original Action Replay 3 hardware and it is also supported in WinUAE. 
* **DeMoN Detection** - The user has the option whether the DeMoN can be "seen" by the Amiga, peripherals etc. **IMPORTANT! Don't toggle this jumper whilst powered on!**
* **DeMoN Ability** - DeMoN has the option to be "On" or "Off". **IMPORTANT! Don't toggle this jumper whilst powered on!**
* **Keyboard Layouts** - New keyboard layouts to cater for the United Kingdom and Italian language have been added. 
* **Serial Communication** - The DeMoN allows serial communications, but this is currently a Work In Progress. Tests have successfully sent a file from Amiga to PC, but not yet the other way. 
* **Extra Tools** - The DeMoN cartridge contains all the commands from the Action Replay 3 cartridge and the Aktion Replay 4 software. Further to this, several bugs have been fixed. Too many to list here, but a few DeMoN specific commands that have been added are:
  * flash: Used to upgrade firmware.
  * r: This is the ramdisk. It can be accessed using R: as the drive in any of the file tools within the DeMoN console.
  * savecfg: Save your current config to the cartridge.
  * resetcfg: Set config to default.
  * axfer: Sets up the Amiga to use AmigaXfer without the need of a floppy.
  * ...plus many, many more!

For an up-to-date list of current tools and commands, see the [Complete Command List](https://github.com/dmcoles/ActionReplay5/blob/main/Complete%20Command%20List.txt).


## Build Your Own DeMoN Cartridge.

If you want to build your own then you will need the following:
* Soldering Iron
* Solder
* Tweezers
* ESD wrist strap
* A flat surface to solder on (such as a soldering mat on a desk, NOT the arm of a sofa or your partner's back)
* Other soldering related tools and devices, you know the drill.

In this project you can find the KiCad files that are used to build the PCBs for the project, along with the [Bill of Materials](https://github.com/gerbilbyte/DeMoN/tree/main/Kicad) (BOM) required for each build.
To make things even easier, Gerber files have also been included that you can use to send directly to your favourite freindly, or unfriendly, PCB manufacturer.

[![image](https://github.com/user-attachments/assets/bd057ae8-4cc5-489a-a50f-bb349fded169)
Follow this link to build the DIP32 ROM version of DeMoN](https://github.com/gerbilbyte/DeMoN/tree/main/Kicad/DeMoN-Flash)

[![image](https://github.com/user-attachments/assets/6ff6edc8-36b6-45ae-bedc-bced24ccb2cd)
Follow this link to build the PLCC32 ROM version of DeMoN](https://github.com/gerbilbyte/DeMoN/tree/main/Kicad/DeMoN-Flash-J)

I actually don't need to write any more about how to build one, the rest is quite straight forward.


### Firmware.

Once built, your cartridge will now need firmware.

This repo does not contain firmware, but it does contain a patch file that can be used to patch the original Action Replay III (version 3.17) ROM.
Tools are included with instructions in this repo on how to patch an Action Replay III ROM file.

DeMoN uses Action Replay firmware, including modified firmware and homebrews. The latest version of the DeMoN (Action Replay 5) firmware can be found on REbEL's repo that can be found [here](https://github.com/dmcoles/ActionReplay5).


### Cartridge Case.
The case:

![image](https://github.com/user-attachments/assets/ff7e556c-8815-498d-aae7-fc6ca6019e7b) 

Artist's impression of how fantastic the case can look:

![image](https://github.com/user-attachments/assets/56f61f51-c88e-4a32-9cb2-2bfe68079897)


Basing the case on Fongo's [Action Replay 3 Replica case](https://www.printables.com/model/1037033-amiga-action-replay-3-replica-case), modifications have been made to cater for the jumpers on the DeMoN.


## Related Projects.

**REbEL**, the author of the DeMoN firmware has an open project (Action Replay 5) that can be found here. This repo contains firmware that can be used in WinUAE as well as DeMoN. These will be up-to-date and more stable, including source code. His main github page can be found [here](https://github.com/dmcoles).

**na103**, who reverse engineered the Action Replay 3, has posted his project here. This repo contains several versions of the Action Replay 3 for different ROM footprints. His main github page can be found [here](https://github.com/na103/ar3).

**Fongo**, the creator of the Action Replay Replica Case. His Printables page can be found [here](https://www.printables.com/@fongo2k_2502418).
