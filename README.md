# [CLICK HERE TO OPEN UVMOD RX-TX](http://uvmod.ddns.net/) *feature work*
## [中文版 Open Chinese Version (maintained independently)](https://uvmod.xanyi.eu.org/)
# [UVMOD in Russian Language Version](https://uvmod.valek.net.ru/)

[Discussion forum 4PDA](https://4pda.to/forum/index.php?showtopic=1071343&st=0) | [Telegram Group](https://t.me/uv_k5/34434) | [Chinese Mod collection](https://www.zhihu.com/people/troilusxi) | [Japanese Mod collection](https://www.nazononiku.com/uncategorized/uv-k5%E3%81%AE%E3%83%95%E3%82%A1%E3%83%BC%E3%83%A0%E3%82%A6%E3%82%A7%E3%82%A2%E3%82%92%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%82%A4%E3%82%BA/686/)

## Introduction

Web-based client-side Quansheng firmware patcher written in Javascript and HTML.
It is based on the discoveries by the many contributors in the [uvmod-kitchen](https://github.com/amnemonic/Quansheng_UV-K5_Firmware/tree/main/uvmod_kitchen) and [Tunas1337 UV-K5 Modded Firmwares](https://github.com/Tunas1337/UV-K5-Modded-Firmwares). Implements the **same functionality** not limited to RX only but also TX in a modular and flexible javascript structure. This is an enhanced UVMOD based on [whosmatt UVMOD src]([https://github.com/whosmatt/uvmod).

Visitors can generate a patched firmware image by selecting the desired patches. Patches modify the firmware on a binary level and can accept user input to customize variables. A custom base image can be supplied to allow support for mods that are compiled and linked directly into the firmware. 

## Copy and Host it, upload it on your own Webspace

Simply download the [latest files in a zip file](https://github.com/RE3CON/uvmod/archive/refs/heads/main.zip) and extract it, upload it to your own webspace hosting.

## Extract/Encoding Firmware binaries

Firmware version spoofing modded firmware v2 for v3, v4 uv-5r plus
1. Download file [qsfirm.py](https://github.com/RE3CON/Quansheng_UV-K5_Firmware/blob/main/firmware/qsfirm.py) and place it into the same folder with [yourfirmware.bin](https://github.com/RE3CON/Quansheng_UV-K5_Firmware/tree/main/firmware)
3. Run command: qsfirm.py unpack yourfirmware.bin fw.dec.bin fw.ver.bin
4. Edit file fw.ver.bin in hex editor to start with the fw version it should be flashed for example for v4, replace it with 4.00.01. A * makes it universal for all versions.
5. Run command: qsfirm.py pack fw.dec.bin fw.ver.bin yourfirmware_mod_v4.bin

## Mod development

Clone this repository and execute `python3 -m http.server` or `python -m http.server` in the root directory for an instant local web server, allowing easy testing.  
Mods are defined in [mods.js](mods.js), with an example mod to outline the pattern.  
Also __refer to the helper functions and documentation in__ [modframework.js](js/modframework.js).  

The supported format for binary data is in the format of a hex string __without separators__. You can use find and replace to remove all `\x` from a regular hex string or directly export the correct format from a bytes object in python using `print(''.join('%02x'%i for i in BYTES_OBJECT))`.

## **Comming soon** 
Offline universal firmware version patcher
based on search and replace pattern to change and modificate with precission the functions of these patches direct on all firmware versions and upcoming versions files.<br>

## Credits, rules and trouble maker...
"I'll take in account an EU Country block on a new DNS domain cause of different law regulations in whosmatt location. Threatens me with reference to DCMA is a taboo that's absolutely frowned upon among open source coding communities. A No-Go by doing shared code works. Sadly to be afraid from TX mods and freq limits >999MHz, 4 freq digits in MHz range will never match on the LCD screen, not to talk about changing the way how the direct keypad input should be changed to accept numbers higher than 999.999,99. However he's desided to copie my TX unlock code and maybe sooner or later my Tunnas1337 diffs done for TX and RX from 18-1300MHz Mod without paying propper credits back."

*Credits and thanks to whosmatt!*
