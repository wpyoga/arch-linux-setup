`
```
# set brightness keys options

xfconf-query -c xfce4-power-manager \
  -p /xfce4-power-manager/brightness-step-count -n -t uint -s 45
xfconf-query -c xfce4-power-manager \
  -p /xfce4-power-manager/brightness-exponential -n -t bool -s true

exit
```

