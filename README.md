# grub2-tweaks

# 📚 Topics
- [**Setting GRUB display resolution**](https://duckduckgo.com)
- **Using a custom background**

### 🖥️ Setting GRUB display resolution

When the grub screen pops up press `c` to enter the command line

Then enter **`vbeinfo`** or **`videoinfo`** to check available resolutions
 
Open the file `/etc/default/grub` and edit the line **`GRUB_GFXMODE=[height]x[width]x32`** to match your resolution

Finally, run grub-mkconfig -o /boot/grub/grub.cfg to update your grub config

### 🖌️ Using a custom background
