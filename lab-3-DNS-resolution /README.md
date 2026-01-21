# Lab 3: DNS Resolution & Troubleshooting

## Goal
Simulate a network issue where connectivity works, but applications fail due to DNS problems. Verify, break, and restore DNS resolution using troubleshooting tools.

## Topology
- 1 Router (Default Gateway + DHCP Server)
- 1 Switch
- 2 PCs (DHCP Clients)
- 1 Server (DNS Server)
- LAN subnet: 192.168.1.0/24

## Tools Used
- Cisco Packet Tracer
- Commands (`ping`, `nslookup`)

## Steps Performed
1. Reused the existing branch office topology from Lab 2
2. Added a DNS server and configured it with a static IP
3. Created an A record on the DNS server for name resolution
4. Updated the DHCP configuration on the router to assign the DNS server `192.168.1.10` to clients 
5. Renewed DHCP leases on both PCs
6. Verified DNS resolution using `nslookup`
7. Verified connectivity using `ping`
8. Intentionally simulated a DNS failure by disabling the DNS service
9. Restored DNS service and re-verified name resolution and connectivity

## Troubleshooting 
- **Issue:** Could reach the gateway but could not access websites by name, `google.com`
- **Cause:** DNS service disabled
- **Resolution:** Re-enabled DNS service, verified A record, and confirmed resolution using `nslookup` and `ping`

## DNS Configuration
- DNS Server IP: `192.168.1.10`
- A Record:
  - Name: `google.com`
  - Type: A
  - Address: `192.168.1.1`


## Router DHCP Configuration for DNS Assignment
```txt
enable
configure terminal
ip dhcp pool BRANCH-LAN
no dns-server 8.8.8.8
dns-server 192.168.1.10
end



## Verification Commands
```txt
ipconfig /all
nslookup google.com
ping google.com
