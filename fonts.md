`
```
sudo pacman -S ttf-dejavu ttf-liberation noto-fonts noto-fonts-cjk noto-fonts-emoji

sudo tee /etc/profile.d/freetype2.sh >/dev/null <<EOF
export FREETYPE_PROPERTIES="truetype:interpreter-version=40"
EOF

sudo tee /etc/fonts/conf.d/40-noto-sans-mono-spacing.conf > /dev/null <<EOF
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
  <match target="scan">
    <test name="family">
      <string>Noto Sans Mono</string>
    </test>
    <edit name="spacing">
      <int>100</int>
    </edit>
  </match>
</fontconfig>
EOF

#sudo tee /etc/fonts/conf.d/99-hinting-override.conf > /dev/null <<EOF
#<?xml version="1.0" encoding="UTF-8"?>
#<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
#<fontconfig>
#  <match target="font">
#    <edit name="hinting" mode="assign">
#      <bool>true</bool>
#    </edit>
#  </match>
#</fontconfig>
#EOF

sudo sh <<EOF
cp /usr/share/fontconfig/conf.avail/10-autohint.conf /etc/fonts/conf.d/
cp /usr/share/fontconfig/conf.avail/10-sub-pixel-rgb.conf /etc/fonts/conf.d/
cp /usr/share/fontconfig/conf.avail/70-no-bitmaps.conf /etc/fonts/conf.d/
fc-cache -rf
EOF

exit
```




