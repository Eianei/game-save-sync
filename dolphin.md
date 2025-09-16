## Dolphin Configuration

Dolphin works for Wii and GameCube, and like other Nintendo emulators it names games in opening order (read [readme](README.md#nintendo-emulation-folder) for further explaination). 

Dolphin settings however, have more path assignments to make, but they are all folders within the root folder. First copy all the contents of the root folder ```~/.config/Dolphin/``` into the Syncthing folder (you can check the contents on [structure.md](structure.md)). Once done that, go on Dolphin to Config > Paths > and there change the default locations to the same folders but that now are in the Syncthing folder. As said, defaults have to be changed to Syncthing folders: 

- ```~/.config/Dolphin/Wii/``` >> ```~/Game\ Saves/Wii/Wii/``` (this one is redundant as the platform folder is ```Wii/``` and the NAND folder is also called Wii).
- ```~/.config/Dolphin/Dump/``` >> ```~/Game\ Saves/Wii/Dump/```
- ```~/.config/Dolphin/Load/``` >> ```~/Game\ Saves/Wii/Load/```
- ```~/.config/Dolphin/ResourcePacks/``` >> ```~/Game\ Saves/Wii/ResourcePacks/``` 
- ```~/.config/Dolphin/WFS/``` >> ```~/Game\ Saves/Wii/WFS/```

That will change paths for Dolphin, so now it will write directly to the Syncthing folder.
