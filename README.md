## Disclaimer

This repository is intended solely as documentation of my personal setup for managing and syncing save files across devices.  
I do not condone or endorse piracy. All games I use with these emulators have been legally obtained, and it is each individual's responsibility to ensure they comply with their local laws when acquiring and using game software.

## Introduction:

This is my personal set-up for the [Syncthing](https://github.com/syncthing/syncthing) directory for game saved data synchronization. It is detailed specifying each emulator settings and explained why it is made that way and what was done to fix issues in case there was when setting up the whole configuration. 

Each emulator's features and specific set-up will be explained on "emulator-name".md; a general structure example in [structure.md](structure.md); and future project modifications, like other emulators additions or set-up modifications will be added on [future-changes.md](future-changes.md). I am also open to requests, and I will try to add requested emulators.

## Why Syncthing?

Syncthing works by creating and sharing a directory across devices, and checking if any change has been made to that directory. If a change was made, it synchronizes the modification on every device that is on the P2P net so it does not have a single point of failure. Scanning constantly also makes the saved data to be up to date on any playable device and securing data integrity, and allowing the user to resume the game in the same spot that was left on other device in any moment. Additionally, it has a system of public relays where you connect via UPnP (so no port forwarding is needed) if LAN is not available. Therefore, local connection is not necessarily needed to accomplish the synchronization. Thus, Syncthing makes a reliable, quick and easy tool to backup data between devices, making it perfect for the set-up presented in this repository. 

Then Syncthing would be used to have a set of directories cointaining the games saved data and syncing it across devices, ensuring integrity and availability of the saves in any client. 

Summing it up:

- Shares a directory across devices and syncs any changes automatically.
- Keeps save data constantly (each few seconds) updated across devices.
- Avoids a single point of failure. 
- Uses public relay servers if direct LAN is not available.

I thought of this possibility when I started using Syncthing to synchronize my Obisidian vault, and after tinkering a bit with emulators settings I ended up with this set-up, which has proven reliable and scalable. 

## Imporant Considerations

- Throughout the repository, both Syncthing folder or Game Saves folder (```~/Game\ Saves/```) will be mentioned indistictly. Both are the same folder and it's the folder created in Syncthing to share across devices, then other directories can be created within to each person's liking.
More detailed diagram in [structure](structure.md). 

## Peers:

In this set-up, the peers used were my main gaming PC, my MacBook Air M2 and a Optiplex 5070 that sits in my living room with the living room TV as its display. All three have the same emulators installed and are platforms to play in. In a near future a Steam Deck will probably be the next device that will share this same backup system. Anyway, that is my set-up, each one can make it however they want as it has proven to be a scalable solution, so the more devices, the more peers to add to the P2P network. 

## Emulators:

The emulators and subsequent folders (named by the platform) used in my set-up are:

- [PPSSPP](https://github.com/hrydgard/ppsspp): for PSP.
- [PCSX2](https://github.com/PCSX2/pcsx2): for PS2.
- [DeSmuME](https://github.com/TASEmulators/desmume): for Nintendo DS.
- Citra*: for Nintendo 3DS.
- [Dolphin](https://github.com/dolphin-emu/dolphin): for Nintendo GameCube and Wii.
- [Cemu](https://github.com/cemu-project/Cemu): for Nintendo WiiU.
- [Ryujinx](https://git.ryujinx.app/ryubing/ryujinx/-/tree/master): for Nintendo Switch.
- Steam: not an emulator, however I backed up the saved files of Steam games. Extracted from [Steam Cloud](https://store.steampowered.com/account/remotestorage), thus, not relying only on Steam as the sole saved data storage.
  
*Citra was discontinued due to Nintendo's cease and desist and is currently being continued on [Azahar](https://github.com/azahar-emu/azahar), however, the functionality is different as the latter doesn't use the same game format. When I started this project, Citra was still in development and it was the emulator I used, and still use. 


## Procedure:

The way the set-up was made was by simply creating a set of directories in the Syncthing main folder (Game Saves), and selecting them in emulator's settings as the default data directory. Quick and simple. 
   
However, some emulators have a "complicated" save procedure or make it harder to change emulator's path settings. Therefore, more complicated set up for specific emulators or symlinks come into play. Each emulator will have a .md file in the repository explaining its peculiarities and why it was made the way it was made. 

## Nintendo Emulator Folders:

Some Nintendo emulators work by assigning arbitrarily each game saved data folder a name in the opening order. Therefore, backing up the system folder of each emulator is crucial, otherwise, you would need to open games in the exact same order to make each emulator on each device name each folder the same way, and even made this way I don't exactly know if it would work properly. Further explained and exemplified:

If I have a Steam Deck and my main PC with Citra installed, platforms where I will play my back up copies of Monster Hunter 4 Ultimate and Pokémon X, opening the former will create a folder named "00000001", a name assigned internally by the emulator for MH4U; and when I would open the latter, it would create a folder named "00000002" assigned for Pokémon X. Reversing the order would have made Pokémon X to be "00000001" and MH4U "00000002". 

The system information that has mapped which folder is which game is contained in the ```nand``` folder, so just by syncing this folder across deviced will make the emulators to share the same folder mapping and thus, not conflicting save folders names. This example was made with Citra naming and 3DS games, but the same would be applied with slight changes on other Nintendo emulators like Ryujinx. 
