# Gamescope
There is a plan to have a Gamescope setting in Heroic, while that is implemented, you can still use it with Heroic following the steps bellow:
1. Install [Gamescope](https://github.com/Plagman/gamescope) in your system.
2. In Heroic, open the game settings and go to the **Other** tab.
3. On the Advanced Options (Environemnt Variables), put the Gamescope command line you want to use followed by two dashes in the end, for instance: `gamescope -w 1920 -h 1080 -W 3440 -H 1440 -b --`.
4. If you have other variables, make sure you add it add the end of the input like: `DXVK_HUD=full gamescope ... --`
5. For now, enabling `mangohud` or `gamemode` might make gamescope not work, so try with those options enabled first. 

