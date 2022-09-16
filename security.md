`
```
# the defaults may be okay for a server, but too strict for a laptop
# https://wiki.archlinux.org/title/Security#Lock_out_user_after_three_failed_login_attempts
# https://bugs.archlinux.org/task/67644

sudo sed -i /etc/security/faillock.conf -e 's,^ *# *deny *=.*,deny = 0,' 

exit
```

