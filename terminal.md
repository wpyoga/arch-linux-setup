`
```
# customize terminal

cat > /tmp/terminalrc <<EOF
[Configuration]
ColorBackground=#222
ColorCursor=#777
ColorPalette=#000;#f66;#7e7;#fe8;#49f;#f7f;#3ee;#ddd;#666;#faa;#afa;#ffa;#6bf;#faf;#7ff;#fff;
MiscCursorBlinks=TRUE
MiscDefaultGeometry=96x32
MiscMenubarDefault=FALSE
MiscCopyOnSelect=TRUE
MiscSlimTabs=TRUE
MiscNewTabAdjacent=TRUE
MiscShowUnsafePasteDialog=FALSE
ScrollingUnlimited=TRUE
FontName=DejaVu Sans Mono 10.5
EOF

mkdir -p ~/.config/xfce4/terminal/
mv -T /tmp/terminalrc ~/.config/xfce4/terminal/terminalrc

exit
```

