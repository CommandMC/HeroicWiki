# How to Debug Games Using Environment Variables

This page is a continuation of the environment variables page, [https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/wiki/Environment-Variables](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/wiki/Environment-Variables) with a specific focus on how to debug games using environment variables. 

When using `WINEDEBUG=+fixme` or any debug variables, follow the below steps to locate the verbose log:

1. Launch the game so it produces a new verbose log. After you have launched the game (even if it crashes), close out of it and open the Heroic Games Launcher. 
2. Open the game's page, click `Report a problem running this game`.
   * <img src="https://github.com/user-attachments/assets/83def3f6-1ad4-4685-ac5d-5a20c12fe7e8" height="300">
3. Either click `SHOW LOG FILE IN FOLDER` or `UPLOAD LOG FILE`, the first will open the directory of the log, the latter will upload the log to a website that you can then share with someone if you are receiving support.
4. Once you have investigated the log, you can remove the environment variable by returning to the `Advanced` tab in the game's settings and clicking the `-` button.
   * <img src="https://github.com/user-attachments/assets/4b656678-fc5d-4920-921e-cbeaeae721bc" height="300">

Alternatively, you can open the directory of the log directly, the file paths are listed below:

* Flatpak:
  * `$HOME/.var/app/com.heroicgameslauncher.hgl/config/heroic/GamesConfig`
  * Locate the `-lastPlay` log with the newest timestamp.
* Non-Flatpak (AppImage, DEB, RPM, etc.):
  * `$HOME/.config/heroic/GamesConfig`
  * Locate the `-lastPlay` log with the newest timestamp.

If you have not debugged a log before, typically locating error messages or repeating messages and copying these messages into a search engine of your choice is a good way to begin. If you are still struggling to debug your log, join the [Heroic Games Launcher Discord](https://discord.com/invite/rHJ2uqdquK) and create a support post with your log attached.