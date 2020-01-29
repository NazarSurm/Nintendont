### Nintendont - Without forcing the WiiU gamepad to Player 1 inputs
A Wii Homebrew Project to play GC Games on Wii and vWii on Wii U

This is a small hack that disables player 1 being getting assigned to the WiiU gamepad when Nintendont is launched with a forwarder from the WiiU menu and the "Use gamepad" option is selected. 

This is useful for WiiU users only. It allows you to use the WiiU gamepad to launch a Nintendont forwarder from the WiiU system menu, and then swap to a compatible HID controller (eg: gamecube controller with adapter) once inside Nintendont. By default, selecting the "Use gamepad" option when launching the forwarder would force Player 1 to get assigned to the WiiU gamepad. You could work around this by selecting "Don't use gamepad" when launching the forwarder, but that would prompt the user to point a Wiimote at the screen.

This works by disabling the assignment of the WiiU as a controller for any player. The gamepad will continue to display the game, but will not accpept any inputs. You can turn off the display on the gamepad by holding the power button down for about 5 seconds. When you want to power off the WiiU, you must use the power button on the console, since the shutdown command from the power button on the gamepad will also be disabled.

### Features:
* Works on Wii and Wii U (in vWii mode)
* Full-speed loading from a USB device or an SD card.
* Loads 1:1 and shrunken .GCM/.ISO disc images.
* Loads games as extracted files (FST format)
* Loads CISO-format disc images. (uLoader CISO format)
* Memory card emulation
* Play audio via disc audio streaming
* Bluetooth controller support (Classic Controller (Pro), Wii U Pro Controller)
* HID controller support via USB
* Custom button layout when using HID controllers
* Cheat code support
* Changeable configuration of various settings
* Reset/Power off via button combo (R + Z + Start) (R + Z + B + D-Pad Down)
* Advanced video mode patching, force progressive and force 16:9 widescreen
* Auto boot from loader
* Disc switching
* Use the official Nintendo GameCube controller adapter
* BBA Emulation (see [BBA Emulation Readme](BBA_Readme.md))

### Features: (Wii only)
* Play retail discs
* Play backups from writable DVD media (Old Wii only)
* Use real memory cards
* GBA-Link cable
* WiiRd
* Allow use of the Nintendo GameCube Microphone

### What Nintendont will never support:
* Game Boy Player

### Quick Installation:
1. Get the [loader.dol](loader/loader.dol?raw=true), rename it to boot.dol and put it in /apps/Nintendont/ along with the files [meta.xml](nintendont/meta.xml?raw=true) and [icon.png](nintendont/icon.png?raw=true).
2. Copy your GameCube games to the /games/ directory. Subdirectories are optional for 1-disc games in ISO/GCM and CISO format.
   * For 2-disc games, you should create a subdirectory /games/MYGAME/ (where MYGAME can be anything), then name disc 1 as "game.iso" and disc 2 as "disc2.iso".
   * For extracted FST, the FST must be located in a subdirectory, e.g. /games/FSTgame/sys/boot.bin .
3. Connect your storage device to your Wii or Wii U and start The Homebrew Channel.
4. Select Nintendont.

### Notes
* The Wii and Wii U SD card slot is known to be slow. If you're using an SD card and are having performance issues, consider either using a USB SD reader or a USB hard drive.
* USB flash drives are known to be problematic.
* Nintendont runs best with storage devices formatted with 32 KB clusters. (Use either FAT32 or exFAT.)

### Building Nintendont from Source on Windows
* Install devkitPro from their GitHub https://github.com/devkitPro/installer/releases/tag/v3.0.3
* Run msys2_shell.bat from /devkitPro/msys2/ to get a shell window
* Set paths with the following commands. Note the syntax (/drive/folder/). Your paths may differ, below are defaults.
```
  export PATH=$PATH:/c/devkitPro/devkitPPC/bin
  export DEVKITPPC=/c/devkitPro/devkitPPC/
  export DEVKITARM=/c/devkitPro/devkitARM/
```  
* Navigate to your Nintendont repository and excecute the following command to build Nintendont

```windows=1 ./build.sh```
