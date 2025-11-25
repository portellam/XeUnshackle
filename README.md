# XeUnshackle
### v1.08
![XeUnshackle_Banner][000]

Custom *Xbox 360* application designed to be used with the [Xbox360BadUpdate][001]
exploit.

Download [here.][002]

[000]: ./Images/banner.gif
[001]: https://github.com/grimdoomer/Xbox360BadUpdate
[002]: https://github.com/portellam/XeUnshackle/releases/latest

##
## 1. Disclaimers

> [!IMPORTANT]
> **THIS APP IS RELEASED AS IS.**
> **YOU ARE RESPONSIBLE FOR WHAT YOU CHOOSE TO LOAD AND ANY NEGATIVE EFFECTS THAT MAY COME AS A RESULT.**
> **THIS IS NOT A PERMANENT SOFTMOD!** Your console will return to an unmodified
state when powered off or rebooted.

> [!CAUTION]
> 1. **BACKUP YOUR NAND!** This should be the **first** thing you do.
> 2. **DO NOT FLASH MODIFIED NAND IMAGES!** You will **brick** your console.
> 3. **DO NOT REPLACE FILES IN FLASH!** This includes things like **replacing**
the `bootanim`.
> 4. **Avoid** using homebrew or plugins that make changes to Flash (the NAND).
> 5. **Read** the [SETUP.MD][100] or `README - IMPORTANT.txt` in the release files for important
notes regarding the use of Stealth Servers.

[100]: ./SETUP.md

## 2. How It Works
Utilises the **alternate** method of using a specially crafted PeekPoke Hypervisor
(HV) expansion to apply **temporary** HV patches. This is usually the preferred
method of HV access used by Stealth servers. Access via the Syscall0 backdoor is
also available upon completion for apps requiring it
([Simple 360 NAND Flasher][200] for example).

Nothing here is particularly new. It's simply a collection of existing code that
has been adapted and packaged for use with this exploit.

[200]: https://github.com/Swizzy/XDK_Projects/tree/master/Simple%20360%20NAND%20Flasher

## 3. Features
- Applies a full complete patchset of both HV and Kernel patches. These are the
same exact patches that are usually applied when building a modified NAND image
using xeBuild for RGH/JTAG consoles.

- Support for both Retail and Devkit signed xex files. Essentially any plugins or
executables that run natively on RGH/JTAG modified consoles _should_ work.

- Reverts any patches applied by the [Xbox360BadUpdate][300] exploit we no longer
need.

- Restores the default state of the Ring of Light and allows controller syncing to
function as normal. Thanks [InvoxiPlayGames][301].

- Loads a slightly modified version of launch.xex (Dashlaunch). Due to it not
being stored within the NAND filesystem it is loaded from app memory and
`lhelper.xex` is copied to either the Hard Disk Drive (HDD) or USB root depending
on what is available at load time.

- Simple GUI consisting of a short boot animation video followed by a page
displaying both the CPUKey and DVDKey of the console.

- Ability to set "Auto-Start" via button press. This permanently skips the boot
animation and exits the simple GUI after a short delay, which can be customized in
the `XeUnshackleAutoStart.txt` file.

- Ability to dump 1BL to file via button press. This may be particularly useful
for those wanting to use the Low Level Emulator [Xenon][302].

- Automatic dumping of the current MAC address on first load. This is often
changed by stealth servers during the initial KV spoofing. Only other way to
retrieve the original is from a NAND backup taken BEFORE loading a stealth.

- Applies Usbdsec patches to allow *non-Xbox 360* XInput controllers.
Thanks [InvoxiPlayGames][303]

[300]: https://github.com/grimdoomer/Xbox360BadUpdate
[301]: https://github.com/InvoxiPlayGames
[302]: https://github.com/xenon-emu/xenon
[303]: https://github.com/InvoxiPlayGames

## 4. Build instructions
See [BUILD.md][400]

[400]: BUILD.md

## 5. Usage
#### 1. Dashlaunch Plugin Loading:
1. Add the plugins you want to load to the [Plugins] section of the `launch.ini`
provided and copy it to the root of the USB.

2. Copy any plugin files to the USB.
Upon successful exploit XeUnshackle will run and attempt to load `launch.xex`
(Dashlaunch) in the background. Dashlaunch will then attempt to load any plugins
set when exiting the app and returning to the dashboard.

#### 2. Save / Dump Options:
Any files saved/dumped can be found in the `BadUpdatePayload` folder of the USB.

## 6. Credits
- [grimdoomer][600] - [Xbox360BadUpdate][601] exploit
- cOz - xeBuild patches, Dashlaunch and much more.
- [Visual Studio / Goobycorp][602]
- Diamond
- [InvoxiPlayGames / Emma][603] - [FreeMyXe][604], [Usbdsec patches][605], Ring of Light fix, [DaTArrest save exploit][606] and general help.
- [ihatecompvir][607] - [DaTArrest save exploit][606].
- ikari - freeBOOT
- [Jeff Hamm][608] - Chain break video - [Xbox360Hub Discord #coding-corner][609]

- [klofi][610] - Added Auto-Start feature and Build
instructions.

- [SavageCore][611] - QA test and fix of the Chain break
video.

- Anyone else who has contributed anything to the *Xbox 360* scene. Apologies if
any credits were missed.

[600]: https://github.com/grimdoomer
[601]: https://github.com/grimdoomer/Xbox360BadUpdate
[602]: https://github.com/GoobyCorp
[603]: https://github.com/InvoxiPlayGames
[604]: https://github.com/FreeMyXe
[605]: https://github.com/InvoxiPlayGames/UsbdSecPatch
[606]: https://github.com/RBEnhanced/DaTArrest
[607]: https://github.com/ihatecompvir
[608]: https://www.youtube.com/watch?v=PantVXVEVUg
[609]: https://xbox360hub.com/
[610]: https://github.com/klofi
[611]: https://github.com/SavageCore

## 7. Community Translations
- Chinese (Simplified) - [firebirdjsb][701]
- French (Canada, France) - [firebirdjsb][701]
- German - [firebirdjsb][701]

- Italian
  - [Razorbacktrack][703]
  - [firebirdjsb][701]

- Korean (Romanized) - [firebirdjsb][701]
- Polish - [firebirdjsb][701]

- Portuguese
  - (Brazil) - [ronniegchagas][704]
  - [firebirdjsb][701]

- Russian
  - [Lowyk][702]
  - (Romanized) - [firebirdjsb][701]

- Spanish - [CiberStore][700]
- Swedish - [firebirdjsb][701]

[700]: https://github.com/CiberStore
[701]: https://github.com/firebirdjsb
[702]: https://github.com/Lowyk
[703]: https://github.com/Razorbacktrack
[704]: https://github.com/ronniegchagas

##
#### Click [here](#XeUnshackle) to return to the top of this document.