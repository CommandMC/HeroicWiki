# SteamDeck And Linux Flatpak guide

## Install on SteamDeck with flatpak (recommended):
1) Go to **Desktop mode**.
2) Open the app store (Discover).
3) Search for "Heroic".
4) There should be a result for Heroic Games Launcher. Click install.
5) You should now be able to launch Heroic like any other application on your Steam Deck!

If you wish to, you can also make use of a tool called **Heroic Bash Launcher** to launch games directly by [following this guide](https://github.com/redromnon/HeroicBashLauncher/wiki/Steam-Deck-(Flatpak)-Guide).

## Give permissions to SD Card, other partitions, external drives, etc.

Due to Flatpak's nature that uses containarization to bring more security to the system while limiting permissions to several system's features and folders. It is necessary to use a third-party tool to give extra permissions to Heroic. In this case we will need to install Flatseal from the Discover or another Linux Store that you use.

1. Search for and install Flatseal on your Store, Discover on SteamDeck.
![image](https://user-images.githubusercontent.com/26871415/167460932-af7100b7-7a26-4e4e-8ca9-db1bb9d9d4fb.png)
2. Open Flatseal and Search for Heroic Games Launcher:
![image](https://user-images.githubusercontent.com/26871415/167461051-3b2f5cf7-c38e-4a63-bbdb-ce6c0302175f.png)
3. Looks for the Filesystem section and add the folders you need to access it like on the image above.
4. Restart Heroic.

## Mangohud doesn't work
Check if you have installed the flatpak version of Mangodhud: `flatpak install org.freedesktop.Platform.VulkanLayer.MangoHud`