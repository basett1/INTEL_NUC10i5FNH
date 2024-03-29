<div align="center">
  
[![](https://img.shields.io/badge/Repositories-basett1-informational?style=flat&logo=apple&logoColor=white&color=9debeb)](https://github.com/basett1?tab=repositories)
[![](https://img.shields.io/badge/Gitter%20Ice%20Lake-Chat-informational?style=flat&logo=gitter&logoColor=white&color=ed1965)](https://gitter.im/ICE-LAKE-HACKINTOSH-DEVELOPMENT/community)
[![](https://img.shields.io/badge/Gitter%20HL%20Community-Chat-informational?style=flat&logo=gitter&logoColor=white&color=ed1965)](https://gitter.im/Hackintosh-Life-IT/community)
[![](https://img.shields.io/badge/Telegram-HackintoshLifeIT-informational?style=flat&logo=telegram&logoColor=white&color=5fb659)](https://t.me/HackintoshLife_it)
[![](https://img.shields.io/badge/Facebook-HackintoshLifeIT-informational?style=flat&logo=facebook&logoColor=white&color=3a4dc9)](https://www.facebook.com/hackintoshlife/)
[![](https://img.shields.io/badge/Instagram-HackintoshLifeIT-informational?style=flat&logo=instagram&logoColor=white&color=8a178a)](https://www.instagram.com/hackintoshlife.it_official/)
[![](https://img.shields.io/badge/PayPal-HackintoshLifeIT-informational?style=flat&logo=paypal&logoColor=white&color=00B2EE)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RWBVVWL8H9JC2&source=url)

</div>

# 23 APRIL 2021 ADDED NEW EFI. I'LL UPDATE THE REPO WITH THE NEW INFOS IN FEW DAYS

# USE THIS [REPO](https://github.com/mbarbierato/Intel-NUC10i3FNK) FROM OUR WORKGROUP, IS UPDATED AND MAINTAINED BY [MASSIMILIANO](https://github.com/mbarbierato).


# INTEL NUC10i5FNH Hackintosh

![modello](./Infos/pc.png)

EFI for Intel NUC10i5FNH with OpenCore bootloader

![descrizione](./Infos/infomac.png)

### Computer Spec:

| Component        | Brank                              |
| ---------------- | ---------------------------------- |
| CPU              | Intel i5 10210U                    |
| iGPU             | Intel® UHD Graphics                |
| Lan              | Intel I219V10                      |
| Audio            | Realtek ALC256                     |
| Ram              | 32 Gb DDR4 2666 Mhz                |
| Wifi + Bluetooth | INTEL Wi-Fi AC9462                 |
| NVMe             | SAMSUNG 970 EVO PLUS 250 GB (MACOS)|
| SSD              | SAMSUNG 860 EVO 1TB (WINDOWS)      |
| SmBios           | MacMini 8,1                        |
| BootLoader       | OpenCore                           |

## Peripherals & Benchmarks

![infohack](./Infos/peripherals.png)
![CPU](./Infos/cputest.png)
![GPU-metal](./Infos/metal.png)
![GPU-opencl](./Infos/opencl.png)

### What works and What doesn't or WIP:

- [x] Intel UHD iGPU HDMI Output / USB C Output Video
- [x] ALC256 Native Combojack headphones
- [x] ALC256 HDMI Audio Output
- [x] All USB Ports
- [x] SpeedStep / Sleep / Wake
- [x] Wi-Fi and Bluetooth
- [x] Intel LAN
- [x] Thunderbolt 3
- [x] NVRAM
- [x] ALC256 Combojack microphone
- [x] ALC256 jack LINE-IN
- [x] SD card reader 

## CFG Unlock 

N.B. this procedure is very risky.
Any responsibility for this function is discharged to those who perform it.
Be very careful when making this change.

Let's start by downloading the file [RU.efi](./CFGunlock/RU.efi)

We format the USB in FAT32 format.
We copy the RU.efi file in the USB Root.
We enable the UEFI Shell parameter from the BIOS.
We attach the USB stick to the PC and start the UEFI Shell by pressing F10.

If everything is correct, we will come to this screen:

![rootshell](./CFGunlock/rootshell.jpg)

We will then have to find our ROOT, which in my case is FS1
So now we will write "fs1:"
Then we will write "ls"

We will find ourselves in this situation at this point:

![rootshellRU](./CFGunlock/rootshell_RU.jpg)

Then type RU.efi and this mask will appear.

![RU](./CFGunlock/RU.jpg)

Press ALT + ì to remove the popup on the screen.
At this point, on the keyboard, press PagDOWN to scroll the list.

We need to get to the "CPUSetup"

And click ENTER to access the section.

![CPUSetupRU](./CFGunlock/CPUSetupRU.jpg)

Now we have to go down to the value "0030 - 0E

![CPUSetupeMODRU](./CFGunlock/valoremod1.jpg)

Now let's change the value 01 to 00

The correct version will be the following:

![CPUSetupeMODOKRU](./CFGunlock/valoremodok.jpg)

Now to save we press CTRL + W

If everything went well, we will have this screen with a red popup

![CPUSetupeMODSAVERU](./CFGunlock/valoremodsave.jpg)

## BIOS config

To start, choose "Load Defaults" (choose from the menu or press F2 in the BIOS setup).

BIOS version FNCML357.0050 (latest)

* ## Advanced
* ATA Mode Selection -> AHCI
* ## Video
* IGD Minimum Memory -> 128MB
* IGD Aperture Size -> 256MB
* IGD Primary Video Port -> Auto
* ## Boot
* Secure Boot -> Disabled
* UEFI Boot -> Checked
* Legacy Boot -> Unchecked
* Fast Boot -> Unchecked
* ## Power
* Secondary Power Settings
* Deep S4/S5 -> Off
* Wake on Lan from S4/S5 -> Stay Off
* Wake System from S5 -> Off
* Wake From Thunderbolt Device -> Off

### Special Config:


See [ioreg](./MacMini.ioreg) for more clarification

## Credits

- [Apple](https://apple.com) for macOS;
- [Acidanthera](https://github.com/acidanthera) for OpenCore and all the lovely hackintosh work.
- [Dortania](https://github.com/dortania)
- [Hackintoshlifeit](https://github.com/Hackintoshlifeit)
- [PIERPAOLO](https://github.com/pierpaolodimarzo) for his desire to learn and the great commitment he has put into this project

# If you need help please contact us on [Telegram](https://t.me/HackintoshLife_it) or [Web](https://www.hackintoshlife.it/)
