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
