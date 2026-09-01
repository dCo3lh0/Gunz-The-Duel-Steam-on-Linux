# Gunz-The-Duel-Steam-on-Linux
Here lies my personal configuration method to install and play Gunz: The Duel on Linux collecting the best tips from everyone that helped making this process.

This tutorial was made for report on [ProtonDB](https://www.protondb.com/app/3139440)

## Downloading and installing ProtonUp-Qt first and installing "Proton-CachyOS-10.0-Sunset-SLR"

Before starting lets install the proton version used by this tutorial:
1. Download ProtonUp-Qt, you can download it from this link [Here](https://github.com/DavidoTek/ProtonUp-Qt/releases)
2. Download the appimage, right-click and properties and mark the file as executable (depends on the DE)
3. If you do not have a right-click menu option for this just open the terminal on the directory of the AppImage and then:
> ```chmod a+x ProtonUp-Qt-2.15.1-x86_64.AppImage```
4. With ProtonUp-Qt open, download and install "proton-cachyos" > "10.0-sunset-slr", wait until its done and close the program.

## Now Steam

1. Start Steam
2. On Steam > Library, select Gunz: The Duel, press right button and go into properties
3. On Compatibility tab, set "Force the use of a specific Steam Play compatibility tool"
4. Select "proton-cachyos-10.0-sunset-slr" from the dropdown.
5. Check the ports that steam uses to play the game with this command in terminal(usually 5200 or 16101):
> ```strings ~/.local/share/Steam/appcache/appinfo.vdf | grep -iE 'masangsoft|STEAM\|'```
6. On General tab add this line to the launch options:
> ```bash -c 'exec "$@" "STEAM|use1.masangsoft.com|16101|3139440"' -- %command%```
7. Note if you have the game already installed, first, uninstall it on steam client.
8. Click install and wait until it ends.
9. Launch the game just a single time it will install `EAC`, `Visual C Redist` and `DirectX` before trying to launch the game
10. Wait until the launcher crashes.
11. With the game closed, we will now install MSXML6 (NOT 3!!), with the terminal command:
> ``protontricks 3139440 msxml6``
12. Wait until protontricks is done.
13. Start the game and have fun.
