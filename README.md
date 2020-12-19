# Hackintosh-Lenovo-M73-miniPC
Files and notes to get MacOS running on a Lenovo M73 miniPC

### Confirmed working on:

- MacOS: Big Sur 11.0.1	&amp; 11.1	

- OpenCore: 0.6.4		
#
### Disclaimer: 
This is not meant to be a thorough guide or walkthrough. It is merely a dump of files and notes to get MacOS working on a Lenovo M73 miniPC. I will try to keep this updated as I update my miniPC to future MacOS releases. It's not guaranteed to work on your specific device. If it doesn't, you likely need to make some sort of changes to the supplied config.plist. I do not know what those changes may be. I am not responsible for any damage done or data lost by attempting this.		
#
- Update 12/19/2020

- OpenCore 0.6.4		
- Confirm Big Sur official release compatibility		
### Requirements:		

- Core i3 or Core i5 processor, Me is core i3-4330T with intel HD 4600 		
- OpenCore 0.6.4		
- Minimum of a 32GB SSD		
- Minimum 64GB recommended		
- WiFicard Atheros AR9280  use HS80211Family https://www.insanelymac.com/forum/files/file/1008-io80211family-modif/	
- USB Bluetooth adapter CSR8510 A10	
- MacOS installer flash drive		
- See the guides linked in Basic Installation Steps below		

### What's Working:		

- Just about everything!		
- Graphics（DP with Audio out, Up to 4K 60hz）		
- Audio out		
- Bluetooth		
- Wifi	
- Ethernet
- Sleep		
- etc……		

### What's Not Working:

- Most DRM does not work. This means no Apple TV shows, Hulu, Netflix (in Safari), Amazon Prime streaming, etc.
This isn't specific to the Dell CB13. DRM simply does not work on an iGPU only Hackintosh			
- Microphone	
- airdrop handoff

## To Do:

- Enjoy MacOS!		
- Before Getting Started		

- I strongly suggest becoming familiar with Hackintoshing before jumping into this. Know the downsides, shortcomings, and difficulties. Read through the dortania guide, poke around on r/hackintosh, have a look around InsanelyMac and TonyMacX86 (even though their tools aren't used here, they still have a lot of useful information), and do some general web searches. Even if a lot of it doesn't make sense, just reading through it and becoming familiar with terms will be helpful!
- Updates to MacOS, OpenCore, or firmware may break your installation! I will likely be keeping my device up to date so check back here before doing any MacOS, OpenCore, or firmware updates! The latest confirmed working versions will always be at the top of the this page.
- Don't let this section scare you off! Once MacOS is up and running on your system, it is very stable!		
### Basic Installation Steps		

- Create a MacOS installer flash drive		
- A guide can be found here		
- Download OpenCore 0.6.4 and copy only the files shown in this screenshot to your flash drive, keeping the folder structure as seen in the image		
- Download all of the required files		
- Be sure to make any edits mentioned - particularly to config.plist 	
- Move the required files to their appropriate locations on your installer flash drive		
- Your EFI folder should look like this - make sure all of the files are there 		
- Boot to your installer and install MacOS		
- Boot into MacOS using your installer flash drive and copy the EFI folder from you installer flash drive to the EFI partition of your internal SSD - you can - - - mount the EFI partition with MountEFI		
- More info can be found here		
- Follow the post install steps below		
### Post-Install		


- Disable hibernate with "sudo pmset -a hibernatemode 0"		
- Map Full Screen and Mission Control keys		
-- Optional: Give OpenCore a GUI menu and boot chime		
- Use this OCEFIAudio_VoiceOver_Boot.wav as it is resampled to work with the CB13		
- If you want a full Hackintosh guide (not Chromebook specific), I suggest this one: https://dortania.github.io/OpenCore-Install-Guide/ - most of the files in - this repo were created using this guide so you won't need to generate them yourself. Simply pull them from here as you go through the guide.		

### Required Files		

- OpenCore Config		

- Place config.plist in /EFI/OC/		

- Use ProperTree to make the following edits to the config-base.plist file		

- Follow the PlatformInfo portion of this guide to edit the config.plist		
- You can use GenSMBIOS to generate the SMBIOS info		
- Use a MacMini7,1 profile		
- In the config.plist, you need to fill in values for: SystemProductName, SystemSerialNumber, MLB, SystemUUID, and ROM		
- Use your MAC address without the colons for the ROM field (You did get your MAC address, right?)		
- Be sure to rename the config file to config.plist		
### OpenCore Drivers		

- These are included with the OpenCore download unless noted otherwise. Place these in /EFI/OC/Drivers		

- AudioDxe.efi		
- HfsPlus.efi		
- OpenCanopy.efi		
- OpenRuntime.efi		

### SSDT files		
- Place these in /EFI/OC/ACPI		

- SSDT-EC-DESKTOP.aml		
  - Creates a phony EC controller - required to boot Big Sur		
- SSDT-EHCx_OFF.aml		
- SSDT-PLUG-DRTNIA.aml		
  - Enables proper CPU power management		
- SSDT-SBUS-MCHC.aml		

### Required Kexts		

- Place these in /EFI/OC/Kexts		

- AppleALC.kext		
- Lilu.kext		
- WhateverGreen.kext		
- VirtualSMC.kext		
- FakePCIID.kext	
- SMCProcessor.kext		
- SMCSuperIO.kext		
- AirPortAtheros40.kext	
- HS80211Family.kext	
  Atheros AR9280 wireless card
- IntelMausi.kext
  Intel Ethernet device	
- USBPorts.kext	
- USBPower.kext			



## Credits &amp; Sources (in no particular order and maybe missing some)		

- Apple				
- https://github.com/acidanthera		
- https://github.com/alexandred		
- https://github.com/RehabMan		
- https://github.com/corpnewt		
- https://www.insanelymac.com/		
- https://www.tonymacx86.com/		
- https://reddit.com/r/hackintosh			
</pre></body></html>
