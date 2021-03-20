# Broken Vanced Package Fix

![INSTALL_FAILED_UPDATE_INCOMPATIBLE](../Assets/AndroidUpgradeIssue.jpg)

If you are running into this issue or `INSTALL_FAILED_VERSION_DOWNGRADE` then you are at the right spot!

This error is not caused by Vanced; It is caused by Your ROMs package manager. A bug in your package manager makes Vanced no longer visible to the system but is still installed somewhere in your system.

Sadly you can only fix this issue if you have root or a PC, Otherwise the only way to fix it is to factory reset your phone. Sorry! Blame your OEM/Vendor!

___

## Prerequisites

### You will need

- EITHER a PC with adb set up - A guide to do this can be found [here](./SettingUpAdb.md)
- OR a rooted phone

___

## Uninstalling the leftover Vanced

Luckily we can still remove it via the command line! Once you uninstalled it you can just install it back like usual


### Uninstalling the broken Vanced using adb on your PC

- Run the following adb command. Unless you added adb to PATH, add a `.\` before the command. Having issues? Check [our adb Guide](./SettingUpAdb.md#getting-started-using-adb)

```ts
adb uninstall com.vanced.android.youtube
```

### Uninstalling the broken Vanced using root

- First you need a Terminal. I recommend [Termux](https://play.google.com/store/apps/details?id=com.termux)
- Open it up and run the following command

```bash
su -c "pm uninstall com.vanced.android.youtube"
```

### Fail Safe
If all else fails you can run 
`adb shell pm list users` or if you're root `su -c "pm list users"` should return something like following :

```ts
        UserInfo{0:USER_NAME:c15} running
        UserInfo{150:USER_NAME:SOME_NUMBER} running
```

User 0 is the system user and the other user (In this case, it's user 150) is the actual user.
So you can run following command to specify which user to delete youtube vanced.

```ts
adb shell pm uninstall --user 150 com.vanced.android.youtube
```
Or
```bash
su -c "pm uninstall --user 150 com.vanced.android.youtube"
```
