`
```
cat >> ~/.bashrc <<"EOF"
alias diff='diff --color=auto'
alias grep='grep --color=auto'
alias ip='ip --color=auto'
alias dmesg='dmesg -H'
EOF

sudo sed -i /etc/pacman.conf -e 's,^[# ]*\(Color\) *$,\1,'

exit
```

