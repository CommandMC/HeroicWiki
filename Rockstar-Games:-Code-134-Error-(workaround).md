Since the Rockstar Launcher update that removed the support for older Windows versions, their games stopped working with Heroic showing an error with `code 134`:

![image](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/assets/188464/d7399324-92ec-4641-b458-87a171c5768c)

This page describes a workaround to get Rockstar games working again (this is not a final solution but a workaround).

> This was tested by users with GTAV and RDR2, and in all systems: Windows, Linux, and MacOS.

## Steps

1. After installing the game, run it once so it installs the Rockstart launcher, log in, and then close it
2. Open the game install folder and create a text file named `fix.bat`, this new file should be in the same folder where the `PlayGTAV.exe`/`PlayRDR2.exe` file is located:

![image](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/assets/188464/86675ca1-47bf-42b7-8353-c170758d169b)

3. Add this content to the text file:
```
start /B "null" "C:\Program Files\Rockstar Games\Launcher\LauncherPatcher.exe"

ping -n 20 localhost > nul

./PlayGTAV.exe %*
```

  - Don't type the content, copy and paste it
  - Replace the `PlayGTAV.exe` with `PlayRDR2.exe` if you are trying to launch Red Dead Redemption 2
  - This will tell Heroic to: launch the Rockstar Launcher, then wait for 20 seconds, and then launch the game

4. Open the game settings in Heroic and set this `fix.bat` file as an alternative exe for the game in the Advanced tab:
![image](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/assets/188464/9c604a44-5f8b-479f-b47b-86d61b8f6751)
5. Launch the game

## Troubleshoot

- If this is working right, the Rockstar launcher **MUST** show up first and after 20 seconds the game should start automatically, if this doesn't happen (for example, nothing happens for 20 seconds and then you get an error) then something is wrong with your `fix.bat` file, so double check it.
- This workaround is **ONLY** for the `134` error, any other problem is not going to be fixed by this.
- Some users reported they need to change the `C:\Program Files\Rockstar Games\Launcher\LauncherPatcher.exe` line in the fix.bat file to use the `Program Files (x86)` folder instead of the `Program Files` one. Double check what is the right folder by searching the `LauncherPatcher.exe` file inside your drive/wine prefix/bottle.
- The `20` in the script is the time it wait to launch the game after the Rockstar launcher started, slower systems may take longer to start the launcher and be ready so you might need to try different numbers there (you could also try less than 20 if you see it's ready before that)
- If you change your wine (from wine to proton, for example), or you reset the prefix for any reason, you must **remove** the `fix.bat` configuration the first time so the Rockstar Launcher is reinstalled.