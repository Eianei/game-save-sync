## PPSSPP Configuration

PPSSPP makes it harder to configure as there is no settings to define the path used for saved data. Thus, the only possibility I could think of was creating a symbolic link between the Syncthing folder and the default PPSSPP folder.

To make this, move the SAVEDATA folder of ```/home/user/.config/ppsspp/PSP/``` to the Syncthing folder, once done that use the command ```ln -s ~/Game\ Saves/PSP/SAVEDATA/ /home/user/.config/ppsspp/PSP/```. This will make a symlink betwween the Syncthing folder and the default PPSSPP folder, mirroring the synced folder on the emulators. 

This way the emulator will write and load everything from its default folder, but in reality it's writing everything on our synced folder.
