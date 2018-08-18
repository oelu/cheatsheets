# NMAP

- `nmap -sn 10.0.0.0/24` ping sweep.

- `nmap -A -oA nmap $targetip` scan 1024 most common ports

- `nmap -v -p -sT $targetip` scan all ports with a full connect scan

## Nmap Scripts

- `locate *.nse | grep smb`

- `nmap -p 139,445 --script=$scriptname $targetip`

- the script parameter accepts wildcards
