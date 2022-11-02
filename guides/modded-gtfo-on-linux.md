---
description: describes the steps to get a modded gtfo up and running
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
* launch r2modman, should detect your GTFO directory, can be set from settings if not
* create profile, install the mods you want
* r2modman will most probably either launch vanilla gtfo or complain about path , so the bat-file below is a circumvention to launching.

![](<../.gitbook/assets/image (5).png>)

## GTFO modded.bat

Assuming your r2modman profiles are in \~/.config/r2modmanPlus-local/GTFO/profiles/ , create a modded.bat in your GTFO folder, modify the path to the DLL as necessary:

```
GTFO.exe --doorstop-enabled true --doorstop-target-assembly "z:\home\user\.config\r2modmanPlus-local\GTFO\profiles\profilename\BepInEx\core\BepInEx.Unity.IL2CPP.dll"
```

Then on steam, properties of GTFO, set "modded.bat" as the launch parameter.

``![](<../.gitbook/assets/image (7).png>)``

* caveat: for changing r2modman profile, you have to modify the directory of the dll in modded.bat

Once done, from steam, double click GTFO, bepinex console window should pop up and modded GTFO should begin. You're set.

## Untested stuff

R2modman will provide a doorstop\_config.ini into GTFO game folder, so from the modded.bat file, a simple "--doorstop-enabled true" might suffice, provided that you first attempt r2modman "start modded" from a selected profile (put the doorstop\_config.ini in place).

R2modman might be able to launch modded gtfo directly but from my early tests, steam seems to blatantly ignore the launch params that r2m provides. if someone discovers a away or would like to point out my mistake, please do edit this page thanks :)

## Closing

for questions or further explanation, ask for help on the modding discord.

(all screenshots and tests done on ubuntu 22.04, successful level drop with xorg-x11 as wayland went not responding on level drop).
