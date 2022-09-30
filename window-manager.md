`
```
xfconf-query -c xfwm4 -p /general/button_layout -n -t string -s "O|HMC"
xfconf-query -c xfwm4 -p /general/title_font -n -t string -s "Noto Sans Bold 10.5"

xfconf-query -c xfwm4 -p /general/snap_to_windows -n -t bool -s true

xfconf-query -c xfwm4 -p /general/scroll_workspaces -n -t bool -s false
xfconf-query -c xfwm4 -p /general/wrap_cycle -n -t bool -s false
xfconf-query -c xfwm4 -p /general/wrap_layout -n -t bool -s false
xfconf-query -c xfwm4 -p /general/wrap_windows -n -t bool -s false

xfconf-query -c xfwm4 -p /general/raise_with_any_button -n -t bool -s false

exit
```

