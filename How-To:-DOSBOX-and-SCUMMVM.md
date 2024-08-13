This describes how to run dosbox and scummvm games using native builds of those tools.
Presented way is the only one currently until we add support for that in heroic.

# Automatic native runners

> [!NOTE]
> Automatic native runners feature is used only on Linux, for Windows builds of games.  
> Only from GOG and Amazon

Starting Heroic 2.15.0 all DOSBox and ScummVM games will be ran using native builds of those tools.  


The locations Heroic will scan and the tools that will be used

|  | Flatpak | PATH |
|--------|--------|--------|
| DOSBox | `io.github.dosbox-staging` | `dosbox` |
| ScummVM | `org.scummvm.ScummVM` | `scummvm` |

## Heroic Flatpak

In case of Heroic flatpak you'll need to add permissions allowing Heroic to run commands outside of sandbox.
This will be used only to run and detect flatpak versions of DOSBox and ScummVM.

The permission in question is `org.freedesktop.Flatpak` talk.

![image](https://github.com/user-attachments/assets/8eaf0d36-ef45-43b4-a164-516d69b15d2f)



<details>
<summary><h1>Manually getting dosbox/scummvm command arguments</h1></summary>

This part describes how to obtain command line arguments used to launch games, for scripting purposes.

## For games installed using Linux offline installers
Those are schemes for commands using both tools used when launching games using packaged binary. You can check what arguments are passed exactly in `start.sh` file.

- Dosbox `dosbox -conf "${conf_1}" -conf "${conf_2}" -no-console -c exit`
- Scummvm `scummvm -c "${conf}" --themepath=scummvm`


## Getting launch arguments - Windows builds
For windows builds, if you are missing some files you should try running the game in heroic first. Heroic will run setup when creating the prefix.

1. Navigate into game files
2. Locate and open `goggame-<GAMEID>.info` file (<GAMEID> is a number like 1207658695)
3. Look for the playTask that contains `"isPrimary": "true"` - this is the default launch command
4. In most cases arguments are dependant on working directory so keep this in mind when making the command.

In example command will look like
`/path/to/scummvm -c "/path/to/beneath.ini" beneath`


# Sample goggame.info file
```json
{
    "buildId": "51156444997712340",
    "clientId": "49002505861146264",
    "gameId": "1207658695",
    "language": "English",
    "languages": [
        "en-US"
    ],
    "name": "Beneath a Steel Sky",
    "playTasks": [
        {
            "arguments": "-c \"..\\beneath.ini\" beneath",
            "category": "game",
            "isPrimary": true,
            "languages": [
                "*"
            ],
            "name": "Beneath a Steel Sky",
            "path": "ScummVM\\scummvm.exe",
            "type": "FileTask",
            "workingDir": "ScummVM"
        },
        {
            "category": "document",
            "languages": [
                "*"
            ],
            "name": "Manual",
            "path": "Manual.pdf",
            "type": "FileTask"
        },
        {
            "category": "document",
            "languages": [
                "*"
            ],
            "link": "http://www.gog.com/support/beneath_a_steel_sky",
            "name": "Support",
            "type": "URLTask"
        },
        {
            "category": "document",
            "languages": [
                "*"
            ],
            "name": "Walkthrough",
            "path": "Walkthrough.pdf",
            "type": "FileTask"
        }
    ],
    "rootGameId": "1207658695",
    "version": 1
}
```
</details>