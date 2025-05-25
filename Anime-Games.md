# Genshin Impact

Since around April 2023, Genshin Impact has been playable in Linux. As of HoyoPlay Launcher v1.5.2, a runner based on Wine 10 must be used. The launcher can technically run with GE-Proton, but the game's anticheat behaves differently when using stock Proton versus GE-Proton, so stock Proton (e.g., Proton 10) installed via Steam is required to run the actual game.

1. Set the game's runner to Proton 10 or newer.
2. Ensure that umu is enabled.
3. If you get a `Wine C++ Runtime Library` error, add an environment variable for `WINEDLLOVERRIDES = lsteamclient=d`.

# Zenless Zen Zero

Zenless Zen Zero does not have the same anticheat restrictions as Genshin Impact. You can follow the above directions above if you prefer to use stock Proton. Otherwise, you can run HoyoPlay Launcher and the game with GE-Proton10-x with umu enabled.

# Infinity Nikki

The EGS build of Infinity Nikki currently does work SteamOS running on the Steam Deck. However, any other device or distro, even if running on a Steam Deck, will not work.

# Wuthering Waves

The [Steam version](https://store.steampowered.com/app/3513350/Wuthering_Waves/) includes a note stating "We're working to resolve Wuthering Waves' compatibility with STEAM DECK and will share updates in the community. Thanks for your understanding!"