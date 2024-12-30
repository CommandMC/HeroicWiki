This page covers different problems related to launching Rockstar Games owned in Epic.

## Rockstar Launcher opens with the option to buy the game

Since the latest update of the Rockstar launcher, these steps are needed to run games like GTAV or RDR2:

- Download the custom `EpicGamesLauncher.exe` file from https://github.com/Etaash-mathamsetty/heroic-epic-integration/releases (this is NOT the real Epic Games Launcher, it's just a wrapper exe with the same file name)
- Put the `EpicGamesLauncher.exe` file in the install directory of the game (next to the `PlayGTAV.exe` or `PlayRDR2.exe` files)
- Create a text file called `fix.bat` in the install directory (next to the `PlayGTAV.exe`) with this content `start "" EpicGamesLauncher.exe PlayGTAV.exe %*` (replace with `PlayRDR2.exe` as needed) (1)
- In the game's settings in Heroic, in the `Advanced` tab, select the created `fix.bat` file in the `Select an alternative EXE to run` field

Then run the game.

The Rockstar Launcher should open, and, while loading, it should launch the game without getting to the main screen of the Rockstar Launcher.

(1) Make sure the file is a plain text file and not a rich text file

## Rockstar Games on MacOS

To run GTAV on Mac, the free `wine-crossover` wine that can be installed with Heroic doesn't work. There are 2 options:

- Using the paid version of Crossover
- Using Whisky, check the guide on their site https://docs.getwhisky.app/game-support/grand-theft-auto-5.html

> I haven't seen any confirmation of running Red Dead Redemption 2 on Mac, feel free to update this if that information is known

## GTAV Online

This will ONLY work on Windows. Rockstar added Battleye anticheat without enabling the Linux support https://www.gamingonlinux.com/2024/09/grand-theft-auto-v-gets-battleye-anti-cheat-breaks-online-play-on-steam-deck-linux/. This means online **does NOT work** on Linux nor MacOS and **there's nothing that can be done to fix that**.

## "com.epicgames.launcher" protocol issue (only on Windows)

> [!NOTE]  
> These steps are only required on Windows. Heroic will automatically apply them on macOS and Linux

When launching a Rockstar title from the Epic Games store, you will encounter the following message:

![image](https://github.com/user-attachments/assets/801c1508-2ab3-4ace-8695-676ff59555ba)

To resolve this, do one of the following:

## Option 1: Use .reg file

Download this .reg file: https://legendary.gl/assets/fnv_fix.reg  
Double-click it to merge it into your current registry (feel free to delete the file afterwards)

## Option 2: Add the key yourself

Open up an administrative PowerShell by right-clicking the Windows logo in your taskbar and choosing "Windows PowerShell (Admin)". This will prompt you for administrative access, choose "Yes" there.
In the command prompt that opens, type in `reg add HKCR\com.epicgames.launcher /f` and press enter. Once you've done that, the command prompt should look like this:

![image](https://github.com/user-attachments/assets/aca59f88-419d-46ce-b15b-0f40ee52adcf)