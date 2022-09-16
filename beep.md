`
```
# disable beep when rebooting
sudo tee /etc/modprobe.d/blacklist-pcspkr.conf >/dev/null <<EOF
blacklist pcspkr
EOF

exit
```

