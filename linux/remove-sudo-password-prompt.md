### Remove password prompt for sudo
Want to remove the password prompt for sudo?

$ sudo visudo
username ALL=(ALL) NOPASSWD: ALL
