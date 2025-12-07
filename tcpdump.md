
# tcpdump
___
**Tcpdump** is a command-line utility that allows you to capture and analyze network traffic going through your system. It is often used to help troubleshoot network issues, as well as a security tool. Since it's command-line driven, it's ideal to use run in remote servers or devices where access to a GUI is not available.

```bash
# --list-interfaces
tcpdump -D
```

## Capturing Network Traffic
___
**Save `.pcap` to a file**
```bash
sudo tcpdump -i enp0s3 -n -w ~/Desktop/tcpdumps/capture.pcap
```

**Filtering Traffic**
```bash
# Filter traffic only on a specific host
sudo tcpdump -i enp0s3 -n host example.com

# Filter traffic either from X dst or to X src
sudo tcpdump -i enp0s3 -n dst <target>
sudo tcpdump -i enp0s3 -n src <target>

# Filter to a specific network
sudo tcpdump -i enp0s3 -n net 10.0.0.0/8
sudo tcpdump -i enp0s3 -n src net 10.0.0.0/8
sudo tcpdump -i enp0s3 -n dst net 10.0.0.0/8

# Filter by port
sudo tcpdump -i enp0s3 -n port 21
sudo tcpdump -i enp0s3 -n src port 21
sudo tcpdump -i enp0s3 -n dst port 21

# tcpdump supports conditions, e.g.:
sudo tcpdump -i enp0s3 -n src 10.0.2.10 and dst port 3389
sudo tcpdump -i enp0s3 -n 'src 10.0.2.10 and not port 22'
sudo tcpdump -i enp0s3 -n 'src 10.0.2.15 and dst 40.123.123.123 and not (port 443 or port 22)'
```



## Analyzing Network Traffic
___

```bash
tcpdump -r capture.pcap

# Count number of packets that match our filtering
tcpdump -r capture.pcap --count
# Return only X amount of packets
tcpdump -r capture.pcap -c 2

# Timestamps
-t    # completly suppress timestamp
-tt   # standard unix epoch time
-ttt  # in miliseconds (deltas between each packets)
-tttt # human readable format
```














___
**Tags:** #tcpdump #NetworkSecurity #NetworkAnalysis #pcap #Sniffing