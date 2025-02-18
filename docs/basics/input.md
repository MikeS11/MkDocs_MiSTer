---
hide:
  - toc
---

MiSTer has support for a wide variety of input devices. It also has options to configure these devices to fit your needs in addition to several quality of life features across most, sometimes all, cores. Here is a breakdown of some special configurations for various input devices like spinners, gamepads, joysticks, and keyboards.

MiSTer has a set of standard features for USB gaming controllers:
* Up to 6 player support
* Auto Fire
* Mouse emulation from your joystick

## Joystick player assignment

Up to 6 player controllers are supported (depending on core):

* After a core starts, press a button on any connected controller to make it the Player 1 gamepad/joystick
* Press a button on a second controller to make it the Player 2 joystick (if supported by the core)
* Keep going for assigning Player 3, Player 4, etc...
* If you assigned the players in the wrong order, it's easy to start over, just go to the On-Screen Display's secondary menu (press Right after going into the OSD) and select "Reset player assignment" to start all over again.
* If you reset the core, it also resets the player assignments.

Please note; if a controller doesn't seem to work, it's possible you will need to reboot the MiSTer into the Menu core, and define the inputs for that controller if it hasn't been done already. Also, if the controller attached has the same Product ID and Vendor ID as seen by the linux system, you may not be able to use two of them at the same time. It depends upon how the controller is made to work.

## Auto Fire

Any defined button (except the d-pad) supports the auto fire feature. To activate auto fire, press and hold the desired button and then quickly press and release the button defined as `BUTTON OSD`(for joystick) or `KBD TOGGLE`(for keyboard). To deactivate auto fire, repeat the the same procedure for that same button you set before.

Auto fire rates can be modified by increments of 32ms all the way up to 1024ms (repeating the button once every second). To change the speed, press and hold a direction on the d-pad and then quickly press the button defined as `BUTTON OSD`(for joystick) or `KBD TOGGLE`(for keyboard). Up or right increases the delay of the auto fire while down and left decrease the delay. Some games will not function properly if the auto fire rate is too fast, so this is a useful feature to keep in mind if you run into problems.

## Mouse emulation

Your joystick can emulate mouse if the required button "Mouse Emu" has been defined when you defined your inputs in the Menu core. Hold the `Mouse Emu` button and ++alt+m++, Mouse Left/Right/Middle Btn will emulate the mouse functions. When Mouse emulation is activated, the left analog stick (if defined earlier) will be switched to pointer functions for the mouse. Press `BUTTON OSD` while holding `Mouse Emu` to toggle mouse emulation permanently. In permanent mouse emulation the `Mouse Emu` button becomes a sniper button with smaller pointer movements. Only the buttons defined for mouse emulation will be switched. Other joystick buttons will continue to act as regular joystick buttons. Thus, if your game pad has many buttons, you can have both mouse and joystick in one game pad at the same time (useful for some games, like Walker on Amiga).

## What devices are supported?

Generally speaking, any normal USB HID compatible input device should work. Keyboards, arcade spinners, usb adapters for original controllers such as the Raphnet and Daemonbite retro adapters, and even modern console controllers like the DualSense PS5 controller. There is even the Serial Native Accessory Connector, if you have one of the Analog or Digital IO add-on boards, which on supported cores allows you to use original hardware controllers, such as lightguns, which would normally only work with the original system and require zero lag to function.

## Serial Native Accessory Convertor (SNAC)

SNAC adaptors allow you to connect original hardware controllers and peripherals to the MiSTer cores. The cores which support SNAC connections have been specially built to have serial connections exposed to specific pins on the DE10-Nano. That means when you pull the trigger on the NES Zapper while aiming at your CRT, the signals travel almost instantly, similar to how they would on original hardware.

## Using A Mouse

You can also use a mouse for various purposes on the MiSTer. The main purpose for mouse support is for use with some computer cores which had mice.

One of the cool things you can do is use the mouse as an emulated lightgun. The same principles behind doing this applies to a wiimote with a powered sensor bar. You can do this by pairing your wiimote to the MiSTer and it will be used as a Mouse when paired.

