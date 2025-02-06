# Environment Variables

## Table of Contents

- [Introduction](#introduction)
- [umu](#umu)
- [External Documentation](#external-documentation)
- [%command%](#command)
- [Commonly Used Environment Variables](#commonly-used-environment-variables)
- [How to Set Environment Variables](#how-to-set-environment-variables)
   - [How to Debug Using Environment Variables](#how-to-debug-using-environment-variables)

## Introduction

In short, environment variables are a way to pass settings to a game on launch. Environment variables can tell the Proton runner to output a verbose log which can then allow the user to debug the game. Environment variables can also tell Proton to use different DLLs, either those bundled with Proton or those bundled with the game in the game's installed directory. 

Do note many guides online will include tutorials on how to set environment variables in Steam. If you are using the Heroic Games Launcher, **do** not set environment variables in Steam. Instead set these variables directly in the Heroic Games Launcher. This page will cover how to do so. In addition, many guides will include `%command%`, this bit is **specifically for Steam**. It does **not** apply to Heroic. Do **not** add `%command% to environment variables you set in the Heroic Games Launcher. 

Another important thing to keep in mind is that many guides can be frivolous with setting environment variables. These can be seen as a "magic bullet" to fix a game but in some cases, these environment variables can be unnecessary which can either not fix the game at all or mask the actual issue at hand. 

Typically the most common use-case for an environment variable is debugging. In these cases, you will set an environment variable that prints out a verbose log which can allow you to further investigate the issue at hand. After you have resolved the issue, you can disable the environment variable. 

## umu

[umu](https://github.com/Open-Wine-Components/umu-launcher) is a tool that allows the Steam runtime to work outside of Steam. It's best utilized in conjunction with Proton-GE or umu-Proton. However, umu can also be used with vanilla Proton. 

If an environment variable successfully fixes a game, it can be upstreamed to the [umu database](https://github.com/Open-Wine-Components/umu-database) and the [umu protonfixes](https://github.com/Open-Wine-Components/umu-protonfixes) repository. Once these fixes are upstreamed, the fixes are automatically applied to your game. In these cases, the environment variable will be handled by umu entirely and **do not** need to be handled by the user. 

You can view the [umu database](https://github.com/Open-Wine-Components/umu-database) to see the list of fixes currently being applied when using umu. 

The umu database and proton-fixes repository are user-driven. If you have discovered a fix, create both a database entry and proton-fixes entry for your game. Once these are approved and merged, these fixes are applied to the game automatically **for any** user who installs the game. 

## External Documentation

* [DXVK Debug Variables](https://github.com/doitsujin/dxvk/blob/master/README.md#debugging)
* [Wine Debug Variables](https://gitlab.winehq.org/wine/wine/-/wikis/Debug-Channels#examples)
* [Wine DLL Overrides](https://gitlab.winehq.org/wine/wine/-/wikis/Wine-User's-Guide#dll-overrides)
* [Wine Environment Variables](https://gitlab.winehq.org/wine/wine/-/wikis/Wine-User's-Guide#environment-variables)
* [Proton Environment Variables](https://github.com/ValveSoftware/Proton#runtime-config-options)
* [VKD3D Environment Variables](https://github.com/HansKristian-Work/vkd3d-proton#environment-variables)

## %command% 

As noted in the introduction, `%command%` is **specifically for Steam**. **Do not** use `%command%` when setting environment variables in the Heroic Games Launcher. 


## Commonly Used Environment Variables

* `WINEDEBUG=+fixme`
   * Outputs verbose logging information.
* `WINEDLLOVERRIDE="DLLNAME=n,b"`
   * The `n` and `b` stand for `native` and `built-in`. This environment variable tells Proton to first check for any DLLs in the game's directory. If this fails or if it cannot find a DLL, it falls back to the DLL bundled with Proton.
   * For more information, see [Wine Environment Variables](https://gitlab.winehq.org/wine/wine/-/wikis/Wine-User's-Guide#environment-variables)

## How to Set Environment Variables

1. Open the Heroic Games Launcher.
2. Select a game and open the game's page.
3. In the top right, click the `Settings` button.
   * <img src="https://github.com/user-attachments/assets/4b03ffe5-3c30-490b-bf53-38edad2c2e85" height="300">
4. Click the `Advanced` tab and scroll down to the `Environment Variables` section.
   * <img src="https://github.com/user-attachments/assets/fb9d5948-10c3-4268-b245-63a009e7fd6b" height="300">
   * <img src="https://github.com/user-attachments/assets/bdf60c91-5739-46ba-b5ed-600488cdf3a5" height="300">
5. Set your environment variable(s), this example will use `WINEDEBUG=+fixme` as an example:
   * <img src="https://github.com/user-attachments/assets/4b635a92-4b45-429c-a661-1dd0d435a0fc" height="300">
6. Click the green `+` icon to save the environment variable(s).
   * <img src="https://github.com/user-attachments/assets/2311ef00-7db8-414f-8f6d-387fb5b6ae0a" height="300">
7. Your environment variable(s) will now be applied to this game in specific. 

### How to Debug Using Environment Variables

If you are using `WINEDEBUG=+fixme` or any debug variables, follow the below steps to locate the verbose log:

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

***
