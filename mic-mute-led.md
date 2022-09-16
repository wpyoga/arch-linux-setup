`
```
#mkdir -p ~/.config/autostart/
#tee ~/.config/autostart/mic-mute-led-off.desktop >/dev/null <<EOF
#[Desktop Entry]
#Type=Application
#Name=Turn off mic LED
#Exec=sh -c "echo 0 | tee /sys/class/leds/platform::micmute/brightness >/dev/null"
#EOF

sudo tee /etc/systemd/system/mic-mute-led-off.service >/dev/null <<EOF
#[Unit]
#Description=Turn off mic mute LED
[Service]
ExecStart=sh -c "echo 0 | tee /sys/class/leds/platform::micmute/brightness >/dev/null"
[Install]
WantedBy=basic.target
EOF

sudo systemctl enable mic-mute-led-off.service

exit
```


