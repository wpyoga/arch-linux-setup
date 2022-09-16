`
```
xfconf-query -c xsettings -p /Net/ThemeName -s "Adwaita"
xfconf-query -c xsettings -p /Net/IconThemeName -s "HighContrast"

xfconf-query -c xsettings -p /Xft/DPI -s 96
xfconf-query -c xsettings -p /Xft/Antialias -s 1
xfconf-query -c xsettings -p /Xft/Hinting -s 1
xfconf-query -c xsettings -p /Xft/HintStyle -s "hintfull"
xfconf-query -c xsettings -p /Xft/RGBA -s "rgb"

xfconf-query -c xsettings -p /Gtk/CanChangeAccels -s false
xfconf-query -c xsettings -p /Gtk/FontName -s "Liberation Sans 10.5"
xfconf-query -c xsettings -p /Gtk/MonospaceFontName -s "Noto Sans Mono 10"

exit
```

