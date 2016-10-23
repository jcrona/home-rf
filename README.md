# Home-RF - A Web UI to control 433MHz OOK based devices (Web UI for rf-ctrl)


## Synopsis

Home-RF is a web UI providing a nice interface to the __rf-ctrl__ command-line tool. The rf-ctrl tool allows to control 433MHz OOK based devices (such as plugs, switches or chimes), and can be found here -> https://github.com/jcrona/rf-ctrl.
Home-RF let you register several switches and chimes (presets) in order to get a graphical remote to control them. You can also register devices that supports the WakeOnLan functionality.

For Home-RF to work properly, you will need the __rf-ctrl__ and __etherwake__ tools.
Please note that Home-RF does not support authentication yet, so an other way to control the access to the web UI is needed in order to use Home-RF from outside the local network, such as SSH, OpenVPN, or htaccess.


## Presets file

The registered devices are stored in a presets file, which must be edited with Home-RF's __Preset Editor__.
Home-RF understands three types: __switch__ for switches and plugs, __chime__ for chime, and __wol__ for WakeOnLine compatible devices.
The syntax is the following:
```
switch | <name> | <protocol> | <remote ID> | <device ID>
chime | <name> | <protocol> | <remote ID> | <device ID>
wol| <name>| <interface> | <MAC> | [password]
```
For instance :
```
switch|Camera|otax|31|16
chime|Carillon|dio|24|42
wol|Desktop PC|eth0|00:42:42:42:42:00
```


## OpenWrt support

In order to build Home-RF as an OpenWrt package and/or add it to an OpenWrt firmware build:
- checkout an OpenWrt build tree (only tested on Barrier Breaker 14.07 so far)
- create the __openwrt/package/utils/home-rf__ sub-folder and place __OpenWrt/Makefile__ in it
- create the __openwrt/package/utils/home-rf/files__ sub-folder and place the __www__ folder in it

Now, if you run `$ make menuconfig` from the __openwrt__ root folder, you should see an __Home-RF__ entry in the __Utilities__ sub-menu !


## License

Home-RF is distributed under the GPLv2 license. See the LICENSE file for more information.


## Miscellaneous

So far, Home-RF has been successfully tested on a regular Linux PC, a TP-Link TL-WR703N router running OpenWrt, and a Raspberry Pi.
Check out also my [rf-ctrl](https://github.com/jcrona/rf-ctrl) and [ook-gpio](https://github.com/jcrona/ook-gpio) projects to be able to control a 1$ 433MHz transmitter connected to a TP-Link TL-WR703N router or any other device running OpenWrt.

Fell free to visit my [blog](http://blog.rona.fr), and/or send me a mail !

__  
Copyright (C) 2016 Jean-Christophe Rona
