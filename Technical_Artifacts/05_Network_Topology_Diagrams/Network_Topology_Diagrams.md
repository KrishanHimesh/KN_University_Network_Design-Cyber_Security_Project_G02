# Network Topology Diagrams

## Overview
The network topology diagrams for KN University detail network components' physical and logical arrangements across its four campuses: Melbourne, Sydney, Brisbane, and Adelaide. Every campus has numerous floors, and every floor is divided into subnets and network devices. If we talk about the real-life requirements of a university, they will require more IP addresses, so based on that, subnets will be planned.
## 1. Physical Network Topology Diagram
This diagram shows the location of the network components, including the routers, switches, access points, servers and workstations on all floors of each campus building.
### Physical Network Topology Elements:
-	Routers: Integrate each floor’s LAN to the main WAN.
-	Switches: Distribute the network traffic at each area.
-	Access Points: Ensure that all campus buildings have Wi-Fi connectivity.
-	Servers: Host several university services and applications.
-	Firewalls: Safeguard the network from external threats.
-	Workstations: Used by students, faculties, and university staff.
-	Central WAN: Connects all campuses
-	Internet Gateway: A single high-speed internet connection that protects the access point with firewalls
-	Campus LANs: Every building within the campuses with floors linked by routers and switches

 ![image](https://github.com/user-attachments/assets/c7320e39-fcd4-499b-92b6-cebb14b22fcb)
 *Figure 1.1 Four Campuses Connect each other via Central WAN (Google Maps, 2024)*


### Melbourne Campus
The following screenshots visualised the Physical Network Topology using the Cisco Packet Tracer. All Campuses have similar floor layouts from level one to level three. The rest of the levels are similar to the floor layout of floor three. The following screenshot shows the first three floors of the Melbourne Campus.

 ![image](https://github.com/user-attachments/assets/f0e37bbe-10d1-4d84-9265-f75ea2e3ac53)
 *Figure 1.2 Melbourne Campus (Google Maps, 2024)*

#### Floor One (Lobby)

The demonstration of the Physical topology of the floor included the front desk, student support office, four administration offices, Intermediate Distribution Frame (IDF) and auditorium. The network layout can be identified if the Packet Tracer File. The purple colour shows the heat map of the wireless network coverage across floor one. 

 ![image](https://github.com/user-attachments/assets/6f701ff4-07a8-419a-b08f-37590786e5df)
 *Figure 1.3 Front desk and IDF*



![image](https://github.com/user-attachments/assets/168552fd-83ec-476e-a1fb-4dbbe867b3da)
*Figure 1.4 Floor One Physical Layout* 

#### Floor Two (Library and Entertainment area)

Floor two has the library, two Administration offices, the Main computer lab, the Entertainment area and the Main Distribution Frame. The following screenshots show the layout of Floor Two. 

 ![image](https://github.com/user-attachments/assets/41f6f1ae-2b76-4c1e-91b5-4fd9f2280e0d)
 *Figure 1.5 Administration Office*

 ![image](https://github.com/user-attachments/assets/573d6fd3-09a3-446d-82dd-657d115b8e84)
 *Figure 1.6 Main Distribution Frame*

 ![image](https://github.com/user-attachments/assets/7d6bdc61-8d68-482b-b7ca-5cbb4c5e493e)
 *Figure 1.7 Floor Two Layout*


#### Floor Three (Labs, offices and Lecture rooms)
Melbourne Campus has six floors. Floors three to six have the same layout as floor three. Floor three has an Intermediate Distribution Frame (IDF), Computer Labs and Lecture Rooms. The following Screenshot shows the floor layout and layout of the Lecture Rooms and Computer Labs. 

 ![image](https://github.com/user-attachments/assets/1c3a9b3e-bb3e-4ca2-8b12-326adac3f85b)
Figure 1.8 Physical Topology Inside a Computer Lab
 
Figure 1.9 Physical Topology inside a Lecture room
 
Figure 1.9 Intermediate Distribution Frame
 
Figure 1.10 Floor Three Physical Layout 

 
2. Logical Network Topology Diagram
This diagram shows the flow and structure of subnet and VLAN components of the network along with the IP addressing plan in the organization, firewall regulation and VPN network.
Logical Network Topology Elements:
•	Subnets: Defined individual subnets for each floor of each campus. Used larger subnets such as /22 /23 to accommodate many devices. 
•	VLAN: VLANs are used to segment network traffic. 
•	IP Address Schemes: IP address range for the devices.
•	Firewall Rules: Security measures to regulate communication in the network.
•	VPN Connections: Ensure safe connectivity to the university’s network from a remote environment.
•	WAN: The central network that interconnects all campuses and allows access to the Internet.
•	Data Flow: Logical path of transferring data between the campuses and the Internet.
•	Central WAN: Connects all campuses.
•	Internet Gateway: Access to outside networks or external communication which are protected by firewalls.
 
Figure 2.1 Logical Topology of the KN University


 
Figure 2.2 Logical Topology of Floor One
 
Figure 2.3 Logical Topology of Floor Two
 
Figure 2.4 Logical Topology of Floor Three
 
Figure 2.5 Logical Topology of Adelaide, Brisbane and Sydney campuses

These modified diagrams provide an overall understanding of the physical and logical topology of the networking structure for KN University. These larger subnets will make it easier for the university to handle large numbers of devices and users without disrupting the network stability. The diagrams give clear recommendations, procedures, and schedules for constructing, deploying, and sustaining the network to serve the university’s educational and administrative roles.
