![logo](/media/banner.png)

<p align="center">
  <b>If anyone wish to contribute new tweak-scripts 📝 or tweak-ideas ✨ then you are always welcome to do so 😄</b>
  <br>
  <b>Also if you found this page useful please consider giving it a star ⭐
</p>

# 📚 Topics

- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-using-a-custom-background)
- [**Fixing incorrect icons for Distro entries**](https://github.com/vandalsoul/grub-tweaks#-fixing-incorrect-icons-for-distro-entries) **💟 By @Jacksaur**
- [**Adding icons for Submenus**](https://github.com/vandalsoul/grub-tweaks#-adding-icons-for-submenus) **💟 Credits @Brookg**
- [**Setting up GRUB theme in Kali Linux**](https://github.com/vandalsoul/grub-tweaks#-setting-up-grub-theme-in-kali-linux)
- [**Fix for GRUB theme not showing up**](https://github.com/vandalsoul/grub-tweaks#-fix-for-grub-theme-not-showing-up--fedora-ubuntu-) **( Fedora, Ubuntu )**
- [**Setting up GRUB init tunes**](https://github.com/vandalsoul/grub-tweaks#-setting-up-grub-init-tunes) **💟 By @Mage102**
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

◻️ **Rename it as `background.jpg` or `background.png` (** *the image extension must be same as in `theme.txt`* **)**
***
## ⁉ [Fixing incorrect icons for Distro entries](https://github.com/vandalsoul/grub-tweaks#-topics)
  
> **Backup all the files in this folder before performing these actions! They are crucial files for GRUB.**
◻️  **Navigate to '/etc/grub.d/'**
  
◻️  **Open and reach through each of the files until you find the entry for the Distro that has an incorrect icon. It will likely be one of the XX_linux_proxy files.**
  
  
## 🔮 [Adding icons for Submenus](https://github.com/vandalsoul/grub-tweaks#-topics)

> **( NOTE ) 🚨 *Make sure to make a backup of the following files just to be on the safe side* 😶**

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
◻️ **Change the lines below (** *if any present* **)**
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
