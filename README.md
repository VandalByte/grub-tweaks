# grub2-tweaks

# 📚 Topics
- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks/blob/main/README.md#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks/blob/main/README.md#%EF%B8%8F-using-a-custom-background)

### 🖥️ Setting GRUB display resolution

- When the grub screen pops up press `c` to enter the command line

- Then enter **`vbeinfo`** or **`videoinfo`** to check available resolutions
 
- Open the file `/etc/default/grub` and edit the line **`GRUB_GFXMODE=[height]x[width]x32`** to match your resolution

- Finally, run grub-mkconfig -o /boot/grub/grub.cfg to update your grub config

### 🖌️ Using a custom background

- Make sure you have your background match any of the following resolution

|Class|Resolution (in pixels)|
|:------:|:--------:|
|1080p|1920 x 1080|
|Ultrawide|2560 x 1080|
|2K|2560 x 1440|
|Ultrawide 2K|3440 x 1440|
|4K|3840 x 2160|

- Place the background image inside the GRUB theme root folder
- Rename it as `background.jpg` or `background.png` **(** *the image extension must be same as in `theme.txt`* **)**

