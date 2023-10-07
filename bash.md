`
```
yay -S bash-completion

cat >> ~/.bashrc <<"EOF"
# ignore repeated commands and command lines starting with a space
export HISTCONTROL=ignoreboth
# save 9999 history items
export HISTSIZE=9999
# color the prompt
PS1='[\[\033[01;32m\]\u@\h\[\033[00m\] \[\033[01;34m\]\W\[\033[00m\]]\$ '
# provide command-not-found functionality
. /usr/share/doc/pkgfile/command-not-found.bash
EOF

exit
```

