![logo](/media/banner.png)

<p align="center">
  <a href="https://raw.githubusercontent.com/vandalsoul/dedsec-grub2-theme/main/LICENSE">
    <img src="https://img.shields.io/badge/License%20MIT-008a8a?style=for-the-badge&logo=github&logoColor=000000" alt="license" />
  </a>
  <a href="https://www.buymeacoffee.com/vandalsoul">
    <img src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-d4b700?style=for-the-badge&logo=buymeacoffee&logoColor=000000" alt="license" />
  </a>
</p>

# 📚 Topics
- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-using-a-custom-background)

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

