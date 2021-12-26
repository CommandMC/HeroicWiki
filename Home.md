Welcome to the Heroic Games Launcher wiki!

### What is Heroic?
Heroic is a native GUI alternative to the Epic Games Launcher for Linux, Windows and MacOS.  
It is open source under GPLv3 and is maintained by a community of developers that work **for free on their free time**.

For now, Heroic is mostly a GUI for Legendary (which is a CLI tool that deals with the login and downloading & launching of games).  
Support for other storefronts & adding your own games (think Steam's "Add Non-Steam Game" feature) is planned in the future.

### Why do you need Heroic?

<!-- For now this only compares Heroic and the EGL. Once other stores are supported, they should be added here -->

Heroic is a community-built, open-source launcher. This means that you can see for yourself what it does in the background and anyone can suggest changes or find optimizations.  
Because of that, Heroic is way faster than the EGL and uses far less resources.  
|                      | Heroic  | EGL      |
| -------------------- | ------- | -------- |
| Installer size       | 92MB    | 153MB    |
| First-launch updates | /       | 529MB    |
| Requires admin?      | No      | Yes      |
| Disk space used      | 338MB   | 951MB    |
| RAM Usage (library)  | <200MB  | 400MB    |
| RAM Usage (store)    | 210MB*  | 450MB*   |
| CPU usage while idle | 0-10%** | 50-70%** |
| Linux support?       | Yes     | No       |

In addition to using more resources, the EGL also performed far worse usability-wise. For example, switching from the Store to the Library took 5-8 seconds. This might've been influenced by the VMs limited GPU power.  
\* Initially, RAM usage was higher for both Heroic and the EGL. After around 10 seconds, the values shown were observed.  
\** Tested on a Windows 10 VM with 6 CPU cores

### Which games are not supported by Heroic?
Currently, only games that require activation in another storefront (Uplay, Origin) are unsupported.  
Legendary recently added support for these with the `activate` command, expect support for this in a future release.
