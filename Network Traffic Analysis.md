___
`Network Traffic Analysis (NTA)` can be described as the act of examining network traffic to characterize common ports and protocols utilized, establish a baseline for our environment, monitor and respond to threats, and ensure the greatest possible insight into our organization's network.

___

# Common Traffic Analysis Tools

## tcpdump
```bash
# List Available Interfaces
sudo tcpdump -D

# Disable name resolution
sudo tcpdump -i eth0 -nn

# Display the Ethernet Header
sudo tcpdump -i eth0 -e

# Include ASCII and Hex Output
sudo tcpdump -i eth0 -X
```

**File Input / Output**
```bash
# Saving PCAP Output to a file
sudo tcpdump -i eth0 -w ~/output.pcap

# Reading Output from a file
sudo tcpdump -r ~/output.pcap
```

174.143.213.184