# Hackintosh-Dell-Latitude-7390-2-in-1-OpenCore-EFI


EFI for MacOS Big Sur 11.5.2, using OpenCore 0.7.2 (as of 28/08/2021). 


## What Works

- Sleep (mostly, see below)
- MicroSD card reader
- USB 3 ports
- HDMI
- Web camera
- Touchpad 
- Touchscreen
- Pen support (with palm rejection)
- Keyboard

## What You Need to Add

- SMBIOS info (see the [platform info](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#platforminfo)) section in the Dortania Opencore Guide (specifically, the *MLB*, *SystemSerialNumber* and *SystemUUID*).


## What Needs Work

- Either thunderbolt 3 OR sleep works. The EFI contains all the necessary files to get hot-swappable thunderbolt 3 to work (just make sure it is enabled in the BIOS); however, sleep doesn't work at the moment. Disabling thunderbolt 3 in the BIOS will allow the hackintosh to sleep most of the time. When it is disabled, the USB C ports will work for USB drives if they are inserted before booting (causing sleep to break). I think this porblem is due to the thunderbolt 3 controller not waking from sleep properly. Interestingly, when thunderbolt 3 is enabled, I have managed to wake my hackintosh from sleep when connected to my thunderbolt 3 dock.

- Sound doesn't work after the hackintosh has woken up from sleep. I'm not sure why this is, it might be the thunderbolt kexts and SSDTs causing all manner of issues. If someone figures this out, please say!

- Brightness keys (currently mapped to Function + S, Function + B) are not mapped to the arrow keys.

- iServices - follow Dortania's OpenCore guide to sort this out.

## Future Development

As this originally started as a personal side project during my Christmas break, I failed to properly document the sources for each kext, driver etc. and the reason wht they were necessary. At some point in the future, I will start from scratch and work out the reason for each additional file and change to OpenCore. Hopefully, this will fix the sleep issues that are the main issue at the moment.
