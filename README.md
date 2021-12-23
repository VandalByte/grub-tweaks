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
  <b>Hey there 🙋, if anyone wish to contribute new ideas 🧠 / tweaks 💡 you are always welcome to do so... Let's make this page as complete as possible 😄</b>
</p>

# 📚 Topics
- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-using-a-custom-background)
- [**Adding icons for Submenus**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-adding-icons-for-submenus)
- [**Setting up GRUB theme in Kali Linux**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-setting-up-grub-theme-in-kali-linux)
- [**Fix for GRUB theme not showing up ( in Fedora )**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-fix-for-grub-theme-not-showing-up--in-fedora-)

## 🖥️ Setting GRUB display resolution

◻️ **When the grub screen pops up press `c` to enter the command line**

◻️ **Then enter **`vbeinfo`** or **`videoinfo`** to check available resolutions**
 
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

## 🖌️ Using a custom background

◻️ **Make sure to have your background match any of the following resolution**

|Class|Resolution ( in pixels )|
|:------:|:--------:|
|1080p|1920 x 1080|
|Ultrawide|2560 x 1080|
|2K|2560 x 1440|
|Ultrawide 2K|3440 x 1440|
|4K|3840 x 2160|

◻️ **Place the background image inside the GRUB theme root folder**

◻️ **Rename it as `background.jpg` or `background.png` (** *the image extension must be same as in `theme.txt`* **)**

## 🔮 Adding icons for Submenus

## 🐲 Setting up GRUB theme in Kali Linux

## 🎍 Fix for GRUB theme not showing up ( in Fedora )

