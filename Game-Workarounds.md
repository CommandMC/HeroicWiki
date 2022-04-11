## List with several Legendary and Wine Workarounds:
[EpicLinux Wiki](https://github.com/CommandMC/EpicLinux/wiki)

## Save Game paths
For Cloud Sync to work as expected, where a game saves and syncs is very important to get right. Ensure that Heroic's save location is actually where the game saves! (Windows games, for example, are likely saving directly inside the WINEPREFIX root, for obvious reasons)

## Heroic-specific

### SUPERHOT
The SUPERHOT launcher does not work with Heroic, since it also uses some Electron components. Luckily, bypassing it is easy:
1. Open up the game-specific settings for SUPERHOT
2. At the "Select an alternative EXE to run" option, type in "SH.exe"
