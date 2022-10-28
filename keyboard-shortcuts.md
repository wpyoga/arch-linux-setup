`
```
sudo pacman -S xcape

xfconf-query -c xfce4-keyboard-shortcuts -p '/commands/custom/<Primary>Escape' -r
xfconf-query -c xfce4-keyboard-shortcuts -p '/commands/custom/<Primary><Alt>Escape' -r
xfconf-query -c xfce4-keyboard-shortcuts -p '/commands/custom/XF86Display' -r

#xfconf-query -c xfce4-keyboard-shortcuts -p '/commands/custom/Super_L' -n -t string -s xfce4-popup-whiskermenu
#xfconf-query -c xfce4-keyboard-shortcuts -p '/commands/custom/Super_L' -r
xfconf-query -c xfce4-keyboard-shortcuts -p '/commands/custom/<Alt>F1' -n -t string -s xfce4-popup-whiskermenu
#xcape -e 'Super_L=Alt_L|F1'

# there is a longstanding X.org bug
# https://forum.xfce.org/viewtopic.php?id=10925
# https://aur.archlinux.org/packages/xorg-server-bug865
# https://gitlab.xfce.org/xfce/libxfce4ui/-/issues/1
# https://gitlab.freedesktop.org/xorg/xserver/-/issues/258

mkdir -p ~/.config/autostart/
tee ~/.config/autostart/xcape.desktop >/dev/null <<EOF
[Desktop Entry]
Type=Application
Name=Xcape
Exec=xcape -t 2000 -e 'Super_L=Alt_L|F1'
EOF

xfconf-query -c xfce4-keyboard-shortcuts -p '/xfwm4/custom/<Alt>Home' -r
xfconf-query -c xfce4-keyboard-shortcuts -p '/xfwm4/custom/<Alt>Delete' -r

xfconf-query -c xfce4-keyboard-shortcuts \
  -p '/xfwm4/custom/<Super>Up' -n -t string -s tile_up_key
xfconf-query -c xfce4-keyboard-shortcuts \
  -p '/xfwm4/custom/<Super>Down' -n -t string -s tile_down_key
xfconf-query -c xfce4-keyboard-shortcuts \
  -p '/xfwm4/custom/<Super>Left' -n -t string -s tile_left_key
xfconf-query -c xfce4-keyboard-shortcuts \
  -p '/xfwm4/custom/<Super>Right' -n -t string -s tile_right_key

xfconf-query -c xfce4-keyboard-shortcuts -p '/xfwm4/custom/<Primary><Alt>d' -r
xfconf-query -c xfce4-keyboard-shortcuts \
  -p '/xfwm4/custom/<Super>d' -n -t string -s show_desktop_key

sudo tee /etc/X11/xorg.conf.d/99-dontzap.conf >/dev/null <<EOF
Section "ServerFlags"
    Option "DontZap" "true"
EndSection
EOF


exit
```

