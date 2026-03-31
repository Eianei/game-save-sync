[Steam ROM Manager](https://github.com/SteamGridDB/steam-rom-manager) allows ROMs to appear on Steam's UI, this is very handy on Steam Deck and PC players as it allows a quicker launch of emulated games, giving a smoother experience overall. Steam Deck is the main beneficiary though, as it's a hassle to switch to desktop, open the emulator and manually launch the ROM.

To create a folder in the library, close Steam (or in Steam Deck, switch to Desktop Mode, and then close Steam). Open SRM (you can download it on its github page or as a Flatpak image), you will see several options on the left side, select Create Parser. A parser gets all the ROMs of a given folder, and adds them to Steam's library, creating a parameter on lauch to open the ROM's emulator, allowing also to add other instructions like ```--fullscreen``` to open as full screen when launched. 

The most straightforward way to create a parser is to find on the "COMMUNITY PRESETS" and search for the emulator you want to create the parser of, be aware that it makes a difference if the emulator has been downloaded from Flatpak, if it's from RetroArch or manually downloaded. This will autofill most of the options, so you don't need to. 

Other needed changes are the ROM path. In my case I keep all the ROMs in my NAS, but it doesn't matter, NAS, local, wherever it is there's a path, copy and paste it on the "ROMS DIRECTORY" slot. Other changes one can make is the "STEAM COLLECTIONS", it'll just change the Steam Collection name that SRM will create, so choose whatever you want to be named. 

Also double check the launch parameter in "EXECUTABLE CONFIGURATION". Sometimes there won't be a community parser for the source you got the emulator from, you can just use another source and change the parameter name. The launch parameter always will point to the executable, so it will have a syntaxis like this:

```run emulatorlaunchcommand --fullscreen "${filePath}"``` or will be the path of the executable file of the emulator, ```/home/deck/Citra/citra-qt.AppImage```.

This is where the source matters. As seen above, executable files with be a path, this is inside the "EXECUTABLE" blank, however, if downloaded from Flatpak, it will have to include a command line command, indicated in the "COMMAND LINE ARGUMENTS". This is what I meant to double check before, as sometimes the community parser is wrong or it isn't exactly the same source, as I said earlier. 

To check what's the actual command line argument to add if the emulator source is Flatpak, go to ```/home/deck/.var/app/``` and look for the emulator you want, the name of the folder will be the name of the command line argument to run. So for instance, the command line argument of PCSX2 in my case is:

```run net.pcsx2.PCSX2 "${filePath}" -batch -fullscreen -nogui``` or in case of mGBA, ```run io.mgba.mGBA -f "${filePath}"```.

Once checked all these things save and test the parser, if you see the games of the ROM folder, everything should be fine. Go to add games if Steam is still opened, close it, refresh and save to Steam, once it retrieves the artworks and batches everything it will be done. Go to Steam and check libraries, there should be a library with the nametag you put, go inside and launch the game of your choice. Everything should work properly and you should be able to play flawlessly.
