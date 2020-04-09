OpenCore ver 0.5.7

# ASRock X570 ITX/TB3 + Ryzen 5 3600 + RX 570 → iMacPro1,1

Current hardware:

- AMD [Ryzen 5 3600](https://www.amd.com/en/products/cpu/amd-ryzen-5-3600)
- [ASRock X570 Phantom Gaming-ITX/TB3](https://www.asrock.com/mb/AMD/X570%20Phantom%20Gaming-ITXTB3/) motherboard
- Sapphire [Nitro+ RX570 8GB](https://www.sapphiretech.com/en/consumer/nitro-rx-570-8g-g5-oc) graphics card
- Intel WiFi card (AX200) replaced with [Fenvi BCM94352Z](https://www.aliexpress.com/item/Dual-band-Wireless-Hackintosh-BCM94352Z-WIFI-Card-Broadcom-bcm94352-M-2-Bluetooth-4-0-Network-NGFF/32464748097.html)
- Corsair [Vengeance LPX](https://www.corsair.com/us/en/Categories/Products/Memory/VENGEANCE-LPX/p/CMK16GX4M2B3200C16) 16 GB (2 x 8 GB) DDR4 3200MHz CL16
- Nouvolo [Steck v1.1](https://www.nouvolo.com) SFF case
- Corsair [SF600 Platinum](https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020182-NA) SFX PSU
- Noctua [NH-L9x65](https://noctua.at/en/products/cpu-cooler-retail/nh-l9x65) CPU cooler
- Noctua [NF-A12x25](https://noctua.at/en/products/fan/nf-a12x25-pwm) case fan
- Noctua [NF-A9 PWM](https://noctua.at/en/products/fan/nf-a9-pwm) fan (used it to replace 9x14 on the CPU cooler).
- ADATA [XPG 8200 Pro](https://www.xpg.com/us/feature/583/) 1TB NVMe SSD

## Usage

In order to use this properly, you need to:

- update SMBIOS stuff with your own, inside config.plist
- Open Terminal on your Mac in the root of this repo and then run `sh vault.sh` to sign the build.

Second step is required or your OC will fail to boot.

### Note

Use at your own risk. 

Don’t ask for help here; use appropriate AMD-OSX forums and Discord channels.

