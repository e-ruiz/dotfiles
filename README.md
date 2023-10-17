# Dotfiles

# Touchpad bugs with libinput

Check https://smarttech101.com/libinput-fix-your-linux-touchpad-using-libinput/

```bash
# /etc/X11/xorg.conf
# or
# /usr/share/X11/xorg.conf.d/??-libinput.conf
Section "InputClass"
    Identifier "libinput touchpad catchall"
    MatchIsTouchpad "on"
    MatchDevicePath "/dev/input/event*"
    Driver "libinput"
    Option "Tapping" "on"
    Option "NaturalScrolling" "true"
    Option "ClickMethod" "clickfinger"
    Option "TappingButtonMap" "lrm"
    Option "AccelSpeed" "0.5"
    Option "DisableWhileTyping" "true"
EndSection
```

Restart lightdm: `systemctl restart lightdm`
