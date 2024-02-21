# OpenCore Z490-E (Comet Lake)
OpenCore Hackintosh configuration example for the **ASUS ROG STRIX Z490-E GAMING** motherboard with an Intel Core i9-10900K. 

<img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/af012dbc-dd39-474e-bb11-3f5ed0682cd3" alt="ultimate-macOS-KVM" width="1400"/>
<p align="center"><i>macOS Sonoma running on native hardware.</i></p>

<br>

## What works?

### macOS

- [x] macOS Sonoma

### Hardware

- [x] Dedicated GPU (RX 5700 XT)
- [x] iGPU (UHD 630)
- [x] NVMe drives
- [x] SATA drives
- [x] USB 3.1 (XHCI)
- [x] Ethernet
- [ ] Wi-Fi
- [ ] Bluetooth
- [x] Camera
- [x] Sound
  
### Software

- [ ] AirDrop
- [x] iMessage
- [x] FaceTime
- [ ] Unlock with Apple Watch
- [x] QE/CI graphics acceleration
- [x] Metal support
- [x] Temperature sensors
- [x] Sleep / Wake
- [x] RTC (protection)
- [x] Hyperthreading
- [x] Virtualisation
- [x] Memory bank configuration
  
<br>

***

## Problems

<ul>
<li><b>Wi-Fi and Bluetooth</b></li>
Having worked on my virtualised instances of macOS Catalina and macOS Monterey, I'm still unable to get stable Wi-Fi or Bluetooth support on macOS Sonoma with <code>AirportItlwm.kext</code>. Wi-Fi networks will often connect but crash the entire system after a minute or two. Strangely, Wi-Fi worked flawlessly in macOS Recovery, and I even used it to install macOS as I had not patched the I225-V ethernet yet.

<br>

<li><b>AirDrop</b></li>
As this relies on Wi-Fi and Bluetooth connectivity, while shown as available throughout the system, it sadly does not work at this time. As a workaround, I have been using <a href="https://github.com/localsend/localsend">LocalSend</a>, a cross-platform alternative.

<br>

<li><b>Unlock with Apple Watch</b></li>
Again, as a Wi-Fi and Bluetooth reliant feature, unlocking with Apple Watch doesn't work either right now.

<br>

<li><b>HDMI on Intel UHD 630 (iGPU)</b></li>
Despite trying multiple different framebuffers and connection patches, I cannot get the HDMI output to work from the iGPU. DisplayPort works fine. HDMI also works fine on the dedicated GPU. 

<br>

<li><b>BIOS POSTs in "Safe Mode"</b></li>
After booting macOS, the next reboot always caused the BIOS to POST in a "safe mode" with the message <code>The system has POSTed in safe mode.</code> displayed. This is because macOS tries to write to disallowed areas of the RTC. This was fixed easily, by using <a href=https://dortania.github.io/OpenCore-Post-Install/misc/rtc.html>this guide</a>.

</ul>


***

## System

The specs of my main system that the OpenCore configuration targets.

| **Motherboard** |                  ASUS ROG STRIX Z490-E GAMING                 |
|-----------------|:-------------------------------------------------------------:|
| **CPU**         |                      Intel Core i9-10900K                     |
| **Chipset**     |                             Z490-E                            |
| **Generation**  |                           Comet Lake                          |
| **Memory**      |                       64 GB DDR4 3200MHz                       |
| **Storage**     |                     500 GB WD Blue NVMe M.2                    |
| **GPU**         | Intel UHD 630<br>AMD Radeon RX 5700 XT<br>~~NVIDIA GTX 3090~~ * |
| **NIC**         |                  Intel I225-V 2.5Gb Ethernet                  |

> [!NOTE]
> The system contains an **NVIDIA RTX 3090** graphics card, but it has been intentionally disabled through a custom SSDT (``SSDT-GPU-DISABLE.aml``).


***

## SMBIOS

### iMac20,2

Due to the system having a 10-core i9-10900K, the CPU model is similar to the one found in an **iMac 5K 27-inch (i9, 2020)**, with a model identifier of ``iMac20,2``.

***

## ACPI

