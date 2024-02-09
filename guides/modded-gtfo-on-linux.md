---
description: basically like it's done on windows
---

# Modded GTFO on Linux

## Steam, GTFO, R2modman

* make sure your gfx drivers are good (other games, glxgears work etc)
* install linux-native steam
* login to steam
* install GTFO
* launch GTFO, make sure it launches and works okay
* if "not responding" after trying to start a level, try x11 instead of wayland (on ubuntu you log out, select user, on password screen you go bottom right of screen gears -> ubuntu on xorg)
* download r2modman for your distro from [https://github.com/ebkr/r2modmanPlus/releases](https://github.com/ebkr/r2modmanPlus/releases)
* launch r2modman, select GTFO, should detect your GTFO directory, can be set from settings if not
* note for AppImage users: use --no-sandbox , otherwise you might get a GPU related error on launch
* create a profile, install the mods you want in it
* click on launch modded, modded launches, enjoy
* Tested to work with r2modman 3.1.34, earlier versions needed some extra steps to launch modded properly (like creating a bat-file to launch modded and a doorstop\_config.ini file with a full path to the BepInEx.Unity.IL2CPP.dll file etc)

## 
