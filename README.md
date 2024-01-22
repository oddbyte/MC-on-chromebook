  # Java edition on chromebook
## A tutorial on how to put minecraft Java edition on chromebook without using the crappy linux VM
![image](https://github.com/OddbyteWasTaken/MC-on-chromebook/assets/141666866/a328a927-d2ea-426e-8709-ae525235259f)

## Read this please:
This is so you can install a custom launcher to download mods. The default launcher you can download by typing `crew install minecraft` after installing chromebrew. This launcher is more difficult to work with and install mods on, so please just use the custom launcher. Mods are required as most chromebooks have garbage specs from 2011.


# Part one: Setting up your chromebook
### You WILL have to enable Developer mode to use this method.
SKIP TO PART TWO IF YOU HAVE DEV MODE ENABLED ALREADY
Step one: Enable developer mode. Press Escape, Refresh, and Power to get into the chromebook recovery screen. **THIS WILL RESET YOUR CHROMEBOOK**

![image](https://github.com/OddbyteWasTaken/MC-on-chromebook/assets/141666866/046dba92-e712-49df-b5ff-0b54adca952e)

Step two: Press Control and D to disable OS Verification (AKA Enable Developer mode) **THIS WILL RESET YOUR CHROMEBOOK**

![image](https://github.com/OddbyteWasTaken/MC-on-chromebook/assets/141666866/6cb493db-715a-4d06-9886-d175b4a6b740)

Step three: Enable the developer features in the first screen you see when you boot your chromebook. (The loud BEEP you get while booting can be skipped by pressing Control D)
# Part two: Installing minecraft
Alrightie, now that you have the hard part done, now its time to do the easy stuff.

Download the latest version of [GDLauncher](https://gdlauncher.com/en/download/).

Open the VT-2 Terminal by pressing Control, alt, Forward key.

Log into root with the password you set in part one step 3 (if you didnt set a password, or left the boxes empty, try to log into root with password `test0000`

Run `chromeos-setdevpasswd` to set password for user chronos.

Run `sudo --user=chronos bash` to log into chronos.

Install [ChromeBrew](https://github.com/chromebrew/chromebrew).

Run `crew install sommelier && crew install vim` (This downloads Sommelier, a very important application as it lets Minecraft actually open a window so you can play. Vim is a text editor we will be using.)

Run `cd ~/Downloads` to go into the downloads folder.

Run `sudo install GDLauncher-linux-setup.AppImage` (replace GDLauncher-linux-setup with the actual file name if it is different)

Run `vim ~/.bashrc` and press I (So you can edit it.)

Add
```
alias .minecraft='cd /usr/local/.config/gdlauncher_next/'

alias minecraft='/usr/local/GDLauncher/GDLauncher-linux-setup.AppImage' # (replace GDLauncher-linux-setup with the actual file name if it is different)

sudo mount -o remount,symfollow,exec "/media/removable/<Name of your SD / USB. spaces are allowed. Only put this line if you plan to run on a usb.>"
```
below where it says `#Put your fun stuff here.`

Save it, by pressing escape, and typing :wq and press enter.

Run `source ~/.bashrc`

If you want to open the .minecraft folder, type .minecraft into the shell after you install MC.

**IMPORTANT: If you plan to use the USB method, please skip this:** Go to the normal screen by pressing Control Alt Back. Press Control Alt T to open the Crosh terminal. run `shell` to open a shell. Run `minecraft` to open the installer and have funs. If you dont have access to crosh, or for some other reason you dont want to use it, just run `minecraft` in VT-2 as chronos.

# Part 3: USB

Make sure the USB Is plugged in and you added the `sudo mount` line in .bashrc

open the VT-2 Terminal if you closed it.

Run `cd /usr/local/.config`

Run `mkdir /media/removable/<Name of usb, press tab if you dont know it>/.minecraft/ && ln -s /media/removable/<Name of usb>/.minecraft gdlauncher_next` to link the folders.

# Part 4: Installing fabric mods to make minecraft play above 10 fps.
Most chromebooks are f\*cking garbage. They will not be able to run the latest MC version at anything playable.

Open the launcher by running `minecraft` in crosh's shell. If you dont have access to crosh, or for some other reason you dont want to use it, just run `minecraft` in VT-2 as chronos.

Install the launcher, and java, and log in with your minecraft account.

Press the **+** button in the bottom left of the window.

Open the CurseForge tab, and search for the modpack named `Fabulously Optimized`, and install it.

Play minecraft on the modpack on lowest settings, and get like 30 fps.

Have fun, and tell your friends about this repo. Please Star the repo. TY!
