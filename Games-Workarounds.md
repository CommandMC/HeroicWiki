## List with several Legendary and Wine Workarounds:
[EpicLinux Wiki](https://github.com/CommandMC/EpicLinux/wiki)

## Heroic Specific

### SuperHot
For some reason, SuperHot Launcher won't work with Heroic since it also runs Electron as well so it is necessary to bypass it:
1. Open the game folder;
2. Rename SUPERHOT.exe to SUPERHOT.exe.bak;
3. Rename SH.exe to SUPERHOT.exe;
4. Rename SH_Data folder to SUPERHOT_data;

### Into The Breach
Steam & GoG have native linux versions of Into The Breach, EGS does not and if you try and load it you'll get a black screen:
1. Open Into The Breach settings inside Heroic Game Launcher;
2. Under Wine > Wine Version, make sure you have a version of Proton select;
3. Under Other > Launch Options, paste PROTON_USE_WINED3D=1;
 
