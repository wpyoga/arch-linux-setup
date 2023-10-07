`
```
cat >> ~/.bashrc <<"EOF"
alias diff='diff --color=auto'
alias grep='grep --color=auto'
alias ip='ip --color=auto'
EOF

sudo sed -i /etc/pacman.conf -e 's,^[# ]*\(Color\) *$,\1,'

exit
```

