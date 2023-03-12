# Fortigate Cheat-sheet

## Networking

Show network interface configuration:

    config system interface

Execute ping:

    execute ping 8.8.8.8

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


## Routing

Show routing table:

    get router info routing-table all

## Ipsec

Show ipsec tunnels:

   get ipsec tunnel list 
