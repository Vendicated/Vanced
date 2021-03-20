
# Setting Up ADB

In this guide you will learn how to set up ADB

---

## About ADB

1. [ADB](https://en.droidwiki.org/wiki/Android_Debug_Bridge) (Android Debug Bridge) is a command line tool that lets you communicate with your Android device from your PC.
2. It has a bunch of useful features like installing/uninstalling apps, collecting system logs from your phone and debugging apps.
3. It is an official Android [SDK](https://en.wikipedia.org/wiki/Software_development_kit) tool developed by Google, so it is completely safe to download and use!

---

## Prerequisites

### You will need

- PC (Windows/Mac/Linux)
- USB cable to connect your phone to your PC
- You can follow the written directions without any outside help.

### Enabling USB Debugging on your phone

In order to debug your phone with ADB you first have to allow it. To do so, simply do the following steps on your phone:

- Enable Developer Options. You can do so by going to `Settings > About Phone` and tapping Build Number 7 times
- Now go to `Settings > System > Developer options` and enable USB Debugging

---

## Installing ADB

###  Windows
   <details> <summary></summary>

[ADB Download Link](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)

Extract the zip
Now open a command prompt in this directory. You can do so by holding shift and right clicking the folder and then pressing `Open Powershell here`
alternatively you can [`cd` for Windows](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/cd) into the location if you have to run command prompt as administrator for any reason like `cd C:\Users\Ven\Downloads\adb` or `cd /home/Ven/Downloads/adb`

</details>

###  Mac
   <details> <summary></summary>

-  > Mac is basically the windows method but your using [Bash](https://en.m.wikipedia.org/wiki/Bash_(Unix_shell)) or [Zsh](https://en.m.wikipedia.org/wiki/Z_shell) like on Linux

Download the Android Debug Bridge (Aka ADB)
[ADB Down Link](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip)

Extract the zip
Now open a Terminal in this directory.
You can use [`cd` for Linux/Mac](https://linuxize.com/post/linux-cd-command/)

</details>

### Linux
 <details> <summary></summary>
      <details> <summary>Debian</summary>

`sudo apt install adb -y`
      </details>
<details> <summary>Arch</summary>

`sudo pacman -S adb`
</details>

Alternatively you can do the same as the Mac guide but using this [ADB download link](https://dl.google.com/android/repository/platform-tools-latest-linux.zip).

</details>

Congratulations! You're all set and ready to use adb!

[Jump To BrokenVancedPackage Fix](./BrokenVancedPackage.md) || [Jump To Creating A Logcat](./CreatingALogcat.md)

---

## Getting started using adb
> Learn ADB

### Now you can execute adb commands via:

- Windows: `.\adb myCommand`
- Linux : `adb myCommand`
- Mac/Linux: `./adb myCommand`

Make sure your phone is connected to your PC and unlocked!

---

## Let's test it!

- Unlock your phone and connect it to your PC
- Run `.\adb devices` or `./adb devices` or `adb devices` depending on your [OS](https://en.wikipedia.org/wiki/Operating_system)
- If everything is okay, you should now get a popup on your Phone whether you want to allow USB Debugging. Select yes
- Your Terminal should print something like

```bash
List of devices attached
576OPB01    device
```
- you may have to run `adb devices` a 2nd time

## Advanced - Adding adb to path for easier access
> if you installed via command line on linux you can skip this entirely.

path is a variable that exists on all operating systems. It tells your terminal where to look for programs so you don't have to be in that program's directory all the time.

By adding adb to your path you can execute it from anywhere by simply typing `adb`. Doing so is very simple actually!

### Adding adb to your path on Windows

- Open the app search bar
- Search for env and choose `Edit the system environment variables`
- Click the Environment Variables button
- Under System Variables in the second half find PATH and click on edit
- Click New and paste the full path to the adb folder

Next time you start a terminal you can just run `adb` and it will know where to look!

### Adding adb to your path on Linux or Mac

- Open a terminal
- Find out which shell you're using via `echo $SHELL`
- Run the appropriate command for your shell:
  - zsh -> `echo "export PATH=/FULL/PATH/TO/ADB/FOLDER:$PATH" >> ~/.zshrc`
  - bash -> `echo "export PATH=/FULL/PATH/TO/ADB/FOLDER:$PATH" >> ~/.bash_profile`
- Make sure you replace `/FULL/PATH/TO/ADB/FOLDER` with the actual path
- Example with my setup: `echo "export PATH=/home/ven/Downloads/adb:$PATH" >> ~/.zshrc`

Next time you start a terminal you can just run `adb` and it will know where to look!
