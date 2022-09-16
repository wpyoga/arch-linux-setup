`
```
killall xfconfd
#sleep .2
cp /etc/xdg/xfce4/panel/default.xml ~/.config/xfce4/xfconf/xfce-perchannel-xml/xfce4-panel.xml
find ~/.config/xfce4/panel/ \
  -type f \
  ! -name xfce4-terminal-emulator.desktop \
  ! -name xfce4-file-manager.desktop \
  ! -name xfce4-web-browser.desktop \
  -exec rm '{}' ';'
find ~/.config/xfce4/panel/ \
  -type d -empty \
  ! -name launcher-17 \
  ! -name launcher-18 \
  ! -name launcher-19 \
  -exec rmdir -p '{}' ';'

# if we do this, the panel launchers are sometimes messed up
#rm -r ~/.config/xfce4/panel/
#rm -r ~/.config/xfce4/panel/launcher-*

mkdir -p ~/.config/xfce4/panel/launcher-{17,18,19}
cp /usr/share/applications/xfce4-terminal-emulator.desktop ~/.config/xfce4/panel/launcher-17/
cp /usr/share/applications/xfce4-file-manager.desktop ~/.config/xfce4/panel/launcher-18/
cp /usr/share/applications/xfce4-web-browser.desktop ~/.config/xfce4/panel/launcher-19/

xfconf-query -c xfce4-panel -p /panels/panel-2 -r -R
xfconf-query -c xfce4-panel -p /panels -a -t int -s 1
xfconf-query -c xfce4-panel -p /panels/dark-mode -s false
xfconf-query -c xfce4-panel -p /panels/panel-1/position -s 'p=4;x=0;y=0'
xfconf-query -c xfce4-panel -p /panels/panel-1/size -s 32
xfconf-query -c xfce4-panel -p /panels/panel-1/icon-size -s 24
xfconf-query -c xfce4-panel \
  -p /panels/panel-1/plugin-ids \
  -t int -t int -t int -t int -t int \
  -t int -t int -t int -t int -t int \
  -t int -t int -t int -t int -t int \
  -t int \
  -s 1 -s 15 -s 19 -s 18 -s 17 \
  -s 2 -s 3 -s 4 -s 5 -s 6 \
  -s 8 -s 9 -s 10 -s 11 -s 12 \
  -s 13
xfconf-query -c xfce4-panel -p /plugins/plugin-1 -n -t string -s whiskermenu
xfconf-query -c xfce4-panel -p /plugins/plugin-2/grouping -n -t uint -s 0
xfconf-query -c xfce4-panel -p /plugins/plugin-2/flat-buttons -n -t bool -s false
xfconf-query -c xfce4-panel -p /plugins/plugin-2/show-labels -n -t bool -s true
xfconf-query -c xfce4-panel -p /plugins/plugin-2/window-scrolling -n -t bool -s false
xfconf-query -c xfce4-panel -p /plugins/plugin-2/middle-click -n -t uint -s 1
xfconf-query -c xfce4-panel -p /plugins/plugin-2/sort-order -n -t uint -s 4
xfconf-query -c xfce4-panel -p /plugins/plugin-20 -r -R
xfconf-query -c xfce4-panel -p /plugins/plugin-21 -r
xfconf-query -c xfce4-panel -p /plugins/plugin-22 -r

cat > ~/.config/xfce4/panel/whiskermenu-1.rc <<EOF
button-title=XFCE
show-button-title=true
launcher-show-tooltip=false
hover-switch-category=true
position-search-alternate=true
position-categories-alternate=true
EOF

xfce4-panel -r

exit
```


H4sIAAAAAAAAA7VX27KiMBB89yss3qOinlsd8bztF+x+QIARU4SEzWWV/fqNKK56MhItfROqpzM9
menBxde24sM/oDSTIoni0SQagshkzkSRRL9+/iDv0ddyMFhkayoE8KGgFSTRdpXBnNTUvYnOo5eD
4XBRK1mDMs0BnUmxYoWDRUPT1O4FE8aFUW7d72k09sW03LoLoErRpuV2yDbQwxTvmb5z5VSVpJI5
dHSplPwYtqJcAxbapkHiLhCq2nR5eMBSM+Mq0aG1Ua6Mx4PqZP65TSafTTLpjvvOwUEUZt0x2DN9
kytx3dmEy6yE3KvUKAs4A3PXRDT7C97Dp3M8Eg2aTa8kzG3BBGG595LDLvo66iUM9hEGew+DvQXB
pkGoWRBqHoQKK8ZrECqsFIF1nYTBAu88rLBxWGXj054fd/17MIqz54snb6trn4kgUxEjFkLrmrOM
7gZdVyAsakWpNcaN826mESqpitHOxketxY02a6ZLUC3p2CcRzXWKHGCoLjnTBs2xUNLWbYTHOq5Y
3YpTQ/YCdb+je+xqLTeE0/Rkv9xgkxsmchevMyU5P8n+lgwqluccSObusvRb/ZXspTJEqvz/NrVe
Nwi8vRlyexpqqqiRCr0+2LrOuWfRaNNw/76Y3Jj8HNu0tHDlwVb6PvYlWPgzFbxiWTTuxfk2vMzh
t6UK2gnvb+PAbN6xelrXztTmTOLdIGjqWrqEJpVU5cQNmTKZNfeMWDugQhq26rzuUQI/MIFyA4pU
VOwah+zBPf3jFpef6zTxQCrM7vuH8HGdGGM+nu2+KPsU3G8jD1SA2QHN9k3UowF1BNeOOejSyLqP
Ah3nYxl6CN4QAk6tyNaAl5EZqMK+pC+Y93/ljFv9TFBOoLJ8l+joQnHfFxAuCTOVZ0taMedHh5F+
nBrMQZ6tZgMpSZXc6NvFnD4txoc/8svBPy2cD/v7DwAA


