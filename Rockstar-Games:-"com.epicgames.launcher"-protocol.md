> [!NOTE]  
> These steps are only required on Windows. Heroic will automatically apply them on macOS and Linux

When launching a Rockstar title from the Epic Games store, you will encounter the following message:

![image](https://github.com/user-attachments/assets/801c1508-2ab3-4ace-8695-676ff59555ba)

To resolve this, do one of the following:

## Option 1: Use .reg file

Download this .reg file: https://legendary.gl/assets/fnv_fix.reg  
Double-click it to merge it into your current registry (feel free to delete the file afterwards)

## Option 2: Add the key yourself

Open up an administrative PowerShell by right-clicking the Windows logo in your taskbar and choosing "Windows PowerShell (Admin)". This will prompt you for administrative access, choose "Yes" there.
In the command prompt that opens, type in `reg add HKCR\com.epicgames.launcher /f` and press enter. Once you've done that, the command prompt should look like this:

![image](https://github.com/user-attachments/assets/aca59f88-419d-46ce-b15b-0f40ee52adcf)