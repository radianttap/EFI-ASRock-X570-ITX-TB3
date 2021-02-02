OpenCore ver 0.6.5 · Bug Sur 11.2

# ASRock X570 ITX/TB3 + Ryzen 9 5900X + RX 5500 XT → iMacPro1,1

Current hardware:

- AMD [Ryzen 9 5900X](https://www.amd.com/en/products/cpu/amd-ryzen-9-5900x) CPU
- XPG [Levante 240](https://www.xpg.com/en/feature/644/) AIO
- [ASRock X570 Phantom Gaming-ITX/TB3](https://www.asrock.com/mb/AMD/X570%20Phantom%20Gaming-ITXTB3/) motherboard
- Sapphire [Pulse RX 5500 XT SF 8GB](https://www.sapphiretech.com/en/consumer/pulse-radeon-rx-5500-xt-sf-8g-gddr6) graphics card
- Corsair [Vengeance LPX](https://www.corsair.com/ww/en/Categories/Products/Memory/VENGEANCE-LPX/p/CMK32GX4M2B3200C16) 32 GB (2 x 16 GB) DDR4 3200MHz CL16
- Corsair [SF600 Platinum](https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020182-NA) SFX PSU
- Noctua [NF-A12x25](https://noctua.at/en/products/fan/nf-a12x25-pwm) case fan
- ADATA [XPG 8200 Pro](https://www.xpg.com/us/feature/583/) 1TB NVMe SSD
- Samsung [860 EVO](https://www.samsung.com/us/computing/memory-storage/solid-state-drives/ssd-860-evo-2-5--sata-iii-500gb-mz-76e500b-am/) 500 GB 2.5in SSD
- Nouvolo [Steck v1.1](https://www.nouvolo.com) SFF case

### WiFI / Bt

The combo below offers natively supported WiFi 5 / Bluetooth 4.

- 1750Mbps Dual Band WiFi 2.4GHz/5GHz / Bluetooth 4.0 [Broadcom BCM94360CD](https://www.aliexpress.com/item/1750Mbps-Dual-Band-WiFi-Bluetooth-Card-2-4GHz-5GHz-BT-4-0-Broadcom-BCM94360CD-Wireless-Module/32974196141.html) card
- mini PCIe [adapter card](https://www.aliexpress.com/item/MINI-PCI-E-Adapter-Converter-to-wireless-wifi-card-BCM94360CD-BCM94331CD-BCM94360CS-BCM94360CS2-module-for-macbook/32256494722.html)

Combined with this riser cable, the card/adapter combo from above can be moved outside the motherboard I/O shroud, instead of existing Intel AX200 card.

- Mini [PCIe riser with adapter](https://www.aliexpress.com/item/BCM94360CD-BCM94360CS2-BCM943224PCIEBT2-Card-To-M-2-Key-A-E-Cable-For-Mac-OS-and-and/4000286967003.html) for M.2 Key A/E

### BIOS

Version 2.80

- Fast Boot: `Disabled`
- CSM: `Disabled`
- Above 4G Decoding: `Enabled`
- Resizable Bar Support: `Disabled`
- PCIe speed: `Gen 3` (*do not* leave it on Auto)
- XMP Profile activated.
- FCLK set to 1600MHz, to be equal to MCLK.

## Usage

1. [Update `PlatformInfo/Generic` stuff](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial) with your own, inside `config.plist`
2. Use your Ethernet’s MAC address for `ROM` value, as explained in the Dortania guide. Don’t leave it as all 0s.
3. Update value of `brcmfx-country` argument in `NVRAM/7C436110-AB2A-4BBB-A880-FE41995C9F82/boot-args` with your country code. Should be identical or compatible with what your WiFi router is broadcasting. (Remove the parameter if you don’t know what I’m talking about here.)
4. Turn off Power Nap in Energy Saver.

Important: Add `-v` boot-args parameter to get verbose boot process, it greatly simplifies troubleshooting.

### What’s working

Pretty much everything.

- NVMe SSD recognised properly.
- WiFi, Bluetooth, Ethernet
- All USB ports properly mapped. Steck case does not have any ports thus internal USB header is not connected.
- Radeon GPU, natively supported.
- All media services (Plex, Netflix in Safari, iTunes, Apple TV+ etc). All are fully hardware-accelerated.
- 4K HDMI with HDR, Dolby.
- Watch unlock, Handoff, iMessage, iCloud, Keychain, Xcode etc.
- System Integrity Protection (SIP) fully enabled.
- Sleep

### What’s not working

- Sidecar
- Wake (GPU fails to start up)
- Thunderbolt 3

## Notes

Use at your own risk. 

- All `.efi` drivers and `.kext` are `-DEBUG` builds from the respective packages. 
- OpenCanopy (GUI boot menu) is up and running.
- I don’t boot Windows 10 using OC, thus I can’t guarantee it will work. I have Win 10 installed on separate SSD and switch using Boot Menu.

**Don’t ask me for help.** Sorry but this stuff is finicky and infuriatingly detailed that every little mis-step can be a proper headache. This is why [Dortania](https://dortania.github.io) advises to not reuse anyone’s EFI.  

Ask [on reddit](https://www.reddit.com/r/hackintosh/) and the [discord server](https://discord.gg/Wxam8aH).

Good luck.
