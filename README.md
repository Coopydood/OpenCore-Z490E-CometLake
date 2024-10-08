<img align="left" height="150" src="https://github.com/Coopydood/Coopydood/assets/39441479/b54b7098-bc82-4110-8a3e-2c4ed729b1b0">

<img align="left" src="https://github.com/Coopydood/ultimate-macOS-KVM/assets/39441479/8f69f9b9-cf23-4e8b-adf3-95862a23e2ba" height=240 width=1 />

<a href="https://coopydood.github.io/ultimate-macOS-KVM"></a><h3>OpenCore Z490-E (Comet Lake)<br><sub>v1.0.0</sub></h3>

OpenCore Hackintosh configuration example for the **ASUS ROG STRIX Z490-E GAMING** motherboard with an Intel® Core™ i9-10900K. 
<br>

[![GitHub](https://img.shields.io/github/license/Coopydood/OpenCore-Z490E-CometLake?label=Licence&logo=unlicense&logoColor=white&style=for-the-badge)](https://github.com/Coopydood/OpenCore-Z490E-CometLake/blob/main/LICENSE) [![GitHub repo size](https://img.shields.io/github/repo-size/Coopydood/OpenCore-Z490E-CometLake?color=07b55b&label=Size&logo=envoy-proxy&logoColor=white&style=for-the-badge)](https://github.com/Coopydood/OpenCore-Z490E-CometLake) [![Discord](https://img.shields.io/discord/574943603466436628?color=7d86ff&label=Discord&logo=discord&logoColor=white&style=for-the-badge)](https://discord.gg/WzWkSsT)

<br>

***

<img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/af012dbc-dd39-474e-bb11-3f5ed0682cd3" alt="Z490-E Hackintosh" width="1400"/>
<p align="center"><i>macOS Sonoma running on native hardware.</i></p>

<br>

You can also use [this template](https://github.com/Coopydood/OpenCore-Writeup-Template) to make your own writeup for your setup!

<br>

***

## Motherboard

<img align="left" height="150" src="https://dlcdnimgs.asus.com/websites/global/products/tcymjbjbhzloect5/img/z490/kv/hero.png">

<img align="left" src="https://github.com/Coopydood/ultimate-macOS-KVM/assets/39441479/8f69f9b9-cf23-4e8b-adf3-95862a23e2ba" height=180 width=2 />

<h3>ASUS ROG STRIX Z490-E GAMING<br><sub><a href="https://rog.asus.com/uk/motherboards/rog-strix/rog-strix-z490-e-gaming-model/">Product Page</a></sub></h3>

*"The ROG Strix Z490-E Gaming motherboard is designed to cope with the demands of 10th Generation Intel® Core™ processors, with boosted power delivery and an optimised cooling design providing more surface area for heat dissipation."* <br> *<sub>Product description provided by ASUS.</sub>*
<br>

## BIOS

<img align="left" width="120" src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/4670b456-040b-4915-bd5d-6ed63cb4b408">

<img align="left" src="https://github.com/Coopydood/ultimate-macOS-KVM/assets/39441479/8f69f9b9-cf23-4e8b-adf3-95862a23e2ba" height=150 width=2 />

<h3>UEFI BIOS Utility<br><sub>Version 3001 (19/02/2024)</sub></h3>

These are the BIOS settings used with this Hackintosh setup.

|       **Setting**                  |     **Value**    |
|:----------------------------------:|:----------------:|
| **VT-d**                           |    ``Enabled``   |
| **Above 4G Decoding**<sup>1</sup>  |   ``Disabled``   |
| **ReSizeable BAR**<sup>1</sup>     |   ``Disabled``   |
| **Memory Remap**                   |    ``Enabled``   |
| **Primary Output**                 | ``CPU Graphics`` |
| **DVMT PreAlloc Size**             |     ``64MB``     |
| **iGPU Multi-Monitor**             |    ``Enabled``   |

<img align="left" src="https://github.com/Coopydood/ultimate-macOS-KVM/assets/39441479/8f69f9b9-cf23-4e8b-adf3-95862a23e2ba" height=100 width=140 />

<sup>1 </sup>*ReSizable BAR and Above 4G Decoding are disabled to allow for the proper virtualisation of macOS under QEMU/KVM with PCI passthrough.*

<br>

***

## OpenCore

<img align="left" width="100" height="100" src="https://dortania.github.io/docs/latest/Logos/Logo.png">
<img align="left" src="https://github.com/Coopydood/ultimate-macOS-KVM/assets/39441479/8f69f9b9-cf23-4e8b-adf3-95862a23e2ba" height=100 width=2 />
<h3>OpenCore<br><sub>1.0.2</sub></h3>

This is the version of OpenCore used, including bundled files. The included ``config.plist`` targets this version.
<br>


## macOS

<img align="left" width="90" height="90" src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/aa49b5ba-6cca-4dab-bcfc-6bf21909e738">
<img align="left" src="https://github.com/Coopydood/ultimate-macOS-KVM/assets/39441479/8f69f9b9-cf23-4e8b-adf3-95862a23e2ba" height=360 width=2 />
<h3>macOS Sonoma<br></h3>

This is the version of macOS that this OpenCore configuration currently targets. Other versions of macOS that are compatible with it are listed below.<br>

#### Supported

<img align="left" width="35" height="35" src="https://github.com/user-attachments/assets/7b9b72ee-5a89-49b4-ae17-7a188ed533ab"> 
<h5>macOS Sequoia</h5>
<img align="left" width="35" height="35" src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/4829ebb4-ce7f-4ecf-8309-d691c9361f6b"> 
<h5>macOS Ventura</h5>
<img align="left" width="35" height="35" src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/7d341cce-4370-4430-b3d5-bf1868afe4a3"> 
<h5>macOS Monterey</h5>
<img align="left" width="35" height="35" src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/79a7a051-0f5a-419e-8544-b51b1572d3b9"> 
<h5>macOS Big Sur</h5>
<img align="left" width="35" height="35" src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/cd8029e8-c256-4295-9908-37809d64dcfe"> 
<h5>macOS Catalina</h5><br>

***


## What works?

### macOS

- [x] macOS Sequoia
- [x] macOS Sonoma
- [x] macOS Catalina

### Hardware

- [x] Dedicated GPU (RX 5700 XT)
- [x] iGPU (UHD 630)
- [x] NVMe drives
- [x] SATA drives
- [x] USB 3.1 (XHCI)
- [x] Ethernet
- [x] Wi-Fi
- [x] Bluetooth
- [x] Camera
- [x] Sound
  
### Software

- [x] AirDrop
- [x] iMessage
- [x] FaceTime
- [x] Sidecar
- [x] Unlock with Apple Watch
- [x] QE/CI graphics acceleration
- [x] Metal support (Metal 3)
- [x] Temperature sensors
- [x] Sleep / Wake
- [x] RTC (protection)
- [x] Hyperthreading
- [x] Virtualisation
- [x] Memory bank configuration
  
<br>

***

## Problems

### 🎉 ALL MAJOR PROBLEMS HAVE BEEN FIXED!

<br>

<ul>
<li><b><s>HDMI on Intel UHD 630 (iGPU)</s> ‏‏‎ ‏‏‎ ‎‎‏‏‎ ‎ 🎉 FIXED!</b></li>
<s>Despite trying multiple different framebuffers and connection patches, I cannot get the HDMI output to work from the iGPU. DisplayPort works fine. HDMI also works fine on the dedicated GPU.
As a result, the iGPU is being used for internal compute only - which works really well. I do still intend to find the fix though!</s>

> [!TIP]
> This was fixed by using new ``DeviceProperties`` connector patches (mentioned in the DeviceProperties section of this readme!).

> [!NOTE]
> The ``DeviceProperties`` for the UHD 630 iGPU has been updated to support Metal 3!

<br>

<li><b><s>Wi-Fi and Bluetooth</s> ‏‏‎ ‏‏‎ ‎‎‏‏‎ ‎ 🎉 FIXED!</b></li>
<s>Having worked on my virtualised instances of macOS Catalina and macOS Monterey, I'm still unable to get stable Wi-Fi or Bluetooth support on macOS Sonoma with <code>AirportItlwm.kext</code>. Wi-Fi networks will often connect but crash the entire system after a minute or two. Strangely, Wi-Fi worked flawlessly in macOS Recovery, and I even used it to install macOS as I had not patched the I225-V ethernet yet.</s>

> [!TIP]
> This was fixed by using the debug (alpha) version of ``AirportItlwm.kext``.

<br>

<li><b><s>AirDrop </s>‏‏‎ ‏‏‎ ‎‎‏‏‎ ‎ 🎉 FIXED!</b></li>
<s>As this relies on Wi-Fi and Bluetooth connectivity, while shown as available throughout the system, it sadly does not work at this time. As a workaround, I have been using <a href="https://github.com/localsend/localsend">LocalSend</a>, a cross-platform alternative.</s>

> [!TIP]
> This was fixed by two seperate patches;
> - Wi-Fi and Bluetooth fixed
> - Secure Boot model changed from ``Default`` to ``j185f`` 

<br>

<li><b><s>Unlock with Apple Watch</s>‏‏‎ ‏‏‎ ‎‎‏‏‎ ‎ 🎉 FIXED!</b></li>
<s>Again, as a Wi-Fi and Bluetooth reliant feature, unlocking with Apple Watch doesn't work either right now.</s>

> [!TIP]
> This was fixed by two seperate patches;
> - Wi-Fi and Bluetooth fixed
> - Secure Boot model changed from ``Default`` to ``j185f`` 

<br>

<li><b><s>BIOS POSTs in "Safe Mode"</s>‏‏‎ ‏‏‎ ‎‎‏‏‎ ‎ 🎉 FIXED!</b> </li>
<s>After booting macOS, the next reboot always caused the BIOS to POST in a "safe mode" with the message <code>The system has POSTed in safe mode.</code> displayed. This is because macOS tries to write to disallowed areas of the RTC.</s> 

> [!TIP]
> This was fixed by using [using this guide](https://dortania.github.io/OpenCore-Post-Install/misc/rtc.html).

</ul>


***

## System

The specs of my main system that the OpenCore configuration targets.

| **Motherboard** |                  ASUS ROG STRIX Z490-E GAMING                 |
|-----------------|:-------------------------------------------------------------:|
| **CPU**         |                      Intel® Core™ i9-10900K                     |
| **Chipset**     |                             Z490                            |
| **Generation**  |                           Comet Lake                          |
| **Memory**      |                       64 GB DDR4 3200MHz                       |
| **Storage**     |                     500 GB WD Blue NVMe M.2                    |
| **GPU**         | Intel UHD Graphics 630<br>AMD Radeon RX 5700 XT<br>~~NVIDIA RTX 3090~~ * |
| **NIC**         |                  Intel I225-V 2.5Gb Ethernet                  |

> [!NOTE]
> The system contains an **NVIDIA RTX 3090** graphics card, but it has been intentionally disabled through a custom SSDT (``SSDT-GPU-DISABLE.aml``).


### Geekbench Scores

| **Intel Core i9-10900K** 	| **Windows** 	| **Linux** 	| **macOS** 	|
|--------------------------	|-------------	|-----------	|-----------	|
| Single Core              	| 1,694       	| 1,936     	| 1,751     	|
| Muti Core                	| 9,279       	| 10,229    	| 9,883     	|

| **GPU**                  	| **Windows**<br>Vulkan 	| **Linux**<br>Vulkan 	| **macOS**<br>Metal 	|
|----------------------------	|-----------------------	|---------------------	|--------------------	|
| NVIDIA<br>GeForce RTX 3090 	| 182,120               	| 194,027             	| -                  	|
| AMD<br>Radeon RX 5700 XT   	| 68,514                	| 76,096              	| 101,291            	|
| Intel<br>UHD 630 Graphics  	| 6,275                 	| 5,702               	| 6,312              	|

<br>

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

Intel UHD Graphics 630 

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| AAPL,ig-platform-id      |   Data   | ``07009B3E`` |
| device-id                |   Data   | ``9B3E0000`` |
| enable-metal             |   Data   | ``01000000`` |
| disable-agdc             	|   Data   	|        ``01000000``       	|
| enable-hdmi-dividers-fix 	|   Data   	|        ``01000000``       	|
| enable-hdmi20            	|   Data   	|        ``01000000``       	|
| framebuffer-con0-busid  	|   Data   	|        ``02000000``       	|
| framebuffer-con0-enable    	|   Data   	|        ``01000000``       	|
| framebuffer-con0-flags  	|   Data   	|        ``C7030000``       	|
| framebuffer-con0-index    	|   Data   	|        ``02000000``       	|
| framebuffer-con0-pipe  	|   Data   	|        ``0A000000``       	|
| framebuffer-con0-type    	|   Data   	|        ``00080000``       	|
| framebuffer-con1-busid  	|   Data   	|        ``04000000``       	|
| framebuffer-con1-enable    	|   Data   	|        ``01000000``       	|
| framebuffer-con1-flags  	|   Data   	|        ``C7030000``       	|
| framebuffer-con1-index    	|   Data   	|        ``03000000``       	|
| framebuffer-con1-pipe  	|   Data   	|        ``08000000``       	|
| framebuffer-con1-type    	|   Data   	|        ``00080000``       	|
| framebuffer-con2-busid  	|   Data   	|        ``01000000``       	|
| framebuffer-con2-enable    	|   Data   	|        ``01000000``       	|
| framebuffer-con2-flags  	|   Data   	|        ``C7030000``       	|
| framebuffer-con2-index    	|   Data   	|        ``01000000``       	|
| framebuffer-con2-pipe  	|   Data   	|        ``09000000``       	|
| framebuffer-con2-type    	|   Data   	|        ``00080000``       	|
| framebuffer-patch-enable 	|   Data   	|        ``01000000``       	|
| framebuffer-stolenmem    	|   Data   	|        ``00003001``       	|
| rps-control              	|   Data   	|        ``01000000``       	|
| hda-gfx                 	|   String   	|        ``onboard-1``       	|
| model                   	|   String   	|        ``Intel UHD Graphics 630``       	|
| igfxfw                   |   Data   | ``02000000`` |

<details><summary><h4>📄  Show as property list data</h4><br><sup>Expand this if you want to copy and paste the entries above as <code>.plist</code> data!</summary>

You can paste this data straight into plist editors like ProperTree.

```xml
<key>PciRoot(0x0)/Pci(0x2,0x0)</key>
<dict>
	<key>AAPL,ig-platform-id</key>
	<data>BwCbPg==</data>
	<key>device-id</key>
	<data>mz4AAA==</data>
	<key>disable-agdc</key>
	<data>AQAAAA==</data>
	<key>enable-hdmi-dividers-fix</key>
	<data>AQAAAA==</data>
	<key>enable-hdmi20</key>
	<data>AQAAAA==</data>
	<key>enable-metal</key>
	<data>AQAAAA==</data>
	<key>framebuffer-con0-busid</key>
	<data>AgAAAA==</data>
	<key>framebuffer-con0-enable</key>
	<data>AQAAAA==</data>
	<key>framebuffer-con0-flags</key>
	<data>xwMAAA==</data>
	<key>framebuffer-con0-index</key>
	<data>AgAAAA==</data>
	<key>framebuffer-con0-pipe</key>
	<data>CgAAAA==</data>
	<key>framebuffer-con0-type</key>
	<data>AAgAAA==</data>
	<key>framebuffer-con1-busid</key>
	<data>BAAAAA==</data>
	<key>framebuffer-con1-enable</key>
	<data>AQAAAA==</data>
	<key>framebuffer-con1-flags</key>
	<data>xwMAAA==</data>
	<key>framebuffer-con1-index</key>
	<data>AwAAAA==</data>
	<key>framebuffer-con1-pipe</key>
	<data>CAAAAA==</data>
	<key>framebuffer-con1-type</key>
	<data>AAgAAA==</data>
	<key>framebuffer-con2-busid</key>
	<data>AQAAAA==</data>
	<key>framebuffer-con2-enable</key>
	<data>AQAAAA==</data>
	<key>framebuffer-con2-flags</key>
	<data>xwMAAA==</data>
	<key>framebuffer-con2-index</key>
	<data>AQAAAA==</data>
	<key>framebuffer-con2-pipe</key>
	<data>CQAAAA==</data>
	<key>framebuffer-con2-type</key>
	<data>AAgAAA==</data>
	<key>framebuffer-patch-enable</key>
	<data>AQAAAA==</data>
	<key>framebuffer-stolenmem</key>
	<data>AAAwAQ==</data>
	<key>hda-gfx</key>
	<string>onboard-1</string>
	<key>igfxfw</key>
	<data>AgAAAA==</data>
	<key>model</key>
	<string>Intel UHD Graphics 630</string>
	<key>rps-control</key>
	<data>AQAAAA==</data>
</dict>
```
</details><br>

> [!IMPORTANT]
> The connector patches in the table above are new as of the **25th August 2024** and were implemented to **fix HDMI output**. Please add these new entries to enable HDMI! 

> [!NOTE]
> The NEW configuration of the **UHD Graphics 630** can run in both ***display and headless*** modes!

> [!TIP]
> The ``enable-metal`` key is now included to enable **Metal 3** graphics support with the UHD Graphics 630! 
> 
> This means various macOS apps can now utilise the iGPU - even while headless - for more trivial tasks, such as rendering Finder. This frees up the dGPU's resources for other more intensive tasks.
>
> You can even see this in action by [enabling the hidden GPU tab in Activity Monitor](https://github.com/Coopydood/OpenCore-Z490E-CometLake#show-gpu-tab-in-activity-monitor).

<br>

### PciRoot(0x0)/Pci(0x1C,0x1)/Pci(0x0,0x0)

Intel I225-V 2.5Gb Ethernet

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| device-id                |   Data   | ``F2150000`` |

<details><summary><h4>📄  Show as property list data</h4><br><sup>Expand this if you want to copy and paste the entries above as <code>.plist</code> data!</summary>

You can paste this data straight into plist editors like ProperTree.

```xml
<key>PciRoot(0x0)/Pci(0x1C,0x4)/Pci(0x0,0x0)</key>
<dict>
	<key>device-id</key>
	<data>8hUAAA==</data>
</dict>
```
</details><br>

> [!NOTE]
> The **Intel I225-V** requires a special patch mentioned in [Kernel](https://github.com/Coopydood/OpenCore-Z490E-CometLake/?tab=readme-ov-file#patches).
> 
> This only applies to macOS Big Sur and older.

> [!TIP]
> For improved compatibility with macOS Big Sur and older, the ``I225-V`` model has now been masked as the near-identical ``I225-LM`` model. After extensive testing, it appears functionality is the same.

<br>

### PciRoot(0x0)/Pci(0x1b,0x0)

Apple ALC

| **Key**                  | **Type** |   **Value**  |
|--------------------------|:--------:|:------------:|
| AAPL,ig-platform-id      |   Data   | ``0300220D`` |
| layout-id                |   Data   | ``01000000`` |

<details><summary><h4>📄  Show as property list data</h4><br><sup>Expand this if you want to copy and paste the entries above as <code>.plist</code> data!</summary>

You can paste this data straight into plist editors like ProperTree.

```xml
<key>PciRoot(0x0)/Pci(0x1b,0x0)</key>
<dict>
	<key>AAPL,ig-platform-id</key>
	<data>AwAiDQ==</data>
	<key>layout-id</key>
	<data>AQAAAA==</data>
</dict>
```
</details><br>

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
- VirtualSMC
- AppleALC
- BlueToolFixup
- IntelBTPatcher
- SMCProcessor
- SMCSuperIO
- SMCRadeonSensors
- RestrictEvents
- FeatureUnlock
- RTCMemoryFixup
- Z490E_USBMap

> [!NOTE]
> ``Z490E_USBMap.kext`` is a custom kext containing the USB mappings of my ASUS ROG STRIX Z490-E GAMING motherboard ports - your mileage may vary!

> [!NOTE]
> ``RestrictEvents.kext`` has been added to utilise its OTA software update patches. It does NOT apply any other patches.

> [!TIP]
> There are multiple versions of ``AirportItlwm.kext`` installed to support various versions of macOS.
>
> You don't have to remove any - they have all been individually configured to only be injected based on the macOS version booted.

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

<details><summary><h4>📄  Show as property list data</h4><br><sup>Expand this if you want to copy and paste the entries above as <code>.plist</code> data!</summary>

You can paste this data straight into plist editors like ProperTree.

```xml
<dict>
	<key>Arch</key>
	<string>Any</string>
	<key>Base</key>
	<string>__Z18e1000_set_mac_typeP8e1000_hw</string>
	<key>Comment</key>
	<string>I225-V patch</string>
	<key>Count</key>
	<integer>1</integer>
	<key>Enabled</key>
	<true/>
	<key>Find</key>
	<data>8hUAAA==</data>
	<key>Identifier</key>
	<string>com.apple.driver.AppleIntelI210Ethernet</string>
	<key>Limit</key>
	<integer>0</integer>
	<key>Mask</key>
	<data></data>
	<key>MaxKernel</key>
	<string>20.4.0</string>
	<key>MinKernel</key>
	<string>19.0.0</string>
	<key>Replace</key>
	<data>8xUAAA==</data>
	<key>ReplaceMask</key>
	<data></data>
	<key>Skip</key>
	<integer>0</integer>
</dict>
```
</details><br>

***

## Security

**SecureBootModel 》** j185f

**Vault 》** Optional

> [!NOTE]
> The secure boot model ``j185f`` corresponds to an ``iMac20,2`` from August 2020.

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
| boot-args                 |  String  | keepsyms=1 debug=0x100 alcid=1 agdpmod=pikera igfxgl=1 forceRenderStandby=0 itlwm_cc=GB revpatch=sbvmm |
| csr-active-config         |   Data   |                                  ``00000000``                                  |
| prev-lang-diags:kbd       |   Data   |                                 ``656E2D47 42``                                |
| prev-lang:kbd             |   Data   |                               ``656E2D47 423A32``                              |                                      |
| StartupMute               |   Data   |                                     ``00``                                     |

<details><summary><h4>📄  Show as property list data</h4><br><sup>Expand this if you want to copy and paste the entries above as <code>.plist</code> data!</summary>

You can paste this data straight into plist editors like ProperTree.

```xml
	<key>4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14</key>
	<dict>
		<key>DefaultBackgroundColor</key>
		<data>AAAAAA==</data>
	</dict>
	<key>4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102</key>
	<dict>
		<key>rtc-blacklist</key>
		<data></data>
	</dict>
	<key>7C436110-AB2A-4BBB-A880-FE41995C9F82</key>
	<dict>
		<key>ForceDisplayRotationInEFI</key>
		<integer>0</integer>
		<key>boot-args</key>
		<string>keepsyms=1 debug=0x100 alcid=1 agdpmod=pikera igfxgl=1 forceRenderStandby=0 itlwm_cc=GB revpatch=sbvmm</string>
		<key>prev-lang-diags:kbd</key>
		<data>ZW4tR0I=</data>
		<key>prev-lang:kbd</key>
		<data>ZW4tR0I6Mg==</data>
		<key>csr-active-config</key>
		<data>AAAAAA==</data>
		<key>StartupMute</key>
		<data>AA==</data>
		<key>SystemAudioVolume</key>
		<data>Rg==</data>
	</dict>
```
</details><br>

***

## SMBIOS

### iMac20,2

Due to the system having a 10-core i9-10900K, the CPU model is similar to the one found in an **iMac 5K 27-inch (i9, 2020)**, with a model identifier of ``iMac20,2``.

***

## UEFI

Drivers in use:

- HFSPlus
- OpenCanopy
- OpenRuntime
- ResetNvramEntry
  
***

## Post-Install Tweaks

This is just a collection of my post-install tweaks I apply after installing macOS. They're not really related to OpenCore or the overall functionality of the configuration.

<details><summary><h4>Dark Menu Bar and Dock</h4></summary>

Okay, so I'm a bit of a macOS boomer. Having used macOS since long before Mojave's *dark mode*, I'm accustomed to the regular light appearance of the windows - but I always enabled the "Dark menu bar and dock" option as I loved the look. While I still like dark mode (and use it on iOS), the hybrid light/dark mode on macOS is still my favourite!

The following commands restore that functionality:

**Window Server**
```sh
defaults write -g NSRequiresAquaSystemAppearance -bool Yes
```

**Notification Centre**
```sh
defaults write com.apple.notificationcenterui NSRequiresAquaSystemAppearance -bool No
```

**Control Centre**
```sh
defaults write com.apple.controlcenterui NSRequiresAquaSystemAppearance -bool No
```

**About This Mac + System Profiler**
```sh
defaults write com.apple.SystemProfiler.AboutExtension NSRequiresAquaSystemAppearance -bool No
defaults write com.apple.SystemProfiler.AboutExtension NSRequiresAquaSystemAppearance -bool No
```

</details>

<details><summary><h4>Show Hidden Files</h4></summary>

Does what it says on the tin. Shows all files, including hidden ones, in the Finder.

```sh
defaults write com.apple.Finder AppleShowAllFiles YES
killall Finder
```
</details>

<details><summary><h4>Show GPU Tab in Activity Monitor</h4></summary>

Unhides the hidden sECrET GPU tab in macOS' Activity Monitor, helpful for seeing which apps are running on what GPU!

```sh
defaults write com.apple.ActivityMonitor ShowGPUTab -bool true
```
</details>

<details><summary><h4>AirDrop over Ethernet</h4></summary>

Makes AirDrop scan Ethernet too!

```sh
defaults write com.apple.NetworkBrowser BrowseAllInterfaces 1
killall Finder
```
</details>

<details><summary><h4>Frosted Glass Terminal Theme</h4></summary>

Some macOS eye candy.

```sh
curl -OL https://raw.githubusercontent.com/Coopydood/OpenCore-Z490E-CometLake/main/EXTRAS/HyperTerm.terminal
```

Import through Terminal's preferences.
</details>


***

## Gallery

<img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/9dd5dda0-92c3-4cc7-a7e4-3aab714671db" width="30%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/4694291b-adcd-4847-99e2-a4f89c9c1ac9" width="60%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/569407bd-0893-4974-82f0-ff669d317783" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/c3ec115d-fe2c-4382-9fa3-d73d3c10cfd2" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/4ef63542-a628-4a97-a598-7474bf151414" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/7fd1683a-b389-4d5c-a8c6-106279a50625" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/bc47bf2e-0879-4584-bab1-f039f38f73c0" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/85bd9aee-1a09-4a16-b121-5bc96f21becd" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/8ee36d3f-9b64-42bc-b853-a82dd7feb58d" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/c5dde7cc-2e73-4833-882f-ab86ab4fbf33" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/85dd1971-efb5-47f0-a73b-459099d383bb" width="45%"></img> <img src="https://github.com/Coopydood/OpenCore-Z490E-CometLake/assets/39441479/d455d5f8-830e-4fb5-9f08-30d65fcce1db" width="45%"></img>

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

<!-- <details><summary><h4>📄  Show as property list data</h4><br><sup>Expand this if you want to copy and paste the entries above as <code>.plist</code> data!</summary>

You can paste this data straight into plist editors like ProperTree.

```plist

```
</details><br> --!>
