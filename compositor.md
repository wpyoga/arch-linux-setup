`
```
xfconf-query -c xfwm4 -p /general/unredirect_overlays -s true
xfconf-query -c xfwm4 -p /general/cycle_preview -s false
xfconf-query -c xfwm4 -p /general/show_popup_shadow -s false
xfconf-query -c xfwm4 -p /general/show_dock_shadow -s false
xfconf-query -c xfwm4 -p /general/show_frame_shadow -s false
xfconf-query -c xfwm4 -p /general/zoom_desktop -s false
xfconf-query -c xfwm4 -p /general/zoom_pointer -s false
xfconf-query -c xfwm4 -p /general/frame_opacity -s 100
xfconf-query -c xfwm4 -p /general/inactive_opacity -s 100
xfconf-query -c xfwm4 -p /general/move_opacity -s 100
xfconf-query -c xfwm4 -p /general/resize_opacity -s 100
xfconf-query -c xfwm4 -p /general/popup_opacity -s 100

exit
```
`

customize compositor settings
unfortunately we cannot disable the compositor, since it causes problems
even with the default theme

`/general/frame_opacity` is "Opacity of window decorations"
`/general/show_frame_shadow` is "Show shadows under regular windows"