![type:video](videos/mouse-lightgun.mp4)

You can also use a mouse for a paddle style controller if you'd like.

## Are gaming keyboards worth it?

High performance and expensive keyboards and mice aren't advantageous to use for MiSTer. They won't give any major or even minor significant benefits. Additionally, these devices often have too many functions and many virtual devices cluttering the input subsystem which may introduce input lag or be complete unresponsive. They may also prevent other devices, such as gamepads, from working. So if you experience problems with your gaming keyboard, try a simpler keyboard instead to see if that resolves the issue. General advice is not to go out and buy a specialty gaming keyboard for MiSTer specifically, it may end up being a waste of money.

## What about rumble support?
Rumble support was just recently added into the framework in preparation for the release of the Playstation core on MiSTer. There are only a handful of systems that need support added and the support will be added at a later time.

## What about PS3/PS4/PS5, XBoxOne/360, Switch, and 8bitdo receivers/gamepads?
The ideal solution today for these types gamepads is to use 3rd-party receivers, such as 8bitdo retro receivers, specifically the 8Bitdo Wireless Bluetooth Adapter, or any number of name-brand Bluetooth 4.x/5.0 receivers. The 8bitdo receiver easily supports Xbox One S/X, PS3, PS4, Wii, Switch, and 8Bitdo's own gamepads and it can pair easily without using the bluetooth setup menu. One 8bitdo bluetooth receiver will pair with one controller at one time. If multiple controllers are required for multiplayer games, then multiple receivers will need to be purchased if you are using the 8bitdo receiver, however a regular Bluetooth usb receiver does not suffer from this limitation.

The 8bitdo receivers have been reported as having some lag introduced, limited range, and bad line of sight, when compared to Bluetooth 5.0 adapters (like the TP-Link and Asus ones). The main appeal of the 8bitdo receivers is the ease of use and quick pairing. The 8bitdo receivers act as a controller themselves and are a compatibility layer between your paired controller and whatever they are attached to via USB, for easy compatibility. Bluetooth adapters by comparison pair your controller itself directly as a device to the MiSTer. No matter what controller you connect, the 8bitdo receiver will see it as the same controller, the 8bitdo receiver's controller. This means that some features like the DualSense (PS5) controller's added mute button and touchpad will not be available, whereas using bluetooth 5.0 may run a very minor risk of limited compatibility (until device support is added into the framework and linux by the development team), but will come with every feature.

The Grey/Orange (brick decorated) USB Adapters are functionally the same, after using the latest firmware. Gamepads may switch to different input modes using hotkeys for different functionality (depends upon the model of controller, some have a switch on the back like the 8bitdo SN30 Pro 2). Note that documentation on 8Bitdo's site doesn't specify this, but the update logs for the firmware updates does.

* X-Input mode: Hold SELECT+UP for 3 seconds.
* PSC (Playstation Classic) mode: Hold SELECT+DOWN for 3 seconds. This is useful for gamepads which are limited in buttons (12 total; DPAD counts as 4) and need to access the MiSTer OSD menu. Note that the OSD menu should not be assigned when configuring buttons in the main MiSTer menu core, as the L+R+START combination will bring up the OSD while in the cores. The combination is hard-coded in MiSTer specifically for 8Bitdo adapters. You may also lose auto-fire/mouse functionality in this mode.

Alternative 8Bitdo adapters, such as the 8Bitdo Console Retro Receiver (SNES, NES, Genesis) are always in X-Input mode when connected via microUSB.

## JammaSD support

MiSTer supports the use of a JammaSD by detecting if the pressed buttons are from player 1 or 2. You first have to configure player 1 in main menu (as a joypad) (and also remap it in cores if needed). Player 2 inputs will be auto defined, like if it was a second identical joypad. JammaSD support was added with a VID/PID that should be the same across all devices, but if your device has a different VID/PID, you can adjust it in the MiSTer.ini file.
