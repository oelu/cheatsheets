# Openbsd

## Package Management

* `pkg_add <package name>` install package
* `pkg_del <package name>` remove package
* `pkg_info -Q` query for package

## Upgrades
* `syspatch` install base system patches
* `fw_update -a` install available firmware updates for all devices

### New Version upgrade

- Do an automatic system upgrade with `sysupgrade
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
