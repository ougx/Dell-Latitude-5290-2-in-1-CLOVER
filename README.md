# Dell-Latitude-5290-2-in-1-Clover

## Specifics

- CPU : Intel® Core™ i5-8350U Processor (6M Cache, up to 3.60 GHz)
- GRAPHIC : Intel® UHD Graphics 620
- SOUND : REALTEK ALC3253(ALC225)
- DISPLAY : 12.3 INCH 1920 X 1280(WUXGA+) 3:2 10 POINTS MULTI TOUCH
- MEMORY : SAMSUNG LPDDR3 8GB 1867MHZ (4GB * 2 DUAL CHANNEL)
- SSD : TOSHIBA KXG60ZMV256G 256GB (M.2 PCIE 3.0 X2 NVME/SATA3 SLOT * 2 ; 2280, 2242/2230)
- WIRELESS : BCM943602BAED(DW1830) (EMPTY WWAN SLOT * 1)
- EXTERNAL PORT & SLOT : USB 3.2 Gen 1  * 2, TYPE C * 2 (USB 3.2 Gen 1, DISPLAYPORT, POWER DELIVERY), I2C PORT * 1, AUDIO JACK * 1, SMART CARD READER * 1 USIM SLOP * 1, LOCK SLOT *1
- BATTERY : 42WHR
- WINDOWS 10 PRO


## Bios/Clover Bootloader/macOS Version

- Bios : 1.7.3
- Clover Bootloader : v2.4k r4920 (or Higher)
- macOS : Above 10.14


## Bios Setup

- Load Optimized Defaults


## DSDT Patch

- [misc] Remove _PRW from LID
- [sys] AC Adapter Fix
- [sys] Add IMEI
- [sys] Fix _WAK Arg0 v2
- [sys] Fix Mutex with non-zero SyncLevel
- [sys] Fix PNOT/PPNT
- [sys] HPET Fix
- [sys] Fix IRQ Fix
- [sys] OS Check Fix (Windows 10)
- [sys] RTC Fix
- [sys] Shutdown Fix
- [sys] Shutdown Fix v2
- [sys] SMBUS Fix
- [GPIO] GPIO Controller Enable [SKL+]


## Drivers64UEFI

- ApfsDriverLoader-64.efi
- AptioMemoryFix-64.efi
- FSInject-64.efi
- HFSPlus.efi
- VirtualSmc.efi


## Kexts

- AirportBrcmFixup.kext
- AppleALC.kext
- BrcmFirmwareRepo.kext
- BrcmPatchRAM2.kext
- EFICheckDisabler.kext
- Lilu.kext
- NullEthernet.kext
- SMCBatteryManager.kext
- SMCLightSensor.kext
- SMCProcessor.kext
- SMCSuperIO.kext
- USBPorts.kext    -    Hackintool generated, HS / SS port matching and realignment
- VirtualSMC.kext
- VoodooI2C.kext
- VoodooI2CHID.kext
- VoodooPS2Controller.kext    -    Add 'Info.plist - IOKitPersonalities - IONameMatch - Item 0 - PNP044E'
- WhateverGreen.kext


## What Works

***Graphics/Display***
- Intel® UHD Graphics 620 QE/CI, 2048MB Vram
- Type C DP 2 ports Video / Audio output Hot Swap
- Brightness control
- Lid Close Sleep with Magnetic Travel Keyboard
- I2C touch screen Up to 4 points Gesture action (recognized as Magic Trackpad 2)

***Audio***
- Built-in speaker
- Built-in microphone
- Line input
- DP Audio Output

***Input***
- I2C touch screen Up to 4 points Gesture action (recognized as Magic Trackpad 2)
- I2C Keyboard (Magnetic Travel Keyboard) with Backlight
- Touchpad (Magnetic Travel Keyboard, recognized as mouse)
- Volume button, window button, power button

***Power Management***
- CPU/Speed Step
- Battery
- Type C PD 2 Ports Charging
- Sleep/Wake

***Storage Device***
- Full Size/ Type C USB 2.0, 3.0 Hot Swap
- m.2 NVME 2280/ m.2 SATA 2280 1 Slot and m.2 NVME 2230(2242)/ m.2 SATA 2230(2242) 1 Slot

***Wireless communication***
- iMessage/FaceTime/App Store
- Wi-Fi, Bluetooth, Airdrop, Continuity with macOS compatible wireless card


## Issues
- If power is connected and the device is connected to Full size USB, it wakes up immediately after sleeping.
Fixed after designating the port as internal port
As a result, if you connect a 3.0 device to the USB, it will be recognized as an internal disk icon.

- When the battery is in use, the disk not ejected properly after sleeping
Fixed with SafeSleepUSB.app or Jettison.app

- WWAN card, LTE available as USIM but not tested yet

- MicroSD slot not working properly
If you use Sinetek-rtsx.kext, you can use HFS + formatted SD card, but there are still some problems

- PCIE front and rear camera (AVStream2500, OV series camera) not recognized

- Compared to Windows, White Noise occurs a little on speakers

- In case of new installation, Magic Trackpad 2 touch screen via VoodooI2C, VoodooI2CHID is not immediately recognized and suddenly recognized after specific setup / injection event after personal setting
Once recognized, the touch screen will not be lost
After recognizing the touch screen, the touch pad of the Magnetic Travel Keyboard is disabled, which can be activated using Karabiner

## Screenshots

![01SystemOverview](./images/01SystemOverview.png)

![02SystemDisplay](./images/02SystemDisplay.png)

![03VideoProc](./images/03VideoProc.png)

![04IntelPowerGadget](./images/04IntelPowerGadget.png)

![05Geekbench_CPU](./images/05Geekbench_CPU.png)

![06Geekbench_GPU](./images/06Geekbench_GPU.png)

![07USBOrigin](./images/07USBOrigin.png)

![08USBEdit](./images/08USBEdit.png)