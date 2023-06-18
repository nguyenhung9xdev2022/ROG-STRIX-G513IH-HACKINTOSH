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

### Not Working

- Unable to wake up after a long period of sleep

- NVIDIA dGPU

- Third-party browsers cannot use hardware acceleration normally (Edge)

- Keyboard backlight control, Fn shortcut keys (the driver did not work properly)

- VCN (Video/Picture Hardware Encoding and Decoding) still has problems, can be used but not guaranteed, turned off by default, to enable, please add `-nredvcn` to `boot-args`, please move to NootedRed page for the latest progress

## Credit

https://github.com/NootInc/NootedRed

https://github.com/zabdottler/Lenovo-Yoga-16S-hackintosh

https://github.com/AlphaNecron/Zephyrus-G14-GA401QH-EFI

https://github.com/b00t0x/ROG-Zephyrus-G14-GA402-Hackintosh
