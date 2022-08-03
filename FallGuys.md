# Heroic Beta Guide:

## Install latest wine-ge

Install the latest version of wine-ge from heroic wine-manager.
![FallGuys0](https://user-images.githubusercontent.com/61798668/182595187-a6487373-7526-48d2-94e9-9415cc95e08b.png)

## Install Fall Guys

Make sure to choose the downloaded wine-ge version.
![FallGuys1](https://user-images.githubusercontent.com/61798668/182595491-71206b81-a142-42cf-abd5-396900520d62.png)
![FallGuys2](https://user-images.githubusercontent.com/61798668/182595504-792f911a-1245-40ca-9db4-6d629565e4e7.png)

## Enable DXVK, VKD3D and EAC
![FallGuys4](https://user-images.githubusercontent.com/61798668/182595830-0e021a3c-a1d6-462d-aee6-8de21987f0c1.png)
![FallGuys5](https://user-images.githubusercontent.com/61798668/182595851-c35f7a9a-bae0-4795-809d-e575ca025b92.png)

## Adapt Fall Guys
### Adapt FallGuys_client.ini

Replace `TargetApplicationPath=FallGuysEACLauncher.exe` with `TargetApplicationPath=FallGuys_client_game.exe` in `<path-to-FallGuys>/FallGuys_client.ini`.
![FallGuys6](https://user-images.githubusercontent.com/61798668/182596359-234a7ba6-b22a-4ba8-b65d-b65b83dc6a94.png)

### Copy easyanticheat_x64.so

Copy `<path-to-FallGuys>/EasyAntiCheat/easyanticheat_x64.so` to `<path-to-FallGuys>/FallGuys_client_game_Data/Plugins/x86_64/`
![FallGuys7](https://user-images.githubusercontent.com/61798668/182596802-43f59e71-bb44-429e-a455-16065c9d8fe9.png)

## ONLY NEEDED ON FLATPAK
### Enable gamemode

**Note**: Gamemode is shipped with heroic flatpak. Gamemode is needed to avoid `std::logic_error`
![FallGuys8](https://user-images.githubusercontent.com/61798668/182597088-e7a085ba-23ed-4739-87f8-002ed37e5688.png)

## Enable EOS Overlay
**Note**: Corefonts maybe need to be installed, via winetricks. Winetricks currently broken on heroic beta. You can installed them manually with `WINEPREFIX='<path-to-Heroic-Prefixes>/FallGuys' PATH='/<path-to-user-var-folder>/.var/app/com.heroicgameslauncher.hgl/config/heroic/tools/wine/<Wine-ge-version>/bin':$PATH /<path-to-user-var-folder>/.var/app/com.heroicgameslauncher.hgl/config/heroic/tools/winetricks corefonts`

![FallGuys9](https://user-images.githubusercontent.com/61798668/182597519-ef5ca4e9-089d-4499-95e3-d7e09b05d062.png)

## Troubleshooting

- Make sure you **don't** have set any enviroment variable, which is in conflict with `PROTON_EAC_RUNTIME` or similiar in the game and general settings
![FallGuys3](https://user-images.githubusercontent.com/61798668/182599115-e937b9fd-b28c-4d43-80d8-1b01cc2b8442.png)
![FallGuys10](https://user-images.githubusercontent.com/61798668/182599239-1c3def8d-f3a3-46a3-8bad-3797fa528a4c.png)





