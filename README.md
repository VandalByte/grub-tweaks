![logo](/media/banner.png)

<p align="center">
  <b>If anyone wish to contribute new tweak-scripts 📝 or tweak-ideas ✨ then you are always welcome to do so 😄</b>
  <br>
  <b>Also if you found this page useful please consider giving it a star ⭐
</p>

# 📚 Topics

- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-using-a-custom-background)
- [**Adding icons for Submenus**](https://github.com/vandalsoul/grub-tweaks#-adding-icons-for-submenus) **💟 Credits @Brookg**
- [**Setting up GRUB theme in Kali Linux**](https://github.com/vandalsoul/grub-tweaks#-setting-up-grub-theme-in-kali-linux)
- [**Fix for GRUB theme not showing up**](https://github.com/vandalsoul/grub-tweaks#-fix-for-grub-theme-not-showing-up--fedora-ubuntu-) **( Fedora, Ubuntu )**
- [**Setting up GRUB init tunes**](https://github.com/vandalsoul/grub-tweaks#-setting-up-grub-init-tunes) **💟 By @Mage102**
- [**Restoring a broken GRUB install**](https://github.com/vandalsoul/grub-tweaks#-restoring-a-broken-grub-install) **💟 By @Jacksaur**
***
## 🖥️ [Setting GRUB display resolution](https://github.com/vandalsoul/grub-tweaks#-topics)

◻️ **First find your screen resolution**
```shell
xdpyinfo | awk '/dimensions/{print $2}'
```
 
◻️ **Open the file `/etc/default/grub` and edit the line `GRUB_GFXMODE=[height]x[width]x32` to match your resolution**

◻️ **Finally, update your grub config file**
- **Debian ⛔ Ubuntu ⛔ Arch**
  ```shell
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
- **Fedora ⛔ Redhat**
  ```shell
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```
***
## 🖌️ [Using a custom background](https://github.com/vandalsoul/grub-tweaks#-topics)

◻️ **Make sure to have your background match any of the following resolution**

|Class|Resolution ( in pixels )|
|:------:|:--------:|
|1080p|1920 x 1080|
|Ultrawide|2560 x 1080|
|2K|2560 x 1440|
|Ultrawide 2K|3440 x 1440|
|4K|3840 x 2160|

◻️ **Place the background image inside the GRUB theme root directory `/boot/grub/themes/THEME-DIRECTORY`**

◻️ **Rename it as `background.jpg` or `background.png` (***the image extension must be same as in `theme.txt`***)**
***
## 🔮 [Adding icons for Submenus](https://github.com/vandalsoul/grub-tweaks#-topics)

> **( NOTE ) 🚨 *Make sure to make a backup of the following files just to be on the safe side* 😶**
  
> ( NOTE ) 🚨 *This section will not work if you have used GRUB Customizer at all, as it changes around the files used here. You will need to uninstall GRUB Customizer and restore your original grub.d files to follow the instructions here.*

<p align="left">
  <img width=80% src="https://raw.githubusercontent.com/vandalsoul/grub-tweaks/main/media/submenu.png" alt="license" />
</p>

◻️ **First navigate to path `/etc/grub.d/`**

◻️ **Edit the file `10_linux` then find and change the line,**
```shell
echo "submenu '$(gettext_printf "Advanced options for %s" "${OS}" | grub_quote)' \$menuentry_id_option 'gnulinux-advanced-$boot_device_id' {"
```
**to**
```shell
echo "submenu '$(gettext_printf "Advanced options for %s" "${OS}" | grub_quote)' --class submenu \$menuentry_id_option 'gnulinux-advanced-$boot_device_id' {"
```

<br>

◻️ **Edit the file `30_uefi-firmware` then find and change the line,**
```shell
menuentry '$LABEL' \$menuentry_id_option 'uefi-firmware' {
```
**to**
```shell
menuentry '$LABEL' --class efi \$menuentry_id_option 'uefi-firmware' {
```

<br>

◻️ **Edit the file `20_memtest86+` then find and change the line,**
```shell
menuentry "Memory test (memtest86+)" {
```
**to**
```shell
menuentry --class memtest "Memory test (memtest86+)" {
```
**And the line,**
```shell
menuentry "Memory Test (64-bit UEFI)" {
```
**to**
```shell
menuentry --class memtest "Memory Test (64-bit UEFI)" {
```

<br>

◻️ **Finally, update your grub config file**
- **Debian ⛔ Ubuntu ⛔ Arch**
  ```shell
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
- **Fedora ⛔ Redhat**
  ```shell
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```
***
## 🐲 [Setting up GRUB theme in Kali Linux](https://github.com/vandalsoul/grub-tweaks#-topics)
*Writing soon...*
***
## 🎩 [Fix for GRUB theme not showing up](https://github.com/vandalsoul/grub-tweaks#-topics) ( Fedora, Ubuntu )

◻️ **Edit the GRUB config file `/etc/default/grub`**
```shell
sudo nano /etc/default/grub
```
◻️ **Change the lines below (***if any present***)**
```
GRUB_TERMINAL_OUTPUT=consoleㅤ-->ㅤ #GRUB_TERMINAL_OUTPUT=console

GRUB_TIMEOUT_STYLE="hidden"ㅤ -->ㅤ #GRUB_TIMEOUT_STYLE="hidden"

GRUB_ENABLE_BLSCFG=true   ㅤㅤ-->ㅤ GRUB_ENABLE_BLSCFG=false
```

◻️ **Finally, save the file and update your grub config file**
- **Debian ⛔ Ubuntu ⛔ Arch**
  ```shell
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
- **Fedora ⛔ Redhat**
  ```shell
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```
***
## 🎶 [Setting up GRUB init tunes](https://github.com/vandalsoul/grub-tweaks#-topics)

◻️ **Edit the GRUB config file `/etc/default/grub`**

◻️ **Uncomment the line `#GRUB_INIT_TUNE="480 440 1"`**

◻️ **Now if you want you can keep the default tune or else use one from the [cheatsheet](https://github.com/vandalsoul/grub-tweaks/blob/main/docs/GRUB%20INIT-TUNE%20CHEATSHEET.md)**

> 📢 *Just remember, longer the tune longer the boot time*

> 📢 *Music composers are also welcome to contribute in the cheatsheet*

◻️ **Finally, update your grub config file**
- **Debian ⛔ Ubuntu ⛔ Arch**
  ```shell
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
- **Fedora ⛔ Redhat**
  ```shell
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```
***
## ⁉ [Restoring a broken GRUB install](https://github.com/vandalsoul/grub-tweaks#-topics)
  
> **If you have somehow managed to break your GRUB installation, have lost your grub.d files, or just want to reinstall GRUB to start again from a fresh installation, this program will fully reinstall GRUB with all default settings.**

◻️ **Backup anything from GRUB you still want to save. This includes themes and any remaining edited grub.d files. Everything inside your grub folders will be deleted.**

◻️ **Download [boot-repair-disk](https://sourceforge.net/p/boot-repair-cd/home/Home/) and burn it to a USB. You can use a program like [Rufus](https://rufus.ie/en/) or [Ventoy](https://www.ventoy.net/en/index.html) to do so.**

◻️ **Shut down your computer, plug in the USB, start the computer and boot off it. Boot-Repair-Disk will now load up and ask whether you want to update. It's highly recommended you do this.**

◻️ **In the Boot Repair window, click the `Advanced Options` text in the corner. Make sure `Reinstall GRUB` is ticked ✅, then move to the `GRUB Options` tab and tick ✅ the `Purge GRUB before reinstalling it` option.**

<img width=50% src="https://raw.githubusercontent.com/vandalsoul/grub-tweaks/main/media/Reinstall.png" />

◻️ **Apply your changes, let the tool run, and it should pop up a window with a few terminal commands to run. Press `CTRL + ALT + T` to open a terminal, copy the first command from the window, and paste it in with `CTRL + SHIFT + V`. Run each command in sequence like this and click continue when you have finished. GRUB will now be reinstalled.**

◻️ Reboot your system and you will now have a completely default GRUB installation again.
