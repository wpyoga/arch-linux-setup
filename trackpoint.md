`
```
# workaround for trackpoint issue on newer thinkpads

sudo tee /etc/modprobe.d/psmouse-thinkpad.conf >/dev/null <<EOF
options psmouse proto=imps
EOF

# this is for faster trackpoint

sudo tee /etc/X11/xorg.conf.d/99-trackpoint.conf >/dev/null <<EOF
Section "InputClass"
    Identifier "TrackPoint"
    MatchProduct "PS/2 Synaptics TouchPad"
    Option "TransformationMatrix" "3.0 0 0 0 3.0 0 0 0 1"
EndSection
EOF

xfconf-query -c pointers -p /PS2_Synaptics_TouchPad/Acceleration -n -t double -s 10.0

exit
```


