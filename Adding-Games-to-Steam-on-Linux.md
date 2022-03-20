## How to add your Heroic library to Steam?
If you're facing problems in launching your Heroic games on Steam, you can take a look at [Heroic Bash Launcher](https://github.com/redromnon/HeroicBashLauncher).

## What is Heroic Bash Launcher?

Heroic Bash Launcher is a tool that helps launch your Heroic Games library from the terminal or any game manager/launcher. 

It automatically creates executable bash files for each installed game. Each bash file or launch file includes the entire launch command (including parameters) of a game. Yes, it's the same launch command you see when you run `heroic` from the terminal and launch a game. Moreover, the parameters auto-update whenever you change the settings of a particular game on Heroic.

## Adding your games to Steam

### Syncing
Once you've run the **HeroicBashLauncher** executable, the **_AddToSteam_** bash script will be generated that helps sync your Heroic library to Steam. It basically displays a list of installed games and lets you choose games to be added to Steam (one at a time, for now).

### Adding Manually
If you're facing issues or prefer to add games manually, open Steam and add a game's launch script (located in **GameFiles** directory) as a Non-Steam game by performing the following steps:

1. Go to **LIBRARY**
2. Click **ADD A GAME**
3. Select **Add a Non-Steam Game** from the options
4. Select **BROWSE** on the new window that appears
5. For File Type, make sure to choose **All Files**
6. Navigate to `~/HeroicBashLauncher/GameFiles` and choose the game's launch file
7. If you want to add more games, repeat steps 4-6
8. Finally, click on **ADD SELECTED PROGRAMS**  

You're all setup! 