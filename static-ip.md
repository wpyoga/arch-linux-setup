`
```
# static network config

sudo tee /etc/systemd/network/20-mywifi.network >/dev/null <<EOF
[Match]
Name=wlan0
SSID=mywifi
[Network]
Address=192.168.18.80/24
Gateway=192.168.18.1
DNS=8.8.8.8
EOF

exit
```

