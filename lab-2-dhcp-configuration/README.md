# Lab 2: DHCP Configuration for Branch Office Turn-Up

## Goal
Automatically assign IP addresses to multiple client PCs during a site turn-up and verify the DHCP lease.

## Topology
- 1 Router (DHCP Server + Default Gateway)
- 1 Switch
- 2 PCs (DHCP Clients)
- LAN subnet: 192.168.1.0/24
- Default gateway: 192.168.1.1

## Tools Used
- Cisco Packet Tracer

## Steps Performed
1. Opened the Lab 1 topology and reused the same branch office layout
2. Configured DHCP on the router (scope, default gateway, DNS)
3. Set both PCs (PC0 and PC1) to obtain IP addresses automatically via DHCP
4. Verified each PC received a valid lease using `ipconfig`
5. Verified connectivity by pinging the default gateway (`192.168.1.1`)
6. Simulated a DHCP failure by removing the DHCP pool
7. Restored DHCP configuration and re-verified connectivity

## Troubleshooting Example
- Issue: PCs failed to receive valid IP addresses and showed `169.254.x.x`
- Cause: DHCP scope removed or misconfigured on the router
- Resolution: Recreated the DHCP pool, renewed DHCP on both PCs, and re-tested connectivity

## Outcome
Successfully configured DHCP for multiple clients, validated automatic IP assignment, and practiced Day 1 troubleshooting for DHCP-related failures.

## DHCP Configuration (Router CLI)
```txt
enable
configure terminal
ip dhcp excluded-address 192.168.1.1

ip dhcp pool BRANCH-LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
exit
