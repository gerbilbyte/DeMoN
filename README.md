![image](https://github.com/user-attachments/assets/ad882ca7-a637-47aa-bfc2-5c65c82e7dc7)


# DeMoN


The DeMoN is hobby cartridge that was developed as a collaboration between three geeks who have a very healthy obsession with the Amiga, and skilled in both software and hardware development alike. It can be described as an Action Replay on steroids.

![image](https://github.com/user-attachments/assets/98fd00ce-8cad-4ac1-be52-16d5208ba2aa)

This project will give a brief introduction about DeMoN, how it came to be, its features and plans so that you can build your own.

## Contents

[A Brief History](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#a-brief-history) (the boring bit. In fact, skip over this bit).

[DeMoN features](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#features)

[Build Your Own](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#build-your-own-demon-cartridge)

* [Firmware](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#firmware) 
* [Flashing](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#flashing) 
* [Cartridge Case](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#cartridge-case)
   
[Related Projects](https://github.com/gerbilbyte/DeMoN/blob/main/README.md#related-projects)



## A Brief History

In a nutshell...

Since the 1990s I've been a massive fan of the Action Replay III cartridge (AR3) for the Amiga. Whenever I played games on the Amiga, the AR3 was always plugged in, and I had more fun finding infinite lives, infinite weapons, level skips, etc. I learnt so much from that device as well as other ways to use it. I wanted to have an AR3 with my own tools, but this was an impossibility for me at the time.

Fast forward a few years....

I learnt about a project where somebody (na103) had reverse engineered the original AR3 cartridge. The project can be found [here](https://github.com/na103/ar3). I built my own, reverse engineered the firmware, added my tool and the project was a success.

Shortly after this I learnt that another individual (REbEL) had reverse engineered the Action Replay III firmware, the Aktion Replay IV "firmware", and combined all the tools together into a ROM binary that worked as a "cartridge" for WinUAE (known as the Action Replay V). I got in touch to see if he wanted it working on real hardware and he agreed. We invited na103 to join us and and a collaborative hobby ensued.

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
* **Serial Communication** - The DeMoN allows serial communications, but this is currently a Work In Progress. Tests have successfully sent and received files between Amiga and PC. 
* **Extra Tools** - The DeMoN cartridge contains all the commands from the Action Replay 3 cartridge and the Aktion Replay 4 software. Further to this, several bugs have been fixed. Too many to list here, but a few DeMoN specific commands that have been added are:
  * flash: Used to upgrade firmware.
  * r: This is the ramdisk. It can be accessed using R: as the drive in any of the file tools within the DeMoN console.
  * savecfg: Save your current config to the cartridge.
  * resetcfg: Set config to default.
  * axfer: Sets up the Amiga to use AmigaXfer without the need of a floppy.
  * rfy, sfy: Send and receive files via Y-Modem (currently a Work In Progress). 
  * ...plus many, many more!

An up-to-date list of current tools and commands will be coming soon.


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

DeMoN uses Action Replay firmware, including modified firmware and homebrews. The latest version of the DeMoN (Action Replay 5) firmware will soon be available on REbEL's GitHub repo.


### Flashing.

#### **Flashing using a chip programmer**

All tools required for flashing can be found in the FirmwareTools folder of this repo.
To prepare the firmware for the flash chips the following steps can be taken:
* Prepare the firmware by using the patchfile and the AR3 image to obtain the firmware:

   ```python3 DeMoNpatcher.py <AR3rom file> <DeMoNpatch file>```

* Split the file to be used for programming the chips. The obtained files are self descriptive:

   ```python3 firmwareSplitter.py <input_file>```

* Power-cycle the Amiga.
And that's it! Enjoy the cartridge! :)


#### **Flashing using the stand-alone flash tool**

All tools required for stand-alone flashing - along with detailed instruction on how to use it - can be found in the Standalone Flash Tool folder of this repo.
But in a nutshell, the process is as follows:
* Set JP1 on the DeMoN to pins 2-3 to make the DeMoN memory visible to the Amiga.
* Set JP2 on the DeMoN to pins 2-3 to functionally deactivate the DeMoN.
* Prepare an Amiga floppy disk that includes a standard bootblock (without starup-sequence), the ar5flasher tool and also the firmware
* Load disk and enter the following command, following any futher on screen instructions:

   ```ar5flasher firmware.rom```

* Power-cycle the Amiga.
And that's it! Enjoy the cartridge! :)


#### **Flashing using the FLASH tool on DeMoN**
All that is needed for this method is the firmware on a floppy disk.
* Set JP1 on the DeMoN to pins 2-3 to make the DeMoN memory visible to the Amiga.
* Copy the firmware onto a floppy, and insert it into the drive.
* Press DeMoN freeze button.
* At the console type in the following command, following any futher on screen instructions:

   ```flash firmware.rom```

   The flashing and verifying will take place. After verifying, the screen will change colour to match one of the following conditions:
  
   Red = Failed flash. An error has happened causing the checksums of the firmware file and the on-board firmware to differ.

   Green = Successful flash!
* Power-cycle the Amiga.
And that's it! Enjoy the cartridge! :)

#### License

This work is licensed under a Creative Commons Attribution 4.0 International License. See [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).



### Cartridge Case.
The case:

![image](https://github.com/user-attachments/assets/43b0c059-f1ed-4a13-a80b-2d65ea440d6b)

Basing the case on Fongo's [Action Replay 3 Replica case](https://www.printables.com/model/1037033-amiga-action-replay-3-replica-case), modifications have been made to cater for the jumpers on the DeMoN.


## Related Projects.

**REbEL**, the author of the DeMoN firmware has an open project (Action Replay 5) that can be found here. This repo contains firmware that can be used in WinUAE as well as DeMoN. These will be up-to-date and more stable, including source code. His main github page can be found [here](https://github.com/dmcoles).

**na103**, who reverse engineered the Action Replay 3, has posted his project here. This repo contains several versions of the Action Replay 3 for different ROM footprints. His main github page can be found [here](https://github.com/na103).

**Fongo**, the creator of the Action Replay Replica Case. His Printables page can be found [here](https://www.printables.com/@fongo2k_2502418).
