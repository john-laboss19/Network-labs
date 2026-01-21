# Lab 1: Branch Office Network Turn-Up

## Objective
Simulate a branch office network and perform a Day 1 network turn-up, including IP configuration and connectivity testing.

## Topology
- 2 PCs
- 1 Switch
- 1 Router
- LAN subnet: 192.168.1.0/24

## Tools Used
- Cisco Packet Tracer

## Steps Performed
1. Created a basic branch office network topology in Cisco Packet Tracer
2. Assigned static IP address information to the PC
3. Configured the router interface to act as the default gateway
4. Verified network connectivity using ping to the default gateway
5. Intentionally misconfigured IP settings to simulate a connectivity issue
6. Troubleshot and corrected the misconfiguration
7. Re-verified successful connectivity using ping

## Troubleshooting
- Issue: PC could not reach the default gateway
- Cause: Incorrect subnet mask and default gateway configuration
- Resolution: Corrected the subnet mask and default gateway IP on the PC and re-tested connectivity

## Outcome
Successfully brought a simulated branch office network online, verified connectivity, and documented the Day 1 troubleshooting process.

## Router Configuration (CLI)
```txt
enable
configure terminal
interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
