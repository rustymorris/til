## Juniper Notes

The default login is user root with no password. A password must be set before commiting changes.


Get to the JunOS cli

`root@:RE:0% cli`

There are two CLI modes, operational and configuration.
Operational mode
`user@host>`

To enter configuration mode
```
user@host> configure
user@host#
```

Set the root password

`user@host# set system root-authentication plain-text-password`

Disable auto-image-upgrade

`user@host# delete chassis auto-image-upgrade`

Show configuration in operational mode

`user@host> show configuration | display set`



Restore factory defaults

`user@host# load factory-default`

Gracefully shutdown in operational mode

`user@host> request system halt`
