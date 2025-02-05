# As of February 5th 2025, Fall Guys was updated migrating from EAC to EOS as the anticheat solution. In the process, they removed the support for Linux so the game is currently unplayable on Linux systems. Thus, the following guide is outdated and shouldn't be used


1. Download the latest version of Wine-GE from Heroic's Wine Manager:  
   ![Download steps for Wine-GE](https://user-images.githubusercontent.com/34034631/193324230-1520111c-39a5-456a-af94-79992445c806.png)

2. <details>
   <summary>Install Fall Guys</summary>
   
   ![Download button of Fall Guys highlighted in the library](https://user-images.githubusercontent.com/34034631/193329396-c51f0596-fc38-42e4-83f6-1ca2f37e4928.png)  
   Make sure to select the version of Wine-GE you just downloaded here:  
   ![Install modal](https://user-images.githubusercontent.com/34034631/193329538-99186c27-ffd4-4b20-b790-04b8ab647c48.png)
   </details>


## That should be all, but if, for any reason, you get a Missing Files error, do the next steps:

> Note these steps should be executed automatically by Heroic's [known-fixes](https://github.com/Heroic-Games-Launcher/known-fixes/blob/main/epic/0a2d9f6403244d12969e11da6713137b-epic.json) feature, you shouldn't need to do this manually 

3. Open the game settings.

4. Check the `EasyAntiCheat Runtime` toggle and click on `Run EXE in prefix`.
   ![image](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/assets/45927311/67727091-254d-4912-87d1-3d5dc3509fb5)

5. Select `EpicOnlineServicesInstaller.exe` inside the EpicOnlineServices folder in the location you installed the game to.
    ![image](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/assets/45927311/a96b4c50-b866-4361-a070-cab8b364e238)

Now the game should work with no missing files error! Make sure you have the Easy Anti Cheat runtime enabled.