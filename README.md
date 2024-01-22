  # Java edition on chromebook
## A tutorial on how to put minecraft Java edition on chromebook without using the crappy linux VM
![image](https://github.com/OddbyteWasTaken/MC-on-chromebook/assets/141666866/a328a927-d2ea-426e-8709-ae525235259f)

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

Run `crew install sommlier && crew install vim` (This downloads Sommlier, a very important application as it lets Minecraft actually open a window so you can play. Vim is a text editor we will be using.)

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

**IMPORTANT: If you plan to use the USB method, please skip this:** Go to the normal screen by pressing Control Alt Back. Press Control Alt T to open the Crosh terminal. run `shell` to open a shell. Run `minecraft` to open the installer and have funs.

# Step 3: USB
If you want to put MC on a USB, dont open minecraft yet. That is a bad idea.

Make sure the USB Is plugged in and you added the `sudo mount` line in .bashrc

open the VT-2 Terminal if you closed it.

Run `cd /usr/local/.config`

Run `mkdir /media/removable/<Name of usb, press tab if you dont know it>/.minecraft/ && ln -s /media/removable/<Name of usb>/.minecraft gdlauncher_next` to link the folders.

You are done, run `minecraft` to open the launcher, 
