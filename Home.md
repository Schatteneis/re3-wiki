Welcome to the `re3` wiki!

## Extra Features

Alongside the original game code, `re3` implements features and improvements that make the game accessible in a many modern configurations.

### Map View

All [releases (.zip)](https://github.com/GTAmodding/re3#installation) includes a custom file called `models/menu.txd`. To enable this feature you must replace it in the game directory. Once done that, a "Map" option will be enabled in the Main Menu (the one when you pause the game). As shown in the figure below, the player can navigate the map and place custom way-points (a gray blip) with mouse right button.

<p align="center"><img src="https://i.imgur.com/LsrJ2p4.png" width="300" alt="Map View"/><br><sup>Image 1: VC's map view in action (backported to III)</sup></p>

### Debug Menu

Debug menu provides a series of in-game settings that can be toggled by the user using the mouse. It can be activated by pressing `Control+M`. The following image (1) shows what it looks like. The code that implements this module can be found in `src/extras/debugmenu`{[.cpp](https://github.com/GTAmodding/re3/blob/master/src/extras/debugmenu.cpp) [.h](https://github.com/GTAmodding/re3/blob/master/src/extras/debugmenu.h)}.

<p align="center"><img src="https://i.imgur.com/GQyUEtX.png" width="300" alt="Debug Menu"/><br><sup>Image 1: Debug Menu in action</sup></p>

## Derived Work

### Platform Ports
* Nintendo Switch: https://github.com/AGraber/re3-nx
* PlayStation Vita: https://github.com/TheOfficialFloW/re3
* Wii U: https://github.com/GaryOderNichts/re3-wiiu

### Features

* [modloader](https://github.com/thelink2012/re3/commits/re3-modloader) by `@thelink2012` - load mods assets (e.g. textures) from a folder without replacing the original game files

### Guides

* [reVC: Graphical Settings](https://hackmd.io/fd3AO6WERxawedSooMvvmg) by `@IlDucci` - comparison with images showcasing the differences of each graphics setting
* [reVC/3: Files Required to Play](https://hackmd.io/fIKsJ4BaSoWV3sEF2lgQhg) by `@IlDucci` - which files do you need in each version of the game (e.g XBOX or PS2) in order to play `re3/VC`