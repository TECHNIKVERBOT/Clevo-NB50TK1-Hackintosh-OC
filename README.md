# Clevo-NB50TK1-Hackintosh-OC

### This repo includes the OpenCore EFI with all the fixes for NB50TK1 on Big Sur.

This repo can also be used for macOS Catalina.

Tested on:

Model | NB50TK1
------------- | ---------------
CPU | Intel Core i3-8100
iGPU | Intel UHD Graphics 630
dGPU | NVIDIA GTX 1050 Ti (disabled)
RAM | 16 GB DDR4
SSD | 128 GB M.2 (SATA)
WiFi | Intel® Dualband-Wireless-AC 3168
Software | macOS 10.15.7 Catalina (Big Sur going to be tested soon)

## What works?

* Battery
* TrackPad
* Brightness control
* Function keys
* Sleep
* Keyboard backlight control incl. RGB
* Sound (incl. audio jack)
* WiFi (if using Airportitlwm, not included)
* Bluetooth (if using IntelBluetoothFirmware, untested and not included)
* iGPU acceleration (UHD 630)
* HDMI

### How to get function keys and KBD backlight control working

Download [ClevoService](https://github.com/FreeJHack/ClevoService), install `com.fjhk.ClevoService.agent.plist` into `/Library/LaunchAgents/` and inject `ClevoService.kext` into `/Library/Extensions/`

## What doesn't work?

* dGPU: Since Pascal GPUs have no support since Mojave, it's disabled. By disabling and setting the card into D3 in ACPI, the lowest power state a device can support, the GPU will barely consume any power, so battery life should be improved as well.
* Mini DisplayPort as it's directly conntected to the dGPU
* HDMI Hotplug: This is an issue, we are currently looking into. To get around this, HDMI has to be plugged in during bootup.
* Trackpad has no Magic TrackPad 2 emulation

## How to install

Download this repo and place the EFI folder into your EFI Partition... That's it.

## How to Install macOS Big Sur Beta

There are two ways you can install Big Sur:

Have a working install of macOS, then download the Installer by installing the beta profile and then downloading Big Sur through the "Software Update" section. Then make a bootable Installer with `createinstallmedia` by using this command in Terminal `sudo /Applications/Install\ macOS\ Big\ Sur\ Beta.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`

After you made a bootable Installer, copy the EFI folder to the EFI partition and install as usual. After the installation, mount the EFI of the installed OS and copy the EFI folder to its partition.

A note on Intel WiFi and Bluetooth: While it's possible to get them working with Airportitlwm and IntelBluetoothFirmware, they're not included in this EFI because of stability reasons.
The best advice is getting a card with a supported broadcom chipset like the DW1560, DW1830 or BCM94360NG. A list of supported wifi cards and the needed kexts can be found here: https://dortania.github.io/Wireless-Buyers-Guide/


## Credits

Thanks to:

* sha106b and SkyrilHD (for making an EFI that is working very well)
* acidanthera (for making OpenCore)
* dortania (helping with their troubleshooting guide)
* and to our tester
