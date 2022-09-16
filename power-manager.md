`
```
xfconf-query -c xfce4-power-manager \
  -p /xfce4-power-manager/lid-action-on-ac -n -t uint -s 1
xfconf-query -c xfce4-power-manager \
  -p /xfce4-power-manager/lid-action-on-battery -n -t uint -s 1
xfconf-query -c xfce4-power-manager \
  -p /xfce4-power-manager/logind-handle-lid-switch -n -t bool -s true
xfconf-query -c xfce4-power-manager \
  -p /xfce4-power-manager/show-panel-label -n -t int -s 0

exit
```

