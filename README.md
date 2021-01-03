# usb moDems 3g linux doc.

This Repo is to gather notes and docs/tools about how to setup and usage of usb 3g modems.
Some information is just gathered from internet other has been tested by my self.
I own a Zte mf192 modem so documentation for this one has been tested.

Requirements:

for managing the usb 3g modems in linux you will need 
https://www.draisberghof.de/usb_modeswitch/
Probably you will have already it in some form of package for your distribution.
Note: files in etc[/usb_modeswitch.d](/etc/usb_modeswitch.d) you find my config files for mf192 modem.


once you have switched to a modem not storage you can run AT commands using screen command:

    screen /dev/ttyACM0

I've gather some reference manuals with AT commands for different modems.[at_references](at_references)

**Disable storage mode CD of the momem** 
With this trick you will setup the usb modem to go directly into modem mode you will not need usb_modeswitch

Only tested for mf192:
`AT%USBMODEM=0` Enable modem only mode.
`AT%USBMODEM=1` Restore default cd storage/modem mode

For other modems please try:
ZTE

`AT+ZCDRUN=8`  Modem only
`AT+ZCDRUN=9` Modem and storage
Huawei

`AT^U2DIAG=0`  Modem only
`AT^U2DIAG=276` Factory defaults

References from:

https://www.techytalk.info/disable-virtual-cd-rom-drive-with-built-in-software-on-huawei-and-zte-gsm-modem-devices/


