 Resources for HP Elitebook x360 G3 to run macOS 
===================================================

![Oops!There was supposed to be an image here](https://i.imgur.com/v69Qaw2.png)
![Oops!There was supposed to be an image here](https://i.imgur.com/HTPGVm5.png)

 #### What works
- iGPU acceleration (Intel UHD 620)
- Sleep
- I2C Touchscreen
- Trackpad (with gestures)
- Battery Percentage
- Display Brightness
- USB ports
- Audio with mute button (Both internal speakers and Microphone) (cx8400)
- Native Power Management/(Also with cpufriend)
- SMBus Controller
- CPU Temperature Monitoring
- Fan Speed Monitoring (Both left and right fans)
- Trackpad Finger Gestures
- iMessage
- Facetime

#### What doesn't work
- Internal Camera (*unsupported as it is a Windows Hello IR Camera*)

#### Specs

| Component      | Brand                                                            |
|----------------|------------------------------------------------------------------|
| **CPU**        | `Intel i7-8550U ` |   
| **iGPU**       | `Intel HD Graphics UHD 620 `                                         |
| **Audio**      | `Conexant 8400 - Made to work with VoodooHDA`                                      |
| **Ethernet**   | `Realtek RTL8111/8168`                                           |
| **OS**         | `macOS Sonoma Developer Beta 1` |


#### Making the Audio (cx8400) work
- Although CX8400 can be made to work using AppleLAC Layout-12 with the bootarg `alcdelay=1000`, the speaker loses sound when unplugged.
- CX8400 can be made to work using VoodooHDA. Instructions [Here](https://www.insanelymac.com/forum/topic/314406-voodoohda-302/page/19/#comment-2756841).
- Only the speaker device is affected, and the OS is unaware of any problems, nothing on logs suggest there is a problem and as far as the system is concerned, there should be audio coming out, but there isn't. I tried and built AppleALC with different options/layouts disabling DSP to no avail. so I don't think the problem is with the audio codec or AppleALC or AppleHDA, but I believe this problem either involves the Embedded Controller or the SMC-Battery.


#### Not tested
- HDMI output (both audio and video)
- ThunderBolt
- (*Ideally both should work, If some is willing to test, create an issue*)


#### Benchmarks
- Geekbench 5 [Multi-core and Single core](https://browser.geekbench.com/v5/cpu/8013906)

#### Important
- In the config.plist, section `PlatformInfo > Generic`, the following fields are currently edited with CHANGEME. Please generate your own serial. (Reccommended SMBIOS : MacBookPro15,2) 

- This repo can be helpful for other HP Probook/Elitebook series notebooks
 
### Bios Configuration


#### Enable

- Fast Boot
- Runtime Power Management
- Extended Idle Power States
- Deep Sleep
- Power Control
- Turbo Boost
- Virtualization Technology (VTx)
- Hyperthreading
- Multi Processor

 #### Disable
 
- Legacy boot
- Wake when lid is opened
- Wake on USB

#### WI-FI
- Intel WIFI Cards can be made to work using [Airportitwlm](https://github.com/OpenIntelWireless/itlwm). More Details about this [Here](https://dortania.github.io/Anti-Hackintosh-Buyers-Guide/Wireless.html).

#### Having Problems?
Create an issue and I'll try to help as many as I can

#### Credits
- [Apple](https://apple.com) for [macOS](https://www.apple.com/macos/ventura/)
- [Acidanthera](https://github.com/Acidanthera) for [OpenCorepkg](https://github.com/acidanthera/OpenCorePkg) and necessary kexts
- [dortania](https://github.com/dortania) for its detailed guides
- [Corpnewt](https://github.com/CorpNewt) for [USBMap](https://github.com/corpnewt/USBMap)



