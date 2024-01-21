# Dell-Optiplex-7040-OpenCore
OpenCore Configuration for Dell Optiplex 7040.
Should also work with 7050 and 7060 by replacing the ACPI files with the correct ones for Kaby Lake & Coffee Lake.

This is assuming you're using a stock model with just the iGPU, and either a SATA HDD, M.2 SSD or both. If using a dedicated GPU, be sure to add the appropriate tweaks needed.

F2 Settings (before installing):
- Uncheck "Enable Legacy Option ROMS"
- Disable Serial Port
- SATA Operation: AHCI
- Secure Boot Enable: Disabled
- Intel SGX Enable: Disabled
- HyperThread control: Enabled (this will only show for Core i7 users)
- (6700K only) Fan Control Override: Check - this will improve thermals

How to install (This is assuming you have a macOS computer available, whether a real Mac or an existing Hackintosh):
- Create a macOS install USB.
- Use MountEFI to mount the EFI partition if on macOS.
- Use GenSMBIOS to create an iMac19,1 SMBIOS and flush it to the config.plist.
- Drag and drop the EFI folder into the root folder of the EFI partition.
- Press F12 upon seeing dell logo and select your USB stick.

Post-Installation:
- Use MountEFI to mount both the macOS and USB EFI partition.
- Drag and drop the EFI folder from your USB stick into the root folder of your EFI partition of your primary storage device
- Unmount both EFI partitions
- Reboot and enter F2 menu to clear the boot list from the Boot Sequence menu
- F12 again and boot to your primary storage.

TO-DO:
- Fix sleep: It currently can enter sleep but cannot wake from sleep properly.
- Fix Realtek HD Audio: The HDMI audio from the iGPU works flawlessly, but for those who want to use the headphone jack, I'll get around to fixing the Realtek audio if not using the HDMI audio.
  - *Workaround:* Plug your speakers into the front headphone jack.  
- ~~Fix monitor replug issue: The monitor may require a replug to work on iMac18,1 and a green screen may appear.~~
  - *Fix:* Use iMac19,1 instead of iMac18,1.
