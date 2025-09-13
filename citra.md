## Citra Configuration:

Citra is, like most of Nintendo's console emulators, a bit more messier to configure, as it requires both ```nand``` and ```sdmc``` folders. The former is the virtual SD card, which saves saved data, DLCs, pictures of games... and the latter, which simulates the NAND of the console, storing system configuration and data. 

Syncing ```nand``` is crucial because all these Nintendo emulators create save folders arbitrarily named after the order in which you open each game, this means that, if you have Citra and a backup of your Pokémon X and Bravely Default copies, and you open them in that order, Citra will name "00000001" the Pokémon X save data folder, and "00000002" Bravely Default's one. However, if I have the same games, and open them in reverse order, my "00000001" will be Bravely Default and my "00000002" will be Pokémon X, causing thus a conflict not only in names, but in the saved data format within the folders.

Backing up ```nand``` ensures that the emulator will always recognize each arbitrarily chosen name as the same name on each device. To do this, simply copy the ```nand``` and ```sdmc``` folders and dump them in the Syncthing folder, and then go to:

Citra > Emulation > Configure... > System > Storage and once in there, tick the "Use Custom Storage" box and select the Syncthing folder (```/home/user/Game Saves/3DS/nand/```) as the path for ```nand``` and ```/home/user/Game Saves/3DS/sdmc/``` for ```sdmc```. Once done that, it will share the same configuration in every device, ensuring the codes given for each game is the same.
