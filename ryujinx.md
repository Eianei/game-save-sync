## Ryujinx Configuration

Ryujinx is like other Nintendo emulators as it arbitrarily names game saves folders by playing order, just like Citra or Dolphin, but it is easier to back up its configuration and saves as everything is contained in the ```bis``` folder. Within ```bis``` there is a ```system``` folder with all system files and configuration (just like ```nand``` of Citra or Dolphin); and a ```user``` folder, that contains all saved game data (like the ```smdc``` of Citra).

So, to back Ryujinx up, just copy the ```bis``` folder located in ```~/.config/Ryujinx/``` and drop it in the Syncthing folder. 

Ryujinx does not allow to change paths, so just create a symlink between the Syncthing folder and the default Ryujinx folder to make the emulator believe it's writing its default instead of the synced folder: ```ln -s ~/Game\ Saves/Switch/bis/ ~/.config/Ryujinx/```.

This way we'll have both, system data and game saves backed up and no matter the system we play in, the emulator will recognise the arbitrarily named folders, as it will share the same nomenclature. 
