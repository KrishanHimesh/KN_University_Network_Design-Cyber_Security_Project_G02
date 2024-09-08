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
![image](https://github.com/user-attachments/assets/d8c07e1c-fb08-4839-ad6a-9bbac2597859)

Usage Categories. 
-	Casual: Low-priority, non-essential services like browsing, light streaming, and music.
-	Instructional: Critical academic services include video conferencing, online testing, and lecture streaming.
-	General: Administrative or high-volume services like file sharing, printing, and database access. as segmentation

![image](https://github.com/user-attachments/assets/87d692b0-7db2-482a-ab5a-dcbdccfd6800)


## Network Architecture
- Core Layer: 
The core network includes high-speed routers and switches installed within the campus's data centre. These devices serve as the network's core, offering inter-campus communication through VPN tunnels, high bandwidth, and minimal latency.
-	Distribution Layer: 
The Distribution layer collects traffic from the access layer switches and directs it to the core layer. It also acts as a switch that allows routing between VLANs and acts as a backup to guarantee the network is always on.
-	Access Layer: 
The Access layer links end devices such as workstations, printers, and IoT devices to the network via edge switches. It is designed to handle Power over Ethernet (PoE) for devices attached to the layer and is geared towards edge connectivity.

![image](https://github.com/user-attachments/assets/5abcf49f-d1b6-43db-945f-6a13f4caf361)


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

![image](https://github.com/user-attachments/assets/e067b3f0-1f85-4935-b82c-757dd1ce3318)


### Summary of Total Equipment
-	**Total Core Layer Routers (Cisco ISR 4451-X): 8**
-	**Total Distribution Layer Switches (Cisco Catalyst 9400-48U): 13**
-	**Total Access Layer Switches (Cisco Catalyst 9300-48P): 46**
-	**Total Firewalls (Cisco Firepower 2100 Series): 8**

### Overview of the Devices
#### 1.	Cisco ISR 4451-X Router 
![image](https://github.com/user-attachments/assets/0a49f249-84b2-4c98-9116-4a1cf42937fd)

![image](https://github.com/user-attachments/assets/63bc3693-00ce-42d8-8727-b5009a5ef5fb)

#### 2.	Cisco Catalyst 9400-LC-48U Switch
![image](https://github.com/user-attachments/assets/02223db6-47e7-49ef-9ce0-2dc820e96f33)

![image](https://github.com/user-attachments/assets/08e1d5f8-f445-4238-a400-276088cb4280)

#### 3.	Cisco Catalyst 9300-48P switch
![image](https://github.com/user-attachments/assets/ea6c00ec-4db1-480c-a93a-16c66e919ffa)

![image](https://github.com/user-attachments/assets/e15c9200-57cc-4978-9764-5b5c10c249e1)

#### 4.	Cisco Firepower 2100 Series Firewall Model 2140
![image](https://github.com/user-attachments/assets/1a570867-b243-4ddb-bfcf-68950d4f39c8)

![image](https://github.com/user-attachments/assets/0b57dd0c-707e-4f87-9a9c-3b6bb3ef3adc)


### Key Considerations:
-	Core Layer: Both campuses utilize the core layer with two Cisco ISR 4451-X routers for redundancy and failover capability.
-	Distribution Layer: Distribution layer switches are Cisco Catalyst 9400-48U switches, of which each campus may contain two and above depending on its size and demand.
-	Access Layer: Each campus needs connectivity to the end devices on the various floors, and the Cisco Catalyst 9300-48P switches provide this.
-	Firewalls: There are several campuses, and to support and secure all the campuses, the Cisco Firepower 2100 series firewalls have been implemented


## References

- Cisco 2021, Cisco Firepower 2100 Series Data Sheet, Viewed  03 September 2024, https://www.cisco.com/c/en/us/products/collateral/security/firepower-2100-series/datasheet-c78-742473.html
- Cisco 2024, Cisco 4451-X Integrated Services Router, Viewed 02 September 2024, https://www.cisco.com/c/en/us/support/routers/4451-x-integrated-services-router-isr/model.html#~tab-specs
- Cisco 2024, Cisco Catalyst 9300 Series Switches Data Sheet, Viewed 03 September 2024, https://www.cisco.com/c/en/us/products/collateral/switches/catalyst-9300-series-switches/nb-06-cat9300-ser-data-sheet-cte-en.html
- Cisco 2024, Cisco Catalyst 9400 Series Switch Line Cards Data Sheet, Viewed 02 September 2024, https://www.cisco.com/c/en/us/products/collateral/switches/catalyst-9400-series-switches/nb-06-cat9400-series-line-data-sheet-cte-en.html




