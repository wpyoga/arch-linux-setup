`
```
# might be a better idea to do this by hand...
sudo sed -i /etc/pacman.conf \
  -e 'N;s,^#\(\[multilib]\)\n#\(Include = /etc/pacman.d/mirrorlist$\),\1\n\2,'

# if the file does not contain the required section, add it at the very end
grep /etc/pacman.conf -e '^\[multilib\]$' -A1 \
  | tr -d '\n' \
  | grep -q '^\[multilib\]Include = /etc/pacman\.d/mirrorlist$' \
  || sudo tee -a /etc/pacman.conf >/dev/null <<EOF
[multilib]
Include = /etc/pacman.d/mirrorlist
EOF

sudo mkdir -p /etc/pacman.d/hooks/
sudo tee /etc/pacman.d/hooks/stop-wine-associations.hook >/dev/null <<"EOF"
[Trigger]
Operation = Install
Operation = Upgrade
Type = Path
Target = usr/share/wine/wine.inf
[Action]
Description = Prevent Wine from configuring file associations
When = PostTransaction
Exec = sh -c 'grep -q "HKCU,\"Software\\\Wine\\\FileOpenAssociations\",\"Enable\",2,\"N\"" /usr/share/wine/wine.inf || sed -i "s/\[Services\]/\[Services\]\nHKCU,\"Software\\\Wine\\\FileOpenAssociations\",\"Enable\",2,\"N\"/g" /usr/share/wine/wine.inf'
EOF

sudo pacman -Sy

sudo pacman -S --needed wine

exit
```

