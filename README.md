![logo](/media/banner.png)

<p align="center">
  <a href="https://raw.githubusercontent.com/vandalsoul/grub-tweaks/main/LICENSE">
    <img src="https://img.shields.io/badge/License%20MIT-blue?style=for-the-badge&logo=github&logoColor=000000" alt="license" />
  </a>
  <a href="https://www.buymeacoffee.com/vandalsoul">
    <img src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-d4b700?style=for-the-badge&logo=buymeacoffee&logoColor=000000" alt="buymeacoffee" />
  </a>
</p>

<p align="center">
  <b>🙋 Hey there, if anyone wish to contribute new tweak-scripts 📝 / tweak-ideas ✨ then you are always welcome to do so 😄</b>
  <br>
  <b>Also if you found this page useful please give it a ⭐
</p>

# 📚 Topics

- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-using-a-custom-background)
- [**Adding icons for Submenus**](https://github.com/vandalsoul/grub-tweaks#-adding-icons-for-submenus) **💟 Credits @Brookg**
- [**Setting up GRUB theme in Kali Linux**](https://github.com/vandalsoul/grub-tweaks#-setting-up-grub-theme-in-kali-linux)
- [**Fix for GRUB theme not showing up**](https://github.com/vandalsoul/grub-tweaks#-grub-theme-not-showing-up--fix-for-fedora-) **( Fedora, Ubuntu )**
- Setting up GRUB init tunes
***
## 🖥️ Setting GRUB display resolution

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
## 🖌️ Using a custom background

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
## 🔮 Adding icons for Submenus

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
## 🐲 Setting up GRUB theme in Kali Linux
*Writing soon...*
***
## 🎩 Fix for GRUB theme not showing up ( Fedora, Ubuntu )

◻️ **Edit the GRUB config file `/etc/default/grub`**
```shell
sudo nano /etc/default/grub
```

◻️ **Change the line `GRUB_TERMINAL_OUTPUT=console` to this (*ie comment it out*) `#GRUB_TERMINAL_OUTPUT=console`**

◻️ **Change the line `GRUB_TIMEOUT_STYLE="hidden"` to this (*ie comment it out*) `#GRUB_TIMEOUT_STYLE="hidden"`**

◻️ **Then save the file and restart your pc**

## 🎶 Setting up GRUB init tunes

◻️ **Edit the GRUB config file `/etc/default/grub`**

◻️ **Uncomment the line `GRUB_INIT_TUNE="480 440 1"`**

◻️ **Now if you want you can keep the default tune or else use one from the cheatsheet**

◻️ **Finally, update your grub config file**
- **Debian ⛔ Ubuntu ⛔ Arch**
  ```shell
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
- **Fedora ⛔ Redhat**
  ```shell
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```
