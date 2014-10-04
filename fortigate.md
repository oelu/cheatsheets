# Fortigate Cheat-sheet

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Fortigate Cheat-sheet](#fortigate-cheat-sheet)
  - [Networking](#networking)
  - [Firewall](#firewall)
  - [VDOMS](#vdoms)
  - [Performance](#performance)
  - [Proxy](#proxy)
    - [SSL Inspection](#ssl-inspection)
    - [FSSO](#fsso)
  - [Routing](#routing)
    - [OSPF](#ospf)
  - [Ipsec](#ipsec)
  - [Debug Flow](#debug-flow)
  - [Admin Interface](#admin-interface)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

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

## Firewall

Show some statistics:

    firewall statistic show

Show session table:

    sys session full-stat

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

### OSPF

Neighbor status (neighbours have state up/down):

    get router info ospf neighbor all

Delete all OSPF entries:

    excecute router clear ospf process

Enable debug output: 

    diagnose ip router ospf all enable
    diagnose ipo router ospf level info

Get Router Status: 

    get router info ospf status

Sniff for OSPF packets: 

    diagnose sniffer packet any ‘proto 89’ 4

Debug OSPF: 

    dignose ip router ospf all enable
    diagnose ip router ospf level info
    diagnose debug enable

## Ipsec

Show ipsec tunnels:

    get ipsec tunnel list 

Troubleshoot VPN connections:

    diag debug application ike -1
    diagnose vpn ike log-filter clear
    diagnose vpn ike log-filter dst-addr 1.2.3.4
    diagnose debug app ike 255
    diagnose debug enable

## Debug Flow

Debug traffic flow through the fortigate: 

    diagnose debug enable
    diagnose debug flow show console enable
    diagnose debug flow filter add 10.10.0.1
    diagnose debug flow trace start 100

## Admin Interface

Set certificate for admin interface:

    config system global
    set admin-server-cert certname
    end
