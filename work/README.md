Cisco Enterprise Network — Cisco Packet Tracer

A CCNA-level enterprise network designed and implemented in Cisco Packet Tracer. This project demonstrates VLAN segmentation, 802.1Q trunking, LACP EtherChannel, and Router-on-a-Stick inter-VLAN routing.

📌 Project Overview

This project simulates a small enterprise network consisting of a router, multilayer switch, access switch, and multiple end devices.

The network is designed to provide logical network segmentation between different departments while maintaining communication between VLANs through router-based inter-VLAN routing.

🏗️ Network Topology




Network Components
Device	Role
Router0	Inter-VLAN Routing / Gateway
Multilayer-SW	Core/Distribution Switching
2960 Switch	Access Layer Switching
PC0–PC3	End Devices
🔧 Technologies Implemented
Cisco Packet Tracer
VLAN Segmentation
VLAN 10 — Sales
VLAN 20 — IT
802.1Q Trunking
LACP EtherChannel
Port-Channel 1
Router-on-a-Stick
IPv4 Addressing
Network Connectivity Testing
🌐 VLAN Configuration
VLAN	Department	Network
VLAN 10	Sales	192.168.10.0/24
VLAN 20	IT	192.168.20.0/24

The VLANs provide logical separation between different departments within the network.

🔗 EtherChannel Configuration

Two GigabitEthernet interfaces are bundled into a single logical Port-Channel using LACP.

EtherChannel Group: 1
Port-Channel: Po1
Protocol: LACP

Gi0/1 ─┐
       ├── Port-Channel 1
Gi0/2 ─┘
Verification
show etherchannel summary

Expected result:

Po1(SU)    LACP    Gi0/1(P) Gi0/2(P)

This confirms that both physical interfaces are successfully participating in the EtherChannel.

🔀 Trunking

802.1Q trunking is configured to carry multiple VLANs across the network.

Verified trunk interfaces include:

Port-channel 1
FastEthernet0/3
Verification
show interfaces trunk

The configuration shows VLANs 10 and 20 as active on the trunk.

🚦 Inter-VLAN Routing

Inter-VLAN communication is implemented using Router-on-a-Stick.

The router uses 802.1Q subinterfaces:

GigabitEthernet0/0/0.10
    192.168.10.1/24

GigabitEthernet0/0/0.20
    192.168.20.1/24

These subinterfaces provide the default gateway for their respective VLANs and allow communication between the Sales and IT networks.

Verification
show ip interface brief
show ip route
🧪 Network Verification

The network configuration was verified using Cisco IOS diagnostic commands.

VLAN Verification
show vlan brief




EtherChannel Verification
show etherchannel summary




Trunk Verification
show interfaces trunk




Routing Verification
show ip route




Connectivity Test

End-to-end connectivity can be tested using:

ping <destination-ip>



🎯 Learning Objectives

This project was developed to practice and demonstrate practical networking concepts including:

Designing a small enterprise network
Creating and managing VLANs
Configuring access and trunk ports
Implementing 802.1Q trunking
Configuring LACP EtherChannel
Implementing Router-on-a-Stick
Configuring IPv4 addressing
Verifying network configurations using Cisco IOS commands
Testing end-to-end network connectivity
🛠️ Tools Used
Cisco Packet Tracer
Cisco IOS CLI
📚 Key Verification Commands
show vlan brief
show interfaces trunk
show etherchannel summary
show ip interface brief
show ip route
ping <destination-ip>
👨‍💻 Project Status

Status: Completed

This project represents a practical CCNA networking implementation and is part of my networking laboratory and portfolio work.

Author

Sakib Khan Rony

CSE Student | Networking & Cybersecurity Enthusiast
