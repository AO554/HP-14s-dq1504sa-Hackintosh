# HP 14s (dq1504sa) Hackintosh Configuration
My (from scratch) Configuration using OpenCore for this specific HP 14s Model.
** I no longer own the Laptop, thus this is being archived.**
**(However you can get Ventura to boot by Updating the Kexts)**

![HPMonterey](https://i.imgur.com/OXAmeR2.png)

# Initial Information

This configuration is for the Ice Lake HP 14s Model Specified (14s-dq1504sa)
The EFI is built upon OpenCore, and took from begining to end 10 Months to complete.

The SMBIOS(es) this EFI is compatible with are `MacBookPro16,2` and `MacBookAir9,1`

Please keep note of this as in the Included EFI there is no Serial Number, MLB, SystemUUID and ROM by Default, you will need to use [genSMBIOS](https://github.com/corpnewt/GenSMBIOS) to make Serial Numbers for your Laptop.

# [Notice] Known Problems

You'll need to read this, as you may experience the same problems as I did when researching and building this configuration.

## Stock NVMe SSD
This laptop (at least for me) came with a Micron 2200 NVMe SSD, **Which is incompatile with macOS.** If you attempt to boot the installer with this Drive **It will Kernel Panic**

## HDMI Output
Ice Lake Laptops seem to have a problem with HDMI Connectivity not working, this means that you will not have the HDMI Port to use for external output. This is because of something in regards to Apple removing the HDMI Stack for Ice Lake. 

You will have to use USB Video Adapters, Apple TV or other AirPlay Devices or something else.

## Touchpad
Initally this did not work without the use of DSDTs and Kexts, if for whatever reason that this does not work in the begining, Rebooting and(or) Resetting NVRAM should fix this.

Once you get into your macOS Desktop, you'll notice the touchpad will hold down instead of a normal click. **You will need to disable the Force Click option under Trackpad in System Preferences.**

![TpdScreenshot](https://i.imgur.com/QSCgF9s.png)

# So what works?

- Intel Iris Plus Graphics (G1) QE/CI
- USB Ports (with USB-C port)
- Audio (with ComboJack)
- Sleep and Wake
- CPU and iGPU Power Management
- Battery
- Brightness
- Function Keys (Brightness function works, Audio Function works, Music Function Works)
- HP Truevision Webcam
- TouchPad (with MultiGesture and Taps)
- SD Card Reader

# What doesn't work?

- HDMI
- Original OEM SSD (Micron 2200 256GB NVMe)
- Stock Wireless Card (Replaced with DW1560)

# Credits to:
- Apple, for macOS (duh)
- OpenCore Team - [@acidanthera](https://github.com/acidanthera)
- u/BudBud2007 - [Reddit](https://www.reddit.com/user/BudBud2007/) - (Helped with Solving Sleep issues among other things)
