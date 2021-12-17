# grub2-tweaks

# 📚 Topics
- [**Setting GRUB display resolution**](https://github.com/vandalsoul/grub-tweaks/blob/main/README.md#%EF%B8%8F-setting-grub-display-resolution)
- [**Using a custom background**](https://github.com/vandalsoul/grub-tweaks/blob/main/README.md#%EF%B8%8F-using-a-custom-background)

### 🖥️ Setting GRUB display resolution

When the grub screen pops up press `c` to enter the command line

Then enter **`vbeinfo`** or **`videoinfo`** to check available resolutions
 
Open the file `/etc/default/grub` and edit the line **`GRUB_GFXMODE=[height]x[width]x32`** to match your resolution

Finally, run grub-mkconfig -o /boot/grub/grub.cfg to update your grub config

### 🖌️ Using a custom background

Make sure you have imagemagick installed, or at least something that provides convert
Find the resolution of your display, and make sure your background matches the resolution
(1920x1080 -> --1080p, 2560x1080 -> --ultrawide, 2560x1440 -> --2k, 3440x1440 -> --ultrawide2k, 3840x2160 -> --4k)
Place your custom background inside the root of the project, and name it background.jpg
Run the installer like normal, but with -s [YOUR_RESOLUTION] and -t [THEME] and -i [ICON]
Make sure to replace [YOUR_RESOLUTION] with your resolution and [THEME] with the theme
