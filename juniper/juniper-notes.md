## Juniper Notes

The default login is user root with no password. A password must be set before commiting changes.


Get to the JunOS cli

`root@:RE:0% cli`

There are two CLI modes, operational and configuration.
Operational mode prompt

`user@host>`

To enter configuration mode
```
user@host> configure
user@host#
```

**Set the root password**

`user@host# set system root-authentication plain-text-password`

Disable auto-image-upgrade to suppress the periodic console messages about auto-image-upgrade.

`user@host# delete chassis auto-image-upgrade`

Show configuration

`user@host> show configuration | display set`



Restore factory defaults

`user@host# load factory-default`

Gracefully shutdown in operational mode

`user@host> request system halt`
###
### Initial Config Requirements

- Hostname
- Management interface IP
- Static route for mgmt traffic
- Remote access (SSH/Telnet/J-Web)
- System time
- Login message (optional)
- Backup router (optional)
- Rescue configuration (optional)

**Set** the root password

`root# set system root-authentication plain-text-password`

**Hostname**

`root# set host-name CORE-SWITCH-1`

What is the management interface name?

`root# run show interfaces terse | match me`

The management interface name varies per platform.

**Management** Interface IP

```root# top edit interfaces
root# set me0 unit 0 family inet address 172.16.20.2/24
```

**Static** route
```
root# top edit routing-options
root# set static route 192.168.1.0/24 next-hop 172.16.20.1 no-readvertise
```

 The no-readvertise will not re-advertise the route into any other routing protocols.

**Rescue** configuration

Note being in operational mode.

`root> request system configuration rescue save | delete`

Use to save (or delete) a rescue configuration. Use `rollback rescue` from configuration mode to restore. Don't forget to `commit`.

**View** the rollback files.

`root# rollback ?`


**Enable SSH**
```
root# set system services ssh
root# run set cli idle-timeout 30
```

**Set the System Time**
```
root# set system time-zone America/New_York
root# run set date 201704010900.00
```

**Check the time**

`root# run show system uptime`

**System Login Message**

`root# set system login message "Access for authorized users only!!"`

**Backup router**

```
root# top edit routing-options
root# set backup-router 172.16.20.1 destination 192.168.1.0/24
```

The backup router has to be reachable on the same local subnet as the Juniper device.


**Other Tasks**

Create a local super-user account

```
root# set system login user fladmin class super-user
root# set system login user fladmin authentication plain-text-password
```
