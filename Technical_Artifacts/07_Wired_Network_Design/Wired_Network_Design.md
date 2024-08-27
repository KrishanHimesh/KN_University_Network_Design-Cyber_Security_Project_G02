# Wired Network Design

## Overview
The wired network design for KN University is focused on providing a robust, scalable, and secure infrastructure that supports the diverse needs of students, academic staff, and non-academic staff across four campuses: Melbourne, Sydney, Brisbane and Adelaide. This design aims to achieve high availability, redundancy and efficiency in all academic and administrative functions.
## Requirement Analysis
-	User Requirements: 
The network must accommodate many users on its connectivity network, as the users include students and academic and non-academic staff of the universities. Every user in the network will require connectivity to the internal resources (e.g., file servers and databases) and external resources (e.g., the internet).
-	Application Requirements: 
The network should accommodate bandwidth-intensive demands, including video conferencing, transfer of large files, research activities, and cloud computing.
-	Security Requirements: 
Security controls such as segmentation, access control and encryption should be implemented to secure the vital network data.


## Network Architecture
- Core Layer: 
The core network includes high-speed routers and switches installed within the campus's data centre. These devices serve as the network's core, offering inter-campus communication through VPN tunnels, high bandwidth, and minimal latency.
-	Distribution Layer: 
The Distribution layer collects traffic from the access layer switches and directs it to the core layer. It also acts as a switch that allows routing between VLANs and acts as a backup to guarantee the network is always on.
-	Access Layer: 
The Access layer links end devices such as workstations, printers, and IoT devices to the network via edge switches. It is designed to handle Power over Ethernet (PoE) for devices attached to the layer and is geared towards edge connectivity.

## Device Selection
-	Core Layer Devices: 
At the core layer, 2Gbps WAN throughput Cisco ISR 4451-X routers will ensure high inter-campus and data centre connections.
-	Distribution Layer Devices: 
The distribution layer is to be supported by Cisco Catalyst 9400-48U switches. They have enhancement features such as VLAN, QoS, and ACL to help control traffic and network security.
-	Access Layer Devices: 
Edge connectivity equipment to be utilised will be Cisco Catalyst 9300-48P switches. They are PoE-specific switches, a boon for devices like IP phones, security cameras and wireless access points.


## Cabling Infrastructure
-	Fiber Optic Backbone: 
Fibre optic links will connect the core and distribution layer between buildings and across campus.
-	Copper Cabling: 
Cat6a cables will connect access layer switches to end devices with up to 10 Gbps connectivity and will support PoE where required.

## Network Topology
-	Campus Layout: 
Every campus will have a structural hierarchy, with the core, distribution, and access layers. The core layer will link all campuses through a Virtual Private Network, while the distribution and access layer will handle internal campus traffic.
-	Redundancy and Failover: 
Redundancy will be achieved at the core and distribution layers through links and devices to eliminate a single point of failure in the network.
-	VLAN Segmentation: 
The VLANs will segment the network according to organisational entities (students, Admin staff, Lecturers) and services required (management, IoT devices, etc.). This segmentation enables high levels of security and makes the network's work smooth.

## Security Implementation
-	Access Control Lists (ACLs): 
ACLs will manage traffic between VLANs and limit access to critical resources at the distribution and core layer.
-	Network Segmentation: 
To minimize the risk of unauthorized access, the network will be segmented using VLANs to accommodate different user groups and services provided at different VLANS.
-	Firewalls: 
Firewalls will be positioned at the edge of the network to filter external threats and allow campus network users to access the internet securely.

## Implementation Plan
**Step 1:** Purchase and install core and distribution switches at each campus’s data centre.

**Step 2:** Installation of fibre optic cables to provide the backbone for core and distribution switches across the campuses.

**Step 3:** Position the access layer switches within the building while connecting them to the distribution layer. Also, use them to provide wired access to end devices.

**Step 4:** VLANs, ACLs, and routing protocols should be configured across all the network elements for the correct segmentation and security measures.

**Step 5:** Test and validate the network to ensure it achieved or exceeded the intended performance, redundancy and security standards.

## Wired Network Equipment by Campus 

![image](https://github.com/user-attachments/assets/af006ff2-a903-49ae-81b9-e450122f4a5f)

### Summary of Total Equipment
-	**Total Core Layer Routers (Cisco ISR 4451-X): 8**
-	**Total Distribution Layer Switches (Cisco Catalyst 9400-48U): 13**
-	**Total Access Layer Switches (Cisco Catalyst 9300-48P): 46**
-	**Total Firewalls (Cisco Firepower 2100 Series): 8**
### Key Considerations:
-	Core Layer: Both campuses utilize the core layer with two Cisco ISR 4451-X routers for redundancy and failover capability.
-	Distribution Layer: Distribution layer switches are Cisco Catalyst 9400-48U switches, of which each campus may contain two and above depending on its size and demand.
-	Access Layer: Each campus needs connectivity to the end devices on the various floors, and the Cisco Catalyst 9300-48P switches provide this.
-	Firewalls: There are several campuses, and to support and secure all the campuses, the Cisco Firepower 2100 series firewalls have been implemented


