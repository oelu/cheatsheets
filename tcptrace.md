# tcptrace

# General
Always use option `-n`, tcptrace will not attempt to resolve ip’s and port’s.

## Statistics

Generate overall statistic over file: 

    $ tcptrace -n -xtraffic dumpfile.pcap
    mod_traffic: characterizing traffic
    1 arg remaining, starting with ‘log2.pcap’
    Ostermann’s tcptrace -- version 6.6.7 -- Thu Nov  4, 2004

    863940 packets seen, 803460 TCP packets traced
    elapsed wallclock time: 0:00:05.594231, 154434 pkts/sec analyzed
    trace file elapsed time: 0:13:40.990202
    Dumping port statistics into file traffic_byport.dat
    Dumping overall statistics into file traffic_stats.dat
    Plotting performed at 15.000 second intervals

    $ cat traffic_stats.dat 

    Overall Statistics over 820 seconds (0:13:40.990202):
    515431885 ttl bytes sent, 628575.438 bytes/second
    511838068 ttl non-rexmit bytes sent, 624192.750 bytes/second
    3593817 ttl rexmit bytes sent, 4382.704 bytes/second
    803460 packets sent, 979.829 packets/second
    4593 connections opened, 5.601 conns/second
    3426 dupacks sent, 4.178 dupacks/second
    16471 rexmits sent, 20.087 rexmits/second
    average RTT: 62.548 msecs

