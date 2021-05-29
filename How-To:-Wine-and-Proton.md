## How to use Wine and Proton on Heroic

Heroic can use both Wine and Proton in any version.
For wine, Heroic passes the selected version on the Game Settings along with the `WINEPREFIX` to Legendary.
For Proton, Heroic uses the `--wrapper` and `--no-wine` flags on Legendary, to use the Proton wrapper and have Proton-specific configs and libraries to increase compatibility and fix bugs. Also, instead of a `WINEPREFIX`, Heroic uses the `STEAM_COMPAT_DATA_PATH `for it, using the prefix specified on settings.

## Where does Heroic search for Wine and Proton versions?

Heroic searches for the default installed wine, normally in `/usr/bin/wine`, and uses it as the default to launch the games. For now, Heroic does not support Wine Flatpak.
For Steam Proton, we know that depending on the distro, the steam path can be different so there are a few default folders pre-defined and you can also extract the custom proton/wine on `.config/heroic/tools/wine` for wine or `.config/heroic/tools/proton` for proton. It is also possible to go to the global settings >  Wine and add a custom Wine installation. 
For that, you can select the wine binary that you want to use or the proton binary. On the custom wine list, they will show as `Proton Custom` or `Wine Custom`.

Those are the default folders that Heroic looks for Proton:
        <ul>
          <i>
            <li>`~/.config/heroic/tools/wine`</li>
            <li>`~/.config/heroic/tools/proton`</li>
            <li>`~/.steam/root/compatibilitytools.d`</li>
            <li>`~/.steam/steam/steamapps/common`</li>
            <li>`~/.local/share/lutris/runners/wine`</li>
            <li>`/usr/share/steam`</li>
          </i>
        </ul>

## How to open Wine Settings, Winetricks/ProtonTricks, or run exe inside the prefix

On the Game Settings, under the Wine tab, it is possible to run WineCFG, Winetricks, or run an EXE inside the prefix.
When clicking the respective buttons, Heroic will run those tools with the selected Wine version or, in the case of Proton, with the Wine binary that is located under `protonVersion/dist/wine`.
Since Heroic runs those tools, like Winetricks, inside the right prefix even when using Proton, there is NO NEED of having Protontricks installed, since Protontricks is to be used on Steam specificaly.