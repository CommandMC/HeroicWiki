# Steam Deck

## Table of Contents


- [Usage](#usage)
- [How to Install Heroic Games Launcher](#how-to-install-heroic-games-launcher)
   - [Flatpak **(Recommended)**](#flatpak-recommended)
       - [Flatpak Permissions](#flatpak-permissions)
   - [AppImage](#appimage)
       - [Game Mode](#game-mode)
   - [How to Add Heroic Games to Steam/Game Mode](#how-to-add-heroic-games-to-steam-game-mode)
       - [Manual](#manual)
       - [Automatic](#automatic)
   - [HDR](#hdr)
       - [Flatpak](#flatpak)
       - [AppImage](#AppImage)
   - [Common Issues](#common-issues)
       - [Mangohud does not work](#mangohud-does-not-work)
       - [Gamescope not available](#gamescope-not-available)

## Usage

It is intended to install and configure games from desktop mode only. Running Heroic itself through Game Mode is not supported and you may encounter issues doing so. 

The proper way to use Heroic with the Steam Deck is to open Heroic in desktop mode, install and update games from there. You may need to play games at least once in desk top mode to confirm that they are functioning properly and in the case where a game requires user interaction on first launch, such as associating your Epic account with the game via a web browser pop up.

Once a game is installed, you can add it to steam through the 3 dot menu on the game page, or by selecting "auto add to steam" from the heroic settings on the side bar.

## How to Install Heroic Games Launcher

### Flatpak (Recommended)

To install Heroic Games Launcher using the Flatpak, follow the below steps. The Flatpak is the recommended packaging method to use Heroic Games Launcher on the Steam Deck. 

1. Switch to **Desktop mode**.
2. Open the app store (Discover).
3. Search for "Heroic".
4. There should be a result for Heroic Games Launcher. Click install.
5. You should now be able to launch Heroic like any other application on your Steam Deck!

#### Flatpak Permissions

Purpose: Give permissions to SD Card, other partitions, external drives, etc.

Flatpak's containerization while intended for increased security does limit Heroic's permissions to several system's features and folders. It is necessary to give extra permissions to Heroic. 

**If you are using KDE (includes the Steam Deck):**

1. Open the `System Settings`
2. On the left-hand side, click `Applications` under the `Personalization` section
3. On the left-hand side, click `Flatpak Permission Settings`
4. In the list of applications, locate Heroic Games Launcher and click it to open the permissions menu.
5. On the right-hand side under the `Permissions` menu, locate the `Filesystem Access` section.
6. Click `Add New` and add your preferred path.
7. When finished, set it to `read/write` and click `OK`
8. Restart Heroic Games Launcher.

**If you are not using KDE:**

In this case we will need to install Flatseal from the Discover or another Linux Store that you use.

1. Search for and install Flatseal on your Store, Discover on Steam Deck.
    * ![image](https://user-images.githubusercontent.com/26871415/167460932-af7100b7-7a26-4e4e-8ca9-db1bb9d9d4fb.png)
2. Open Flatseal and Search for Heroic Games Launcher:
    * ![image](https://user-images.githubusercontent.com/26871415/167461051-3b2f5cf7-c38e-4a63-bbdb-ce6c0302175f.png)
3. Looks for the Filesystem section and add the folders you need to access like shown on the image above.
4. Restart Heroic.

### AppImage

To install Heroic Games Launcher using the AppImage, follow the below steps. 

1. Switch to Desktop Mode.
2. Open the Heroic "Releases" page, [https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/releases](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/releases)
3. Download the `Heroic-*.*.*.AppImage` file
   * Depending on when you are reading this page, the version # may differ
   * If you do not see the AppImage, click `Show all ## assets`
4. Move the newly downloaded AppImage to the `/home/deck/Applications` folder
   * If you do not have an `Applications` folder, it is recommended you create one but you may place the AppImage wherever you would like
5. Right click the AppImage, click `Properties`, `Permissions`, check `Is Exectuable`
6. Double click the AppImage to open Heroic

#### Game Mode

Though it is not recommended to use Heroic in Game Mode, you may add the AppImage to Game Mode by following the below steps. If you are using Heroic in Game Mode, it is highly recommended you only do so to launch your games. Installing, updating, and managing your games should be done in Desktop Mode. 

1. Open the Heroic shortcut by clicking it once.
2. Click the `Gear` icon on the right-hand side of the screen.
3. Click `Properties`
4. On the left-hand side of the screen, click `Shortcut`
5. Scroll down to `Launch Options`
6. Type `--no-sandbox`
7. Heroic will now launch in Game Mode.

## How to Add Heroic Games to Steam/Game Mode

Non-Steam games added to Steam will automatically appear in Game Mode under the "Non-Steam" tab. In order to add non-Steam games to Steam, follow the below steps.

### Manual

These steps will cover how to manually add a Heroic game to Steam after it is installed. 

1. In Desktop Mode, open Heroic.
2. Either install a game or select an already installed game in Heroic.
3. Click the three vertical dots in the top-right section of the screen.
4. Click `Add to Steam`
5. The game will now be added to Steam and appear under the "Non-Steam" tab in Game Mode.

### Automatic

These steps will cover how to automatically add a Heroic game to Steam after it is installed. 

1. In Desktop Mode, open Heroic.
2. On the left-hand side of the screen, click `Settings`
3. On the left-hand side of the screen, click `Add games to Steam automatically`
4. Any newly installed Heroic games will automatically get added to Steam and appear under the "Non-Steam" tab in Game Mode.


## HDR

### Flatpak

To enable HDR with the Flatpak version of Heroic, follow the below steps.

1. Switch to Desktop Mode.
2. In a folder of your choice, right click anywhere, click `Open Terminal Here`
3. Type the following command and press enter: 
    * `flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo --user`
4. Type the following command and press enter: 
    * `flatpak remove org.freedesktop.Platform.VulkanLayer.gamescope -y`
5. Type the following command and press enter: 
    * `git clone https://github.com/flathub/org.freedesktop.Platform.VulkanLayer.gamescope.git`
6. Type the following command and press enter: 
    * `cd org.freedesktop.Platform.VulkanLayer.gamescope` 
7. Type the following command and press enter: 
    * `git checkout 2a8ab98c2881d5a1262712093d051434a1a7d6f4` 
8. Type the following command and press enter: 
    * `sed -i 's|https://freedesktop.org/software/libevdev/libevdev-1.13.1.tar.xz|https://distributions.freedesktop.org/software/libevdev/libevdev-1.13.1.tar.xz|' "modules/libevdev.yml"`
9. Type the following command and press enter: 
    * `sed -i 's|https://freedesktop.org/software/libevdev/libevdev-$version.tar.xz|https://distributions.freedesktop.org/software/libevdev/libevdev-$version.tar.xz|' "modules/libevdev.yml"`
10. Type the following command and press enter: 
    * `flatpak install org.flatpak.Builder --user -y` 
11. Type the following command and press enter: 
    * `flatpak run org.flatpak.Builder --user --jobs=4 --install ./_build ./org.freedesktop.Platform.VulkanLayer.gamescope.yml --user -y` 
12. Type the following command and press enter: 
    * `flatpak mask --user org.freedesktop.Platform.VulkanLayer.gamescope` 
13. The Flatpak Gamescope will now be installed and HDR will now work in Game Mode

### AppImage

HDR will work out of the box with the AppImage.

## Common Issues

### Mangohud does not work

Check if you have installed the Flatpak version of Mangodhud: `flatpak install org.freedesktop.Platform.VulkanLayer.MangoHud`

### Gamescope not available

Check if you have installed the Flatpak version of Gamescope: `flatpak install org.freedesktop.Platform.VulkanLayer.gamescope`

If you are on a Steam Deck, the Flatpak version of Gamescope must match the natively installed version. If these versions do not match, you may experience increased crashing in other Flatpaks. 