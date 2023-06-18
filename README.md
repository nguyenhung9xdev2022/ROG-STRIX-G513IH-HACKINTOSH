# ROG Strix G513 (G513IH) Hackintosh [WIP]
Hackintosh for ASUS ROG STRIX G513 (G513IH) 2021.

<img width="1813" alt="Screen Shot 2023-06-18 at 09.30.39" src="https://i.imgur.com/PyrihFI.png">

## Specifications

| Component                  | Model                 |
| :------------------------- | :-------------------- |
| CPU                        | AMD Ryzen 7 4800H     |
| Integrated Graphics        | AMD Radeon Vega 7     |
| Graphics Card              | NVIDIA Gerfoce 1650   |
| WiFi/Bluetooth             | Intel AX210           |
| Hard Disk                  | Intel SSDPEKNU512GZ and Samsung 970 Evo Plus |
| Keyboard                   | PS2 controller        |
| Touchpad                   | I2C HID               |
| Audio/3.5mm Headphone Jack | ALC256                |
| Memory                     | DDR4 3200MHz 16G      |

## Description
- The available versions for this EFI are BigSur
- The model information has been deleted, please generate and replace it by yourself
- OpenCore version: 0.9.3
- It is recommended to use [UMAF](https://github.com/DavidS95/Smokeless_UMAF/) tool to increase vram, at least 1G is recommended 2G.
- This EFI was made based on the 2021 model, but it should be compatible with the 2022 model

## Warning

- When installing or updating the system, pay attention to disable the `NootedRed` driver in `config.plist`, otherwise the installation process will get stuck in the progress bar and cannot be installed normally
- When installing or updating the system, please disable the `USBMap` driver in `config.plist` or customize it yourself
  
### Current status

- CPU

  - Energy management is done using [AMD Power Gadget](https://github.com/trulyspinach/SMCAMDProcessor)

- IGPU

  - Hardware acceleration has some issues, waiting for updated driver from [NootedRed](https://github.com/NootInc/NootedRed)

- WiFi/Bluetooth

- Apple ID & iMessages & iCloud

- Touchpad and keyboard

- 3.5mm headphone audio output

- NVME SSD

- Metal acceleration

- Volume shortcut keys

- LAN

### Not Working

- Unable to wake up after a long period of sleep

- NVIDIA dGPU

- Third-party browsers cannot use hardware acceleration normally (Edge)

- Keyboard backlight control, Fn shortcut keys (the driver did not work properly)

- VCN (Video/Picture Hardware Encoding and Decoding) still has problems, can be used but not guaranteed, turned off by default, to enable, please add `-nredvcn` to `boot-args`, please move to NootedRed page for the latest progress

## Know Your EFI

### ACPI

| SSDT          | Function                                                     |
| :------------ | :----------------------------------------------------------- |
| SSDT-PLUG-ALT | Used for MacOS to recognize CPU, must-have                   |
| SSDT-EC       | Fakes a EC for MacOS, must-have                              |
| SSDT-HPET     | Solves IRQ conflicts, must-have                              |
| SSDT-USBX     | USB power management, must-have                              |
| SSDT-XOSI     | ACPI function of MAC and WIN, dual systems must-have.        |
| SSDT-ALS0     | Provided by NootedRed, used for screen brightness adjustment |
| SSDT-PNLF     | Provided by NootedRed, used for screen brightness adjustment |

### Kexts

| Kext                       | Function                                                     |
| :------------------------- | :----------------------------------------------------------- |
| AMDRyzenCPUPowerManagement | AMD CPU power management                                     |
| AppleALC                   | Audio driver                                                 |
| AppleMCEReporterDisabler   | Disables AppleIntelMCEReporter to avoid errors on AMD CPU devices |
| Lilu                       | Must-have                                                    |
| NVMeFix                    | NVMe hard disk power management                              |
| RestrictEvents             | CPU renamer                                                  |
| SMCAMDProcessor            | Subsidiary of AMDRyzenCPUPowerManagement                     |
| SMCBatteryManager          | Battery management                                           |
| SMCLightSensor             | Used for ambient light sensors on laptops                    |
| USBToolBox                 | USB customization                                            |
| USBMap                     | USB customization, not universal, need to customize by yourself |
| VirtualSMC                 | Must-have                                                    |
| VoodooI2C                  | Touchpad or touchscreen driver                               |
| VoodooI2CHID               | Touchpad or touchscreen driver                               |
| AirportItlwm               | Intel network card driver, note that different systems have different kexts |
| IntelBluetoothFirmware     | Bluetooth driver                                             |
| IntelBluetoothInjector     | Bluetooth driver                                             |
| IntelBTPatcher             | Bluetooth driver                                             |
| AmdTscSync                 | CPU frequency synchronization, in conjunction with kernel patches, to control power consumption |

## Credit

https://github.com/NootInc/NootedRed

https://github.com/zabdottler/Lenovo-Yoga-16S-hackintosh

https://github.com/AlphaNecron/Zephyrus-G14-GA401QH-EFI

https://github.com/b00t0x/ROG-Zephyrus-G14-GA402-Hackintosh
