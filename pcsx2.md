## PCSX2 Configuration:

PCSX2 is probably one or the most straightforward emulator to configure. It uses virtual memory cards, right like the physical ones we used to plug into the PS2, where saves are saved and loaded from. The only thing needed to set this up is to copy the memory cards (Mcd001.ps2 and Mcd002.ps2) into the Syncthing folder and point the PCSX2 settings into said folder. 

PCSX2 Settings > Memory Cards > look for the folder path (```/home/user/Syncthing folder/PS2/memcards/```) select Mcd001.ps2 and Mcd002.ps2 and put them in Slot 1 and Slot 2. Once done that, memcards will be loaded and PCSX2 will save on them and will be synced. Once done that repeat the same procedure on the PCSX2 in other clients using the memcards from the Syncthing folder.
