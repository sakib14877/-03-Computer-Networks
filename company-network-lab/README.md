# Company Network Lab (Cisco Packet Tracer)

A multi-department company network with a core switch,
6 VLANs, inter-VLAN routing, a server room and internet access.

## Topology
![topology](topology.png)

## What I implemented
- Layer 3 core switch (3560) with SVIs
- 6 department VLANs + server VLAN
- Trunk links to access switches (2960)
- Static routing to edge router and ISP
- DHCP, ACL, NAT (add when done)

## IP plan
| Department | VLAN | Subnet |
|---|---|---|
| HR | 10 | 192.168.10.0/24 |
| Finance | 20 | 192.168.20.0/24 |
| ... | ... | ... |

## How to run
Open company-network.pkt in Cisco Packet Tracer.

## Tested
- Inter-VLAN ping
- Server access
- Internet ping (8.8.8.8)
