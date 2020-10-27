# Hackintosh_Dell-Inspiron-5570_Catalina
EFI to boot macOS Catalina on a Dell Inspiron 5570

https://www.youtube.com/watch?v=WRyRucc01pI&feature=youtu.be


I do not take complete credit for this, but this is a piece-together from several sources littered around the internet.  There might be some things in here that are not necessary, but as I’ve slowly removed a few kexts, things start running less smoothly.  Experiment and let me know if you find something that needs to be addressed.


## My Device:

Dell Inspiron 5570 with i5-8250U with 1920x1080 full HD display and 12GB of RAM (upgraded) and 1TB SSD (upgraded).

- Must have Sata Mode set to AHCI in BIOS in order for the installer to see your hard drive (perhaps just for SSDs) and then you can go back to RAID once you are installed and booting, and you should. Nothing else has to be changed despite what others have incorrectly stated.


## What doesn’t work:

- OEM supplied wifi card--bluetooth works
- Waking from sleep on AC power


## What does work:

- OEM bluetooth connection
- Waking From Sleep on battery
- FileVault Encryption with APFS without boot lag
- Ethernet
- HDMI video and audio out
- Audio—speakers, mic, headphones
- Video/Graphics
- Backlight Keyboard
- Trackpad, not quite like a real Mac but real close
- Fn Keys—Volume + -, skip, play, pause, forward, back, keyboard backlight, Display backlight dim and brighten, etc
- CPU Management and Thermal Control (as far as I can tell, as the fan cuts on properly and adjust speeds as necessary)
- SSD compatibility with no lag
- with proper SMBIOS information editing in config.plist (easy to find here on GitHub), FaceTime, iMessage, iCloud, etc, all working perfectly


## I am very satisfied with this and how it runs on my laptop.  It works damn near to perfection, and will once my new M.2 wifi card gets here and I get continuity going.

## SIP is disabled by default and unverified kexts are allowed and mounting of root filesystem as rw is possible and gatekeeper can be disabled.


## To Install Proper Clover for Dell Inspiron 5570

- Just delete your CLOVER directory in your EFI folder of your EFI partition
- copy the CLOVER directory from here to your EFI folder on your EFI partition  
- after you get booted after making this change, or after you get installed, copy all kexts from the CLOVER/kexts/other to Library/Extensions and rebuild the permissions using Kext Utility--This is not necessary, but tends to help fix some things. I no longer have mine set up this way and everything is working just fine.


## To install Catalina to your system (since this isn’t very well documented)

- download the Olarila image from here: http://www.mediafire.com/file/8paxpvkianhon4m/Olarila+Catalina+10.15.7.raw.bz2/file
- Decompress and apply that image to a flash drive of 16GB or more  
- mount the EFI partition of the flash drive and delete everything on it
- copy over all the files provided in the Olarila_Install_EFI folder in this repo  

This will successfully get you booting the installer.


## Post Install Power Management

- to get sleep working without modding the BIOS and potentially bricking the device and making it incompatible with features of native Windows, some commands have to be run.
- run each command in the .txt file included in POST_INSTALL, then restart.
