# Clevo-NB50TK1-Hackintosh-OC

### This repo includes all the fixes for NB50TK1 on macOS Big Sur.

This repo can also be used for older versions of macOS.

Tested on:

Model | NB50TK1
------------- | ---------------
CPU | Intel Core i3-8100
iGPU | Intel UHD 630
dGPU | NVIDIA GTX 1050Ti (disabled)
RAM | 16GB
SSD | 128GB M.2 SATA
WiFi | Intel® Dualband-Wireless-AC 3168
Software | macOS 11.0 Big Sur

## What works?

Everything except dGPU

### How to improve the Hackintosh experience

Download [ClevoService](https://github.com/FreeJHack/ClevoService) and place `com.fjhk.ClevoService.agent.plist` in `/Library/LaunchAgents/`

## What doesn't work?

* dGPU: Since NVIDIA has no support since Mojave, the best way to run this card is by disabling it. By disabling the card in ACPI, the card will not consume any power, so the battery life is pretty good.
* HDMI Hotplug: This is an issue, we can't currently fix. To fix it, shut down the laptop and boot it while the HDMI is plugged in.
* Trackpad only has basic gestures

## How to install

Download this repo and place the EFI folder into your EFI Partition... That's it.

## How to Install macOS Big Sur

There are two ways you can install Big Sur:

1. If you have an already working macOS, download the Installer through App Store and make a bootable Installer with `createinstallmedia` by using this command in Terminal `sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`

2. If you are using Windows, use the [gibMacOS](https://github.com/corpnewt/gibMacOS) by corpnewt.

After you made a bootable Installer, copy the EFI to the EFI partition and install as usual. After the installation, mount the EFI of the installed OS and copy the EFI folder to its partition.

If you want an OOTB-WiFi: You need to change your WiFi card to get your internet working. Buy it on eBay or your trustworthy website and find a suitable card (M.2) with the kexts.


## Credits

Thanks to:

* sha106b and SkyrilHD (for making an EFI that is working very well)
* acidanthera (for making OpenCore)
* dortania (helping with their troubleshooting guide)
* and to our tester
