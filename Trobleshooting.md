## General Debugging tips:

**First thing to know is that Heroic is just a GUI (Graphical Interface), unlike Lutris, it doesn't call wine/proton directly, it uses Legendary for it. So is good to have in mind that some issues that you might have with some game might not be related with Heroic or even with Legendary as well.**

### Config files

Those are stored under:
`~/.config/heroic` and `~/.config/legendary`
The General settings for Heroic is the file called config.json. Sometimes this file, for some unknown reason so far, can get format issues (with extra brackets for instance) or even corrupted. Fixing it or removing it can fix some issues.
The Game settings and Game Logs (Installation and PlayLogs) are on the GameConfig under the Heroic folder.

### Not Supported Games

Right now Heroic doesn't Support downloading and installing games that need selective download. As far as we know, only **Fortnite **and **Cyberpunk ** has that so far. 

If you still need to download those games you can:
* Open Heroic from the terminal
* Click Install Game
* Check the install command
* Copy the whole command line
* Open another terminal
* Paste the Install command
* Follow the instructions.

### How to read output from game launch

First, you can launch Heroic from the terminal and check if the Launch command is right with the correct wine, prefix, and settings that you have set up. 
Second, you can go to the GamePage, clicking on the GameCard and then click on the Settings Button and on the SubMenu, click on LatestLog.
That will open a log file with everything that happened when you tried to launch the game.
With that, you can start troubleshooting and use it to get help on our Discord Server or on any Linux Community.

### Heroic doesn't open or shows a Blank Window

Close the App or kill the process if necessary then:
* Try removing/renaming the Heroic folder: `~/.config/heroic`.
* Try removing/renaming the Legendary folder: `~/.config/legendary`.

![image](https://user-images.githubusercontent.com/77377160/112746130-a63b4500-8fca-11eb-8b72-461f5b80e8f6.png)

### Game Won't Launch

Several things can cause that and probably Heroic has little or nothing to do with it.
But, one thing you can check is the Compatibility with the game on ProtonDB, even though there you will find more things related with the game on Steam and might not apply to the Epic Games version.

Another thing is to check the latest log like was said above.

Some games like Borderlands 2 and Borderlands: The Pre-Sequel, need that you install some things on the prefix first. Normally the needed files stay under a folder called `redist` or something similar under the game folder and has all the necessary `exe `or `msi `files. To install then, open the Game Settings and go to the Wine Tab. Then you can use the feature called Install EXE on prefix to install those files.

Sometimes, after a long time without using Heroic, your credentials might expire, we are working on showing a message about that and ask to login again, but for now, nothing is shown and when trying to launch the game, nothing will happen. So you will need to manually click logout and restart Heroic. Login again and then launch the game. All your games will be there, don't worry about they being uninstalled.