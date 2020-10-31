- I have a real Macbook which is what makes most of this possible, just fyi.
- starting from scratch without one isn't impossible but not as simple, nor allows clean access to the Catalina installer

# Hackintosh_Dell-Inspiron-5570_Catalina

- EFI to run macOS Catalina on a Dell Inspiron 5570

- https://www.youtube.com/embed/WRyRucc01pI

## Installer 

- https://github.com/stayboogy/Installer_Dell-Inspiron-5570_Catalina


I do not take complete credit for this, but this is a piece-together from several sources littered around the internet.  There might be some things in here that are not necessary, but as I’ve slowly removed a few kexts, things start running less smoothly.  Experiment and let me know if you find something that needs to be addressed.


## My Device:

Dell Inspiron 5570 with i5-8250U with 1920x1080 full HD display and 12GB of RAM (upgraded) and 1TB SSD (upgraded).

- Must have Sata Mode set to AHCI in BIOS in order for the installer to see your hard drive (perhaps just for SSDs) and then you can go back to RAID once you are installed and booting, and you should. Nothing else has to be changed despite what others have incorrectly stated.


## What doesn’t work:

- OEM supplied wifi card--bluetooth works
- Waking from sleep on AC power


## What does work:

- Camera
- USB
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

- Mount your Hackintosh's EFI partition with Clover
- Delete your CLOVER directory in your EFI folder of your EFI partition
- Copy the CLOVER directory from here to your EFI folder on your EFI partition  
- (Optional) After you get booted after making this change, or after you get installed, copy all kexts from the EFI/CLOVER/kexts/other to Library/Extensions and rebuild the permissions using Kext Utility--This is not necessary, but tends to help fix some things. I no longer have mine set up this way and everything is working just fine.



