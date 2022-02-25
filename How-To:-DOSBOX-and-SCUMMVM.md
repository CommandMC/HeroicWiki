This describes how to run dosbox and scummvm games using native builds of those tools.
Presented way is the only one currently until we add support for that in heroic.

# For games installed using Linux offline installers
Those are schemes for commands using both tools used when launching games using packaged binary. You can check what arguments are passed exactly in `start.sh` file.

- Dosbox `dosbox -conf "${conf_1}" -conf "${conf_2}" -no-console -c exit`
- Scummvm `scummvm -c "${conf}" --themepath=scummvm`


# Getting launch arguments - Windows builds
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
