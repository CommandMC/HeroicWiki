## List with several Legendary and Wine Workarounds:
[EpicLinux Wiki](https://github.com/CommandMC/EpicLinux/wiki)

## Save Game paths
For Cloud Sync to work as expected, where a game saves and syncs is very important to get right. Ensure that Heroic's save location is actually where the game saves are! ou can check for the correct folder on the website called PCGamingWiki. (Windows games, for example, are likely saving directly inside the WINEPREFIX root, for obvious reasons)

## Heroic-specific

### SUPERHOT
The SUPERHOT launcher does not work with Heroic, since it also uses some Electron components. Luckily, bypassing it is easy:
1. Open up the game-specific settings for SUPERHOT
2. At the "Select an alternative EXE to run" option, type in "SH.exe"


### Redout: Enhanced Edition
This game runs good by using Wine Staging, it just needs a few extra steps:
1. Install VcRedist 2015-2018 (using winetricks or downloading from Microsoft Website) on the Wine Prefix.
2. Go to the game settings, activate DXVK and VKD3D
3. If the game complains about DX12 not being supported, go to the game `Settings` > `Other` and add `-dx11` to the Game Arguments.
4. The game should open just fine now.

### HITMAN 3
The game requires to be run on any "FShack" build of Wine or Proton, otherwise it will crash. Once installed, the game will try and download a faulty update, and thus, needs updates disabled.
1. Open up the game-specific settings for HITMAN 3
2. Under "Other", go to "Game Arguments", and add `DXVK_CUSTOM_VENDOR_ID=10de %command% --skip-version-check` to the text field.

