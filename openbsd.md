# Openbsd

## Package Management

* `pkg_add <packagename>` install package
* `pkg_del <packagename>` remove package
* `pkg_info -Q` query for package

## Upgrades
* `syspatch` install base system patches
* `fw_update -a` install available firmware updates for all devices

## Services
* `rcctl <command> service` enable or disable a service, can also be used to start/stop services

## Mount USB Stick

* Show all storage devices with `sysctl hw.disknames`
* Show partition layout of USB disk `disklabel sd1`
* Mount the USB disk `mount_msdos /dev/sd1i /mnt/usbstick`
* Do your stuff
* Unmount `umount /mnt/usbstick`

## Packet Filter (pf)
* Manual enable pf `pfctl -e`
* Manual disable pf `pfctl -d`
* Load specific configuration file `pfctl -f /etc/pf.conf`
* Parse configuration file (check for errors) `pfctl -nf /etc/pf.conf`
* Enable pf at startup `rcctl enable pf`
* Show current pf rules `pfctl -s rules`
* Show current pf configuration and stats `pfctl -s all`
