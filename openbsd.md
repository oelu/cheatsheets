# Openbsd

## Package Management

* `pkg_add <package name>` install package
* `pkg_del <package name>` remove package
* `pkg_info -Q` query for package
* `pkg_info -mz | tee packages` list all manually installed packages 
* `pkg_add -l packages` install the set of packages from provided file

### Ports
* Download ports tree via csv: `cd /usr; doas cvs -qd anoncvs@ftp.hostserver.de:/cvs checkout -rOPENBSD_6_9 -P ports`
* Add user foo to wsrc group: `user mod -G wsrc foo`
* Change group ownership of ports to usergroup wsrc: `chgrp wsrc ports; chmod 775 ports`
* Update the ports tree: `cvs -q up -Pd -rOPENBSD_6_9`
* Search for a package in ports tree `cd /usr/ports; make search key=firefox`
* Install package from ports `cd /usr/ports/www/mozilla-firefox; make install`

### Upgrades
* `syspatch` install base system patches
* `fw_update -a` install available firmware updates for all devices

### New Version upgrade

- Do an automatic system upgrade with `sysupgrade`
    - The system will reboot automatically
- After the reboot do a `syspatch`, `pkg_add -u` and a `sysmerge -d`

## Services
* `rcctl <command> service` enable or disable a service, can also be used to start/stop services

## Mount USB Stick

* Show all storage devices with `sysctl hw.disknames`
* Show partition layout of USB disk `disklabel sd1`
* Mount the USB disk `mount_msdos /dev/sd1i /mnt/usbstick`
* Do your stuff
* Unmount `umount /mnt/usbstick`

## Power Management

- Use `apm` to show current power usage
- Set CPU performance to high `apm -H`
- Put the computer to suspend with `zzz`
- Put the computer to hibernate with `ZZZ`

### Enable screen lock for suspend / hibernae 
- APM executes the script `/etc/apm/suspend` or `/etc/apm/hibernate` before going into suspend or hibernate. 

- Create a file with the following content (replace <username> with your actual username):
```
#!/bin/sh
doas -u <username> env DISPLAY=:0 XAUTHORITY=/home/<username>/.Xauthority mate-screensaver-command -a &
```
- Make it executable with `chmod +x /etc/apm/suspend`

## Packet Filter (pf)
* Manual enable pf `pfctl -e`
* Manual disable pf `pfctl -d`
* Load specific configuration file `pfctl -f /etc/pf.conf`
* Parse configuration file (check for errors) `pfctl -nf /etc/pf.conf`
* Enable pf at start up `rcctl enable pf`
* Show current pf rules `pfctl -s rules`
* Show current pf configuration and stats `pfctl -s all`
* Test new rules `pfctl -ef <pf.conf>; sleep 15; pfctl -d`

### Example configuration for single-homed system
```
ethernet_if = "vio0"
icmp_types="echoreq"

block in log

antispoof quick for $ethernet_if

set skip on lo0
pass out on $ethernet_if from any to any 
pass in on $ethernet_if inet proto tcp to any port { 22 80 443 }
pass in inet proto icmp all icmp-type $icmp_types 
```
