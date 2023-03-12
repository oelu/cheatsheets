# Fortigate Cheat-sheet

## Networking

Show network interface configuration:

    config system interface

Show all nics:

    diagnose hardware deviceinfo nic

Show all info for specific nic:

    diagnose hardware deviceinfo nic dmz

Execute ping:

    execute ping 8.8.8.8

Ping Options:

    execute ping-options view
    execute ping-options source 192.168.1.4

Show Session Table:

    diagnose sys session list

Traceroute:

    execute traceroute 8.8.8.8

Telnet:

    execute telnet targethost

## VDOMS

Change vdom:

    config vdom
    edit vdomname

## Performance

Overall performance:

    get system performance status

Top (use Shift+M for memory usage):

    get system performance top

## Proxy

Show console log: 

    execute log filter dump
    execute log filter category 0
    execute log filter field hostname www.google.ch
    execute log display

### SSL Inspection

Show possible diag commands:

    diagnose test application ssl 0

SSL Proxy Usage

    diagnose test application ssl 4

Show info per connection:

    diagnose test application ssl 44

### FSSO

Debug FSSO:

    diag debug enable
    diag debug authd fsso list
    diag debug authd fsso server-status
    diag debug authd fsso-summary

## Routing

Show routing table:

    get router info routing-table all

## Ipsec

Show ipsec tunnels:

    get ipsec tunnel list 

## Admin Interface

Set certificate for admin interface:

    config system global
    set admin-server-cert certname
    end