SSDTs used:
- SSDT-AWAC
- SSDT-EC-USBX-DESKTOP
- SSDT-GPU-DISABLE
- SSDT-PLUG-DRTNIA
- SSDT-RHUB
- SSDT-RX5700XT [⎋](https://www.tonymacx86.com/threads/amd-radeon-performance-enhanced-ssdt.296555/)

> [!IMPORTANT]
> ``SSDT-GPU-DISABLE`` is a custom SSDT used to disable an **NVIDIA RTX 3090** graphics card. It should be removed if config is being used on a different system.
>
> ``SSDT-RX5700XT`` is an *EXPERIMENTAL* custom SSDT used to enhance the performance of an **AMD RX 5700 XT** graphics card. It should be removed if config is being used on a different system.
  
***

## DeviceProperties

The following tables display the added PCI devices and their child keys.


### PciRoot(0x0)/Pci(0x2,0x0)

Intel UHD 630 Graphics

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| AAPL,ig-platform-id      |   Data   | ``0000923E`` |
| device-id                |   Data   | ``923E7000`` |
| framebuffer-fbmem        |   Data   | ``00009000`` |
| framebuffer-patch-enable |   Data   | ``01000000`` |
| framebuffer-stolenmem    |   Data   | ``00003001`` |
| framebuffer-unifiedmem   |   Data   | ``00000080`` |
| hda-gfx                  |  String  |   onboard-1  |

> [!WARNING]
> The current configuration of the **Intel UHD 630** is not stable and is still being tweaked.

<br>

### PciRoot(0x0)/Pci(0x1C,0x1)/Pci(0x0,0x0)

Intel I225-V 2.5Gb Ethernet

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| device-id                |   Data   | ``F2150000`` |

> [!NOTE]
> The **Intel I225-V** requires a special patch mentioned in [Kernel](https://github.com/Coopydood/OpenCore-Z490E-CometLake/?tab=readme-ov-file#patches).

<br>

### PciRoot(0x0)/Pci(0x1b,0x0)

Apple ALC

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| AAPL,ig-platform-id      |   Data   | ``0300220D`` |
| layout-id                |   Data   | ``01000000`` |


***

## Kernel

The following shows the kernel configuration.

### Kexts

Kexts used:
- Lilu
- WhateverGreen
- AirportItlwm
- IntelBluetoothFirmware
- NVMeFix
- RadeonSensor
- VirtualSMC
- AppleALC
- BlueToolFixup
- IntelBTPatcher
- SMCProcessor
- SMCRadeonGPU
- SMCSuperIO
- FeatureUnlock
- RTCMemoryFixup
- Z490E_USBMap

> [!NOTE]
> ``Z490E_USBMap.kext`` is a custom kext containing the USB mappings of my ASUS ROG STRIX Z490-E GAMING motherboard ports - your mileage may vary!

### Patches

Intel I225-V 2.5Gb Ethernet

| **Key**     | **Type** |                **Value**                |
|-------------|:--------:|:---------------------------------------:|
| Arch        |  String  |                   Any                   |
| Base        |  String  |    __Z18e1000_set_mac_typeP8e1000_hw    |
| Comment     |  String  |               I225-V patch              |
| Count       |  Number  |                    1                    |
| Enabled     |  Boolean |                   True                  |
| Find        |   Data   |               ``F2150000``              |
| Identifier  |  String  | com.apple.driver.AppleIntelI210Ethernet |
| Limit       |  Number  |                    0                    |
| Mask        |   Data   |                                         |
| MaxKernel   |  String  |                  20.4.0                 |
| MinKernel   |  String  |                  19.0.0                 |
| Replace     |   Data   |               ``F3150000``              |
| ReplaceMask |   Data   |                                         |
| Skip        |  Number  |                    0                    |

***

## Security

**SecureBootModel 》** Default

**Vault 》** Optional

***

## NVRAM

Contents stored in NVRAM.

<br>

### 4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14

| **Key**                | **Type** |   **Value**  |
|------------------------|:--------:|:------------:|
| DefaultBackgroundColor |   Data   | ``00000000`` |

<br>

### 4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102

| **Key**       | **Type** | **Value** |
|---------------|:--------:|:---------:|
| rtc-blacklist |   Data   |           |

<br>

### 7C436110-AB2A-4BBB-A880-FE41995C9F82

| **Key**                   | **Type** |                                    **Value**                                   |
|---------------------------|:--------:|:------------------------------------------------------------------------------:|
| ForceDisplayRotationInEFI |  Number  |                                        0                                       |
| SystemAudioVolume         |   Data   |                                     ``46``                                     |
| boot-args                 |  String  | -v keepsyms=1 debug=0x100 alcid=1 agdpmod=pikera igfxgl=1 forceRenderStandby=0 |
| csr-active-config         |   Data   |                                  ``00000000``                                  |
| prev-lang-diags:kbd       |   Data   |                                 ``656E2D47 42``                                |
| prev-lang:kbd             |   Data   |                               ``656E2D47 423A32``                              |
| run-efi-updater           |  String  |                                       No                                       |
| StartupMute               |   Data   |                                     ``00``                                     |

***

## UEFI

Drivers in use:

- HFSPlus
- NVMExpressDxe
- OpenCanopy
- OpenRuntime
- ResetNvramEntry
  
***

## Gallery

<img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/9dd5dda0-92c3-4cc7-a7e4-3aab714671db" width="30%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/4694291b-adcd-4847-99e2-a4f89c9c1ac9" width="60%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/569407bd-0893-4974-82f0-ff669d317783" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/c3ec115d-fe2c-4382-9fa3-d73d3c10cfd2" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/4ef63542-a628-4a97-a598-7474bf151414" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/7fd1683a-b389-4d5c-a8c6-106279a50625" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/bc47bf2e-0879-4584-bab1-f039f38f73c0" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/85bd9aee-1a09-4a16-b121-5bc96f21becd" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/85dd1971-efb5-47f0-a73b-459099d383bb" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/d455d5f8-830e-4fb5-9f08-30d65fcce1db" width="45%"></img>

***

## Disclaimer

This repo is simply a dump of my current and up-to-date OpenCore stuff that I use on my machine. 

Feel free to use it as an example and modify it however you'd like, but please don't expect it to "just work" - because it won't.

***

## Contribute!

If you've found a way to make the configuration better, or have solved issues outlined in the **Problems** section, please share your changes on GitHub for us all to use! Thank you!

***

<p align="center">
  <img src="https://github.com/Coopydood/ultimate-macOS-KVM/assets/39441479/39d78d4b-8ce8-44f4-bba7-fefdbf2f80db" width="10%"> </img>
</p>
