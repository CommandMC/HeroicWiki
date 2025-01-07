This page explains different ways to solve the `"The following components are required to run this program: Microsoft Visual C++ Runtime"` error message.

The solution is to install the C++ Runtime, and there are multiple ways of doing it depending on the platform and tools used.

## Linux

### Using Winetricks

This is the simplest option for most users. Winetricks is automatically downloaded and the steps to install the Visual C++ Runtime are:

- Open the game's settings in Heroic
- Make sure you are in the Wine tab
- Scroll down and click the `winetricks` button, a new dialog should show up
- In the text field, type `vcrun2022`. After a moment a list should show up with an `Install` button
- Click the `Install` button and wait until it's done

> Note that, in general, installing the latest `vcrun` covers most use cases since it includes older ones. If, for any reason, you need to install an older version, just type `vcrun` instead and install the one you want.

### Manual installation

Sometimes, the installation using winetricks fails. In those cases, the Visual C++ Runtime can be installed manually:

- Open https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170 in the browser
- Download both the `x86` and `x64` installers listed under `Latest Microsoft Visual C++ Redistributable Version`
- Open the game's settings in Heroic
- Make sure you are in the Wine tab
- Scroll down and click the `Run EXE in Prefix` button, a file picker should show up
- Select one of the installer and complete the process
- Repeat for the other installer

## Mac

### With Crossover (the paid version, not the free Wine-Crossover)

When using Crossover, winetricks cannot be used. In this case you'll have to use Crossover's UI:

- Open Crossover
- Select the corresponding Bottle on the left sidebar
- Click the `Install application into bottle` button in the right sidebar
- Search for C++ Runtime and install the package

### With Whisky

> I haven't used whisky so I don't know if it supports winetricks or if it needs a different process. Feel free to edit this page to add this information.

### With wine-crossover / wine-staging / wineskin / gptk (or other wine)

For these tools, the same options that are available for Linux can be used: with winetricks or with the `Run EXE in Prefix` option

## Windows

In general, Heroic prompts to install the latest C++ Runtime at boot if it detects it's not installed, but, if needed, the files can be downloaded and installed manually:

- Open https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170 in the browser
- Download both the `x86` and `x64` installers listed under `Latest Microsoft Visual C++ Redistributable Version`
- Install both