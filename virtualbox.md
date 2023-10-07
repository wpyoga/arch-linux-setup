`
```

yay -Sy virtualbox virtualbox-host-modules-arch virtualbox-guest-iso virtualbox-unattended-templates linux-headers linux

# suppress unnecessary messages
VBoxManage setextradata global GUI/SuppressMessages confirmGoingFullscreen,remindAboutMouseIntegration,remindAboutAutoCapture

exit
```


