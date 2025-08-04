## OS Version

We always recommend using the latest version of the OS, the tools Heroic uses require usually either the latest of the previous version of the OS to even run.

## Compatibilty Layers

Heroic supports different compatibility layer for MacOS. These tools are used to run Windows builds of games.

Mac gaming is not as mature as linux or windows, so you might need to try different compatibility layers for some games or do some tweaking (one game may not work with GPTK but work with Wine-Crossover, or be usable with Wine-Staging but have better performance with Crossover, you'll have to play around with the options.

### Wine-Crossover

Heroic allows installing `Wine-Crossover` builds from https://github.com/Gcenx/winecx/releases/tag/crossover-wine-23.7.1-1. Many games will work just fine with this Wine flavor and it's compatible both with Intel and Apple Silicon chips.

It has limitations and known issues:
- it is based on Crossover 23, while newest Crossover is at version 25 at the moment of writing this, so it's outdated
- it does not support DX12 games
- many games show invisible content due to a known issues for DXVK for Mac
- check the release notes on that repo for more details

Note this is NOT the commercial version of Crossover from CodeWeavers (listed below)

### Wine-Staging (Wine-Devel)

Heroic allows installing Wine-Staging/Wine-Devel builds from https://github.com/Gcenx/macOS_Wine_builds/releases/tag/10.12. This is based on Wine itself instead of Crossover and it's more up-to-date and may fix issues in some games. this is compatible with both Intel and Apple Silicon chips.

### Game Porting Toolkit (GPTK)

Heroic allows installing Game Porting Toolkit builds from https://github.com/Gcenx/game-porting-toolkit/releases. This is based on [Apple's Game Porting Toolkit](https://developer.apple.com/games/game-porting-toolkit). It's meant to be used for modern games that require DX11 or DX12 and only runs in Apple Silicon chips.

### Whisky

Heroic supports using Whisky as a compatibility layer, but it's not maintained anymore and not recommended! You can still use it if you know what you are doing, but don't ask for support using it, try the other options instead (GPTK will most likely work better and is up-to-date).

### Crossover

Heroic supports using the commercial Crossover (either paid or the 14-days free trial) from https://www.codeweavers.com/crossover. Check [Crossover's guide on how to integrate it with Heroic](https://support.codeweavers.com/common-actions/heroic-games-launcher-in-crossover).

This is the most powerful version of the pack, it gets more frequent updates, it supports both Intel and Apple Silicon chips, it supports multiple graphics layers to pick from and also supports running more software. But this is a paid option, you can try it for a few days for free but you'll need to buy a license to use it eventually. 

### Others

There are more tools like Kegworks that are not yet compatible with Heroic (at the moment of writing this page)

## Will <my game> work?

As mentioned before, you have to try the different layers and hope for the best, there's a not-small chance for games to just not work on MacOS (games with Anti-Cheat software will almost always not work on MacOS).

Here are some resources you can check too (keep in mind everything is crowd-sources, so things can be outdated or incorrect):
- [Crossover compatibility](https://www.codeweavers.com/compatibility) (to use the commercial Crossover)
- [AppleGamingWiki](https://www.applegamingwiki.com/wiki/Home)
- [My personal tests for an M4 mac](https://docs.google.com/spreadsheets/d/1qvM4HpYLrDCi69nejKF3NIbqxr3RJZV3qQM9mL0u2Y0/edit?gid=1924600756#gid=1924600756)
- [My personal tests for an Intel mac](https://docs.google.com/spreadsheets/d/1qvM4HpYLrDCi69nejKF3NIbqxr3RJZV3qQM9mL0u2Y0/edit?gid=1942809985#gid=1942809985)
- There might be more, reach out through discord if you want to add more information here

## Apple Silicon (M chips)

### Rosetta

Apple Silicon chips require a translation layer to understand software made for x86/64 architecture. Apple provides `Rosetta` for this and you'll need this in order to play Windows games through wine/crossover.

To install or update it, open a terminal and run this command:

```sh
softwareupdate --install-rosetta
```

## Intel chips

Mac computers with Intel chips do not need a translation layer, but they cannot use the modern Game Porting Toolkit. In this case, your options are Wine-Crossover, Wine-Staging/Wine-Devel, or Crossover.

## Winetricks setup

`winetricks` is a tool used to install libraries and apply changes to wine prefixes. Heroic can apply some known fixes for specific games based on the information we collect at https://github.com/Heroic-Games-Launcher/known-fixes.

For these fixes to work, `winetricks` must be setup correctly. When running the Winetricks option in a game's settings dialog, it's common to see these 3 warnings:

```
7z not installed! Winetricks might fail to install some packages or even open
cabextract not installed! Winetricks might fail to install some packages or even open
zenity not installed! Winetricks might fail to install some packages or even open
```

- `cabextract` is needed to install important known-fixes packages like `d3dcompiler`, the easiest way to get it installed is through Homebrew, we recommend [installing Homebrew](https://brew.sh) and then [installing the cabextract package](https://formulae.brew.sh/formula/cabextract#default).
- `zenity` is needed to run the GUI interface of winetricks, you can ignore it for the known-fixes to work but you might want it if you want to manually play around with things heroic does not provide easy access to, you can install it with Homebrew running `brew install zenity`
- TODO: `7z` can also be installed with Homebrew, but the message never goes aways, it's something to investigate more and update this page as needed