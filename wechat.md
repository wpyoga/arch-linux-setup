`
```
#pacman -S --needed wine-mono wine-gecko

if ! grep -qE '^zh_CN\.UTF-8 +UTF-8' /etc/locale.gen; then
  sudo tee -a /etc/locale.gen >/dev/null <<EOF
zh_CN.UTF-8 UTF-8
EOF
  sudo locale-gen
fi

#WINEDLLOVERRIDES=mscoree=d wineboot -e -f -k -s

cat > /tmp/wechat.reg <<EOF
Windows Registry Editor Version 5.00
[HKEY_CURRENT_USER\Software\Wine\DllOverrides]
"*msvcp140"="native,builtin"
"*vcomp140"="native,builtin"
"*vcruntime140"="native,builtin"
EOF
wine regedit /tmp/wechat.reg
rm /tmp/wechat.reg

winetricks riched20

LANG=zh_CN.UTF-8 wine WeChatSetup_3.8.1.exe

sed -i \
  ~/Desktop/微信.desktop \
  ~/.local/share/applications/wine/Programs/微信/微信.desktop \
  -e 's,^\(Exec=env\) \(WINEPREFIX\),\1 LANG=zh_CN.UTF-8 \2,'

#chmod +x ~/Desktop/微信.desktop

exit
```

TODO: find a way to add this entry to 微信.desktop:
```
Name[en]=WeChat
```

And this entry to 卸载微信.desktop
```
Name[en]=Uninstall WeChat
```

WeChat 3.8.1 reports an error after login, WeChatOCR.exe crashes
using winecfg to set msvcp140.dll to native avoids the issue

