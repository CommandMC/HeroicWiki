Some Electronic Arts games require the EA App ([link](https://www.ea.com/ea-app)). Those games show up in the Library as `Not Supported`:

![image](https://user-images.githubusercontent.com/188464/212543333-533ed0b7-3b69-4a3e-846f-97705da81239.png)

This page explains the steps to install the EA App on Linux and how to link your Epic account with your EA account so the games show up in the EA App collection.

## Requirements

You have to download the EA App installer for Windows from https://www.ea.com/ea-app

## Install EA App

- Click `Add Game`
- Set `EA App` as the title
- Note: If you have to link your Epic and EA accounts, select Wine or Wine-Staging in the `Wine version` selector, DO NOT use Wine-GE/Proton-GE or it won't work, you can use Wine-GE/Proton here if you don't need the linking
- Click `RUN INSTALLER FIRST`
- Select the `EAAppInstaller.exe` file downloaded from EA's site
- After the installation, the EA App will start but will be broken (missing content) because of missing dependencies, kill the process
- Click the folder icon in the `Select Executable` field and look for this file `.../Prefixes/EA App/drive_c/Program Files/Electronic Arts/EA Desktop/EA Desktop/EADesktop.exe`
- Click Finish, now the EA App should appear in your library

We have to install some dependencies to fix the app before using it:

- Go to the app's settings and click `WINETRICKS`
- Click `Ok` with the Select the default prefix option checked
- Select `Install a font` and click `Ok`
- Select `arial` and click `Ok`
- (If you are using Wine-GE/Proton-GE you can skip the next steps, this seems to be needed only for Wine/Wine-Staging)
- After the font is installed, click `Cancel`
- Select `Install a Windows DLL or Component` and click `Ok`
- Select `d3dcompiler_47` and click `Ok`

After it's done installing, click `Cancel` until Winetricks closes

## Login into the EA App

Now you should be able to run the app with the `Play` button, do that and Login.

## Link the Epic account with the EA account

If your games from Epic DO NOT show up in the EA App's collection, you need to link the accounts.

> For this to work you need the EA App to be installed using Wine or Wine-Staging. With Wine-GE it does not set the `link2ea` protocol and trying to link accounts fail with this error `wine: failed to open "link2ea://launchgame/<appName>?AUTH_PASSWORD=....`

You need some pieces of information:

- The `legendary path`: check Heroic's logs, you should see a line like `(09:34:37) INFO:    [Legendary]:        Legendary location: /home/some/path/legendary` at the top, we'll need the path
- The `app name` for any of your EA games: run the command `/home/some/path/legendary list -T` and look for any EA game, you'll see something like ` * Star Wars Squadrons (App name: bobcat | Version: None)`, the name `bobcat` is what we'll use in this case
- The `wine prefix`: click the EA App card in the library and it will show the `WinePrefix folder` there, would be something like `/some/path/Prefixes/EA App`
- The `wine path`: you should be using Wine or Wine-Staging, so this should be `/usr/bin/wine`, if you are not or you have wine in another path, check the EA App's log in heroic and it should show the path in the first line after `Wine Command:`

Now, with all this information we have to run this command, replace `<...>` with the corresponding information listed above:

```
<legendary path> launch <app name> --origin --wine "<wine path>" --wine-prefix "<wine prefix>"
```

> With the information from the examples, this command would be `/home/some/path/legendary launch bobcat --origin --wine "/usr/bin/wine" --wine-prefix "/some/path/Prefixes/EA App"`

After running that command, the EA App should open and it should ask you to link your Epic and EA accounts and your games should show up in there for you to install them.

## Notes:

- Make sure you logged in into the EA App before trying to link the accounts
- Once the accounts are linked, you can use any Wine version to install the EA App if you need a specific Wine to run any of the games