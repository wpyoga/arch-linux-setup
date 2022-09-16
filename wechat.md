`
```
#pacman -S --needed wine-mono wine-gecko

if ! grep -qE '^zh_CN\.UTF-8 +UTF-8' /etc/locale.gen; then
  sudo tee -a /etc/locale.gen >/dev/null <<EOF
zh_CN.UTF-8 UTF-8
EOF
  sudo locale-gen
fi

winetricks riched20

LANG=zh_CN.UTF-8 wine WeChatSetup_3.7.6.exe

sed -e 's,^\(Exec=env\) \(WINEPREFIX\),\1 LANG=zh_CN.UTF-8 \2,' -i ~/Desktop/微信.desktop

exit
```

