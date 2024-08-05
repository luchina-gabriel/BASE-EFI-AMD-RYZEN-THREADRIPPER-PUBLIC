# BASE EFI AMD - Ryzen and Threadripper (1XXX, 2XXX, 3XXX, 4XXX, 5XXX & 7XXX) and Athlon 2xxGE

# 🛠️ Remote Services | Serviços remotos

🇺🇸 - If you wish, we can create your EFI and [install macOS remotely](https://universohackintosh.com/portal/consultoria-profissional-para-hackintosh/#servico-instalacao-completa-do-hackintosh), just hire our services via the email below.
<br>
🇧🇷 - Se desejar, criamos sua EFI e realizamos a [instalação remotamente do macOS](https://universohackintosh.com/portal/consultoria-profissional-para-hackintosh/#servico-instalacao-completa-do-hackintosh), basta contratar nossos serviços pelo e-mail abaixo.
<br>
✉️ - Endereço EXCLUSIVO para contratação de serviços: consultoria@universohackintosh.com.br.

# 🆘 How to GET a COPY of BASE EFI <br> 🆘 Como obter a CÓPIA da EFI BASE

🇺🇸 - To download EFI BASEs, you must be a member of any category on the [YouTube Channel](https://hackintosh.one/s/seja-membro) and connect your Discord to your YouTube account to access the [#efi-base](https://discord.com/channels/887798875069505587/1184144798312038512) channel;
<br><br>
🇧🇷 - Para download das EFIs BASEs, é necessário você ser membro de qualquer categoria no [Canal do YouTube](https://hackintosh.one/s/seja-membro) e conectar seu Discord à sua conta YouTube para acesso à sala [#efi-base](https://discord.com/channels/887798875069505587/1184144798312038512);

![youtube_connection](https://github.com/luchina-gabriel/BASE-EFI-AMD-RYZEN-THREADRIPPER-PUBLIC/assets/23700365/c7062e03-2c61-4715-bd75-2dac9fd0d5f8)
<br>
![efi-base-channel](https://github.com/luchina-gabriel/BASE-EFI-AMD-RYZEN-THREADRIPPER-PUBLIC/assets/23700365/0d91e920-a254-441f-ac52-ab8b31869330)

# Basic Info

Note|Description
:----|:----
Initial macOS Support|macOS 10.13, High Sierra.
Last Supported OS|macOS 15 Sequoia.

- Opencore version: 1.0.1
- Release date: 05/08/2024

# Basic Steps

1. [Download](https://discord.com/channels/887798875069505587/1184144798312038512) the latest release [Discord, #efi-base channel];
2. Includes **additional** kexts (for ethernet, audio, etc);
3. Include the **necessary** ACPI patches (.aml);
4. Review the special notes;
5. Generate and complete your SMBIOS infos - **ALWAYS**;
6. Adjust your BIOS;
7. Install macOS and enjoy :)

# Features
- [x] Very light, very clean, basic files for your Hackintosh.
- [x] Made with latest OpenCore versions.
- [x] Two editions - *Release* and *Debug* Edition.
- [x] Updated montly with refresh versions of Opencore.

# Kexts included (**Required**)

Kext|Description
:----|:----
[AMDRyzenCPUPowerManagement.kext](https://github.com/trulyspinach/SMCAMDProcessor/releases)|For [AMD Power Gadget](https://github.com/trulyspinach/SMCAMDProcessor).
[SMCAMDProcessor.kext](https://github.com/trulyspinach/SMCAMDProcessor/releases)|For [AMD Power Gadget](https://github.com/trulyspinach/SMCAMDProcessor).
[AppleMCEReporterDisabler.kext](https://github.com/acidanthera/bugtracker/files/3703498/AppleMCEReporterDisabler.kext.zip)|Useful starting with Catalina to disable the AppleMCEReporter kext which will cause kernel panics on AMD CPUs and dual-socket systems.
[Lilu.kext](https://github.com/acidanthera/Lilu/releases)|Patch many processes, required for AppleALC, WhateverGreen, VirtualSMC and many other kexts.
[VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC/releases)|Emulates the SMC chip found on real macs, without this macOS will not boot.<br>Alternative is FakeSMC which can have better or worse support, most commonly used on legacy hardware.
[WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases)|Used for graphics patching, DRM fixes, board ID checks, framebuffer fixes, etc; all GPUs benefit from this kext.

# Other Kexts (not included)

Kexts for support Audio, Wifi, Ethernets and other devices.

### Audio

Kext|Description
:----|:----
[AppleALC.kext](https://github.com/acidanthera/AppleALC/releases)|Used for AppleHDA patching, allowing support for the majority of on-board sound controllers.<br>AMD 15h/16h may have issues with this and Ryzen/Threadripper systems rarely have mic support.
[VoodooHDA.kext](https://sourceforge.net/projects/voodoohda/)|Audio for FX systems and front panel Mic+Audio support for Ryzen system, do not mix with AppleALC.<br>Audio quality is noticeably worse than AppleALC on Zen CPUs.

### Ethernet
Kext|Description
:----|:----
[IntelMausi.kext](https://github.com/acidanthera/IntelMausi/releases)|Intel's 82578, 82579, I217, I218 and I219 NICs are officially supported.
[IntelMausiEthernet.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/IntelMausiEthernet.kext-V2.5.3d4.zip)|Alternative for some I219 NICs. Use it if the kext above doesn't work.
[IntelMausiEthernet.kext](https://github.com/CloverHackyColor/IntelMausiEthernet/releases)|Some alternative for some I219 NICs. Use it if the kext above doesn't work.
[AtherosE2200Ethernet.kext](https://github.com/Mieze/AtherosE2200Ethernet/releases)|Required for Atheros and Killer NICs.<br>**Note**: Atheros Killer E2500 models are actually Realtek based, for these systems please use RealtekRTL8111 instead.
[RealtekRTL8100.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/RealtekRTL8100-V2.0.1.zip)|Required for Realtek FE Familly Controller - 10/100 Mbps. Common on older hardware.
[RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X/releases)|Required for Realtek Gigabit Ethernet. Realtek GbE Familly Controller<br>Sometimes the latest version of the kext might not work properly with your Ethernet. If you see this issue, try older versions.
[LucyRTL8125Ethernet.kext](https://www.insanelymac.com/forum/files/file/1004-lucyrtl8125ethernet/)|Required for Realtek 2.5Gb Ethernet.
[SmallTreeIntel82576.kext](https://github.com/khronokernel/SmallTree-I211-AT-patch/releases)| Required for I211 NICs, based off of the SmallTree kext but patched to support I211.<br>Required for most AMD boards running Intel NICs.
[AppleIGB.kext](https://github.com/donatengit/AppleIGB/releases)|Required for I211 NICs running on macOS Monterey and above. Might have instability issues on some NICs, recommended to stay on Big Sur and use SmallTree. Requires macOS 12 and above.
[AppleIGC.kext](https://github.com/SongXiaoXi/AppleIGC/releases)|Required for I226 NICs running on macOS Monterey and above. Might have instability issues on some NICs.
[AppleIntelI210Ethernet.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/AppleIntelI210Ethernet.kext.zip)|Required for Intel i225-V in macOS 12 (Monterey) and above.

### WiFi and Bluetooth
Kext|Description
:----|:----
[AirportItlwm](https://github.com/OpenIntelWireless/itlwm/releases)|Adds support for a large variety of INTEL WIRELESS cards and works natively in recovery thanks to IO80211Family integration.
[IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases)|Adds Bluetooth support to macOS when paired with an Intel wireless card.
[AirportBrcmFixup](https://github.com/acidanthera/AirportBrcmFixup/releases)|Used for patching non-Apple/non-Fenvi Broadcom cards, will not work on Intel, Killer, Realtek, etc.<br>For Big Sur see [Big Sur Known Issues](https://dortania.github.io/OpenCore-Install-Guide/extras/big-sur#known-issues) for extra steps regarding AirPortBrcm4360 drivers.
[BrcmPatchRAM](https://github.com/acidanthera/BrcmPatchRAM/releases)|Used for uploading firmware on Broadcom Bluetooth chipset, required for all non-Apple/non-Fenvi Airport cards.

### Others
Kext|Description
:----|:----
[NVMeFix](https://github.com/acidanthera/NVMeFix/releases)|Used for fixing power management and initialization on non-Apple NVMe.
[SATA-Unsupported](https://github.com/khronokernel/Legacy-Kexts/blob/master/Injectors/Zip/SATA-unsupported.kext.zip)|Adds support for a large variety of SATA controllers, mainly relevant for laptops which have issues seeing the SATA drive in macOS.<br>We recommend testing without this first.
[RestrictEvents](https://github.com/acidanthera/RestrictEvents/releases)|Better experience with unsupported processors like AMD, Disable MacPro7,1 memory warnings and provide upgrade to macOS Monterey via Software Updates when available.
[SMCRadeonGPU](https://github.com/ChefKissInc/RadeonSensor)|Used for monitoring GPU temperature on AMD GPU systems. Requires RadeonSensor from the same repository. Requires macOS 11 or newer.
[FeatureUnlock](https://github.com/acidanthera/FeatureUnlock/releases)|Add Sidecar, NightShift, AirPlay, Universal Control and Continuity Camera support.

### Notebooks
Kext|Description
:----|:----
[VoodooPS2Controller](https://github.com/acidanthera/VoodooPS2/releases)|PS2 Keyboards/Trackpads.<br>Works with various PS2 keyboards, mice, and trackpads.<br>Requires macOS 10.11 or newer for MT2 (Magic Trackpad 2) functions.
[VoodooRMI](https://github.com/VoodooSMBus/VoodooRMI/releases)|SMBus Trackpads.<br>For systems with Synaptics SMBus trackpads.<br>Requires macOS 10.11 or newer for MT2 functions.<br>Depends on Acidanthera's VoodooPS2.
[VoodooSMBus](https://github.com/VoodooSMBus/VoodooSMBus/releases)|SMBus Trackpads.<br>For systems with ELAN SMBus Trackpads.<br>Supports macOS 10.14 or newer currently.
[VoodooI2C](https://github.com/VoodooI2C/VoodooI2C/releases)|I2C/USB HID Devices.<br>Attaches to I2C controllers to allow plugins to talk to I2C trackpads.<br>USB devices using the below plugins still need VoodooI2C.<br>Supports macOS 10.11+.
[ECEnabler](https://github.com/1Revenger1/ECEnabler/releases)|Fixes reading battery status on many devices (Allows reading EC fields over 8 bits long).<br>Supports OS X 10.7 and above (not needed on 10.4 - 10.6).
[BrightnessKeys](https://github.com/acidanthera/BrightnessKeys/releases)|Fixes brightness keys automatically.

# ACPI Tables - AMD

These files are **MUST** be included in your EFI's ACPI directory. We recommend that you use the **MANUAL** method, but for a first test you can use the prebuild versions.

SSDT|Description
:----|:----
SSDT-EC-USBX|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-EC-USBX-DESKTOP.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-fix.html)
SSDT-CPUR|[Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-CPUR.aml) <br> *Only for B550 and A520*

### Dumping your DSDT in Windows Environment
[Download iASL Compiler ACPI Tools](https://www.intel.com/content/www/us/en/download/774881/acpi-component-architecture-downloads-windows-binary-tools.html)
<br><br>
Open the CMD in the directory where the *ACPI Tools* was extracted. (*Command Prompt*) in **Administrator Mode**:
```
path/to/acpidump.exe -b -n DSDT -z
move dsdt.dat DSDT.aml
```

Decompile DSDT.aml:
```
path/to/iasl.exe path/to/DSDT.aml
```
*File DSDT.dsl will generated. Use this for generate YOUR ACPI Patches.* 

Compile DSDT.dsl:
```
path/to/iasl.exe path/to/DSDT.dsl
```
*File APCPI_FILE_PATCHED.aml will generated.*

# Attention

Update **config.plist** in PlatformInfo > Generic with YOUR informations.
<br><br>
*1. MLB (Board Serial)
<br>
2. ROM (Mac Address)
<br>
3. SystemSerialNumber (Serial)
<br>
4. SystemUUID (SmUUID)*

Please use [*genSMBIOS*](https://github.com/corpnewt/GenSMBIOS/archive/refs/heads/master.zip) for generate values for above itens.
<br>
Please use [*ProperTree*](https://github.com/corpnewt/ProperTree/archive/refs/heads/master.zip) for configure/edit your config.plist.

# Compatible SMBIOS

SMBIOS|Description
:----|:----
iMacPro1,1|AMD RX Polaris and newer.
MacPro7,1|AMD RX Polaris and newer.<br>Note that MacPro7,1 is exclusive to macOS 10.15, Catalina and newer.
MacPro6,1|AMD R5/R7/R9 and older.
iMac14,2|Nvidia Kepler and newer.<br>Note: iMac14,2 is only supported to macOS 10.8-10.15, for macOS 11, Big Sur and newer please use MacPro7,1.

# Catalina and older versions of macOS

- Please configure `MinDate` and `MinVersion` in UEFI > APFS to `-1`;
- Please configure `SecureBootModel` in Misc > Security to `j137`;

\* *Without above settings, macOS will not be able to boot.*

# macOS Sonoma 14.4 or above versions (including macOS Sequoia (v15))
- Please configure `SecureBootModel` to `Disabled`;
- After the installation is completed, you can return the value to 'Default';
- If the above adjustment is not performed, the installation will be in a looping.

# Special notes

- USB port mapping is **REQUIRED**.
- **`XhciPortLimit`** - Please `**ENABLE**` to map the USB ports
	- You can use USBMap.command Utility - [USBMap](https://github.com/corpnewt/USBMap).
- **`SetupVirtualMap`** in config.plist:
	- B550, A520 and TRx40 boards should **`DISABLE`** this;
	- Newer BIOS versions of X570 also require this **`DISABLE`**;
	- X470 and B450 with late 2020 BIOS updates also require this **`DISABLE`**.
- **`DevirtualiseMmio`** - TRx40 users please **`ENABLE`** this flag.

## Special notes - Mapping CORES for AMD CPU

**Note for Zen 4:** Zen 4 (Ryzen 7000) requires patching for IOPCIFamily.kext. <br>
This patch is enabled by default. Please ensure that you've added it to your current config for Zen 4 stability. <br>
This patch also allows MSI A520, B550, and X570 boards to boot macOS Monterey and newer. <br>

Core Count patch needs to be modified to boot your system.<br>
Find the four `algrey - Force cpuid_cores_per_package` patches and alter the `Replace` value only.

|   macOS Version      | Replace Value | New Value |
|----------------------|---------------|-----------|
| 10.13.x, 10.14.x     | B8000000 0000 | B8 < Core Count > 0000 0000 |
| 10.15.x, 11.x        | BA000000 0000 | BA < Core Count > 0000 0000 |
| 12.x, 13.0 to 13.2.1 | BA000000 0090 | BA < Core Count > 0000 0090 |
| 13.3                 |  BA000000 00  | BA < Core Count > 0000 00 |

From the table above substitue `< Core Count >` with the hexadecimal value matching your physical core count. <br>
Do not use your CPU's thread count. <br>
See the table below for the values matching your CPU core count.

| Core Count | Hexadecimal |
|------------|-------------|
|   2 Core   |     `02`    |
|   4 Core   |     `04`    |
|   6 Core   |     `06`    |
|   8 Core   |     `08`    |
|   12 Core  |     `0C`    |
|   16 Core  |     `10`    |
|   24 Core  |     `18`    |
|   32 Core  |     `20`    |

So for example, a user with a 6-core processor should use these `Replace` values: `B8 06 0000 0000` / `BA 06 0000 0000` / `BA 06 0000 0090` / `BA 06 0000 00`

**Note:** *MacOS Monterey installation requires `Misc -> Security -> SecureBootModel` to be disabled in the config.<br />Also TPM needs to be disabled in the BIOS. Both can be enabled after install.*

# Special notes [DeviceProperties > Add]

- PLEASE EDIT/ADD DEVICE FOR ETHERNET i225 (You can identify with Hackintool on `PCIe` tab).
	- If your board didn't ship with the Intel I225 NIC, there's no reason to add this entry.
	- If you get a kernel panic on the `AppleIntelI210Ethernet` kext, your Ethernet's path is likely `PciRoot(0x0)/Pci(0x1C,0x4)/Pci(0x0,0x0)`.
	- Please **`ENABLE`** Patch for i225 on `Kernel > Patch`.
	- for macOS Monterey 12.2.1 and below, please add `dk.e1000=0` in `boot-args`.
	- for macOS Monterey 12.3 or newer, please add `e1000=0` in `boot-args`.
	- for macOS Ventura, please add `e1000=0` in `boot-args` and add Kext [AppleIntelI210Ethernet.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/AppleIntelI210Ethernet.kext.zip)

## TRX40 Systems

Disabling the `mtrr_update_action - fix PAT` patch has shown an improvement in GPU performance on some systems that have tested. If you wish to test this it is recommended to do so on a USB with OpenCore to ensure it works first. There may be issues with different motherboard/GPU combos that we aren't aware of. Proceed at your own risk.

### General Purpose `boot-args`

Parameter|Description
:----|:----
npci=0x2000|This disables some PCI debugging related to `kIOPCIConfiguratorPFM64`, alternative is `npci=0x3000` which disables debugging related to `gIOPCITunnelledKey` in addition.<br>Required for when getting stuck on `PCI Start Configuration` as there are IRQ conflicts relating to your PCI lanes. **Not needed if Above4GDecoding is enabled.**
npci=0x3000|Alternative for `npci=0x2000`.

### GPU-Specific `boot-args`

Parameter|Description
:----|:----
agdpmod=pikera|Used for disabling board ID checks on Navi GPUs(RX 5000 series & RX 6000 series), without this you'll get a black screen.<br>**Don't use if you don't have Navi** (ie. Polaris and Vega cards shouldn't use this).
nvda_drv_vrl=1|Used for enabling Nvidia's Web Drivers on Maxwell and Pascal cards in Sierra and High Sierra.

### Ethernet (Intel i225) `boot-args`
Parameter|Description
:----|:----
dk.e1000=0|Disables `com.apple.DriverKit-AppleEthernetE1000` (Apple's DEXT driver) from matching to the Intel I225-V Ethernet controller found on higher end Comet Lake boards, causing Apple's I225 kext driver to load instead.<br>This boot argument is optional on most boards as they are compatible with the DEXT driver. However, it is required on Gigabyte and several other boards, which can only use the kext driver, as the DEXT driver causes hangs.<br>You don't need this if your board didn't ship with the I225-V NIC.
e1000=0|for macOS 12.3.1 or newer<br>Disables `com.apple.DriverKit-AppleEthernetE1000` (Apple's DEXT driver) from matching to the Intel I225-V Ethernet controller found on higher end Comet Lake boards, causing Apple's I225 kext driver to load instead.<br>This boot argument is optional on most boards as they are compatible with the DEXT driver. However, it is required on Gigabyte and several other boards, which can only use the kext driver, as the DEXT driver causes hangs.<br>You don't need this if your board didn't ship with the I225-V NIC.

# BIOS Settings

### Disable
- Fast Boot
- Secure Boot
- Serial/COM Port
- Parallel Port
- Compatibility Support Module (CSM)(Must be off, GPU errors like `gIO` are common when this option in enabled)

***Special note for 3990X users***: *macOS currently does not support more than 64 threads in the kernel, and so will kernel panic if it sees more. The 3990X CPU has 128 threads total and so requires half of that disabled. We recommend disabling hyper threading in the BIOS for these situations.*

### Enable
- Above 4G decoding
	- This must be on, if you can't find the option then add `npci=0x2000` to `boot-args`. 
	- Do not have both this option and `npci` in `boot-args` enabled at the same time.
	- If you are on a Gigabyte/Aorus or an AsRock motherboard, enabling this option may break certain drivers(ie. Ethernet) and/or boot failures on other OSes, if it does happen then disable this option and opt for `npci` instead.
	- 2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some X570 and newer motherboards. Please ensure this is **`DISABLED`** instead of set to Auto.
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- SATA Mode: AHCI

# References
https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html
<br>
https://dortania.github.io/Getting-Started-With-ACPI/
<br>
https://github.com/AMD-OSX/AMD_Vanilla

## Discord - Universo Hackintosh
- [Access Discord](https://discord.universohackintosh.com.br)
