`
```
sudo pacman -S --needed ibus ibus-libpinyin

while read VAR; do
  sudo sed -i /etc/environment -e "\$a$VAR" -e "/${VAR%%=*}/d"
done <<-EOF
  GTK_IM_MODULE=ibus
  QT_IM_MODULE=ibus
  XMODIFIERS=@im=ibus
EOF

sudo tee /etc/xdg/autostart/ibus.desktop >/dev/null <<EOF
[Desktop Entry]
Type=Application
Name=Ibus
Exec=ibus-daemon -drxR
Icon=ibus
EOF

gsettings set org.freedesktop.ibus.panel property-icon-delay-time 0
gsettings set org.freedesktop.ibus.general switcher-delay-time 0

gsettings set org.freedesktop.ibus.general engines-order "['xkb:us::eng', 'libpinyin']"
gsettings set org.freedesktop.ibus.general preload-engines "['xkb:us::eng', 'libpinyin']"
gsettings set org.freedesktop.ibus.general.hotkey triggers "['<Control>space']"

gsettings set org.freedesktop.ibus.panel lookup-table-orientation 0
gsettings set org.freedesktop.ibus.panel use-custom-font true
gsettings set org.freedesktop.ibus.panel custom-font "'Sans 14'"


gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin dynamic-adjust true
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin remember-every-input true
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin sort-candidate-option 0
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin dictionaries "'12;15'"
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin english-candidate false
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin english-input-mode false
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin main-switch ''
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin emoji-candidate false
gsettings set com.github.libpinyin.ibus-libpinyin.libpinyin lua-extension false

exit
```

