`
```
yay -S vi-vim-symlink

grep -q '^ *source /etc/vimrc.local *$' /etc/vimrc ||
sudo tee -a /etc/vimrc >/dev/null <<EOF
" load local customizations
if filereadable("/etc/vimrc.local")
  source /etc/vimrc.local
endif
EOF

sudo tee /etc/vimrc.local >/dev/null <<EOF
runtime! defaults.vim
let g:skip_defaults_vim = 1
set mouse=
set noincsearch
set paste
set ruler
EOF

exit
```

vim customization:
note that vim is a bit unlike other apps:
- if ~/.vimrc is present, read it and don't read defaults.vim
- otherwise, read /etc/vimrc, then read defaults.vim

