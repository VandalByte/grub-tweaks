# grub2-tweaks

# 📚 Topics
- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks#%EF%B8%8F-using-a-custom-background)

## 🖥️ Setting GRUB display resolution

1️⃣ **When the grub screen pops up press `c` to enter the command line**

2️⃣ **Then enter **`vbeinfo`** or **`videoinfo`** to check available resolutions**
 
3️⃣ **Open the file `/etc/default/grub` and edit the line `GRUB_GFXMODE=[height]x[width]x32` to match your resolution**

4️⃣ **Finally, update your grub config file**
- **Debian ⛔ Ubuntu ⛔ Arch**
  ```shell
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
- **Fedora ⛔ Redhat**
  ```shell
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```

## 🖌️ Using a custom background

1️⃣ **Make sure to have your background match any of the following resolution**

|Class|Resolution ( in pixels )|
|:------:|:--------:|
|1080p|1920 x 1080|
|Ultrawide|2560 x 1080|
|2K|2560 x 1440|
|Ultrawide 2K|3440 x 1440|
|4K|3840 x 2160|

2️⃣ **Place the background image inside the GRUB theme root folder**

3️⃣ **Rename it as `background.jpg` or `background.png` (** *the image extension must be same as in `theme.txt`* **)**

