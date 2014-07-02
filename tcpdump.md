# TCPDUMP

Save whole dump to file:

    tcpdump -w file.cap -s 0

Show full output of packet: 
    
    tcpdump -A

Show only `SYN` and `FIN`

    tcpdump -i any -n ‘tcp[tcpflags] & (tcp-syn|tcp-fin) != 0 ‘

