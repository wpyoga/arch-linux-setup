`
```
# enable dmesg for all users

sudo tee /etc/sysctl.d/99-no-dmesg_restrict.conf >/dev/null <<EOF
kernel.dmesg_restrict=0
EOF

sudo systemctl restart systemd-sysctl

# filter audit messages for sudo invocations

sudo mkdir -p /etc/audit/rules.d/
sudo chmod 750 /etc/audit/rules.d/
sudo tee /etc/audit/rules.d/filter-sudo.rules >/dev/null <<EOF
-A exclude,always -F exe=/usr/bin/sudo
EOF

sudo auditctl -D
sudo systemctl enable --now auditd.service

# use human-readable time

cat >> ~/.bashrc <<"EOF"
alias dmesg='dmesg -HP'
EOF

exit
```

