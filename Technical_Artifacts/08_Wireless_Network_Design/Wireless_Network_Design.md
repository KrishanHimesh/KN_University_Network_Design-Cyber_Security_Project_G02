# Wireless Network Design

## Overview
The wireless network design for KN University is developed based on the top-down wireless network design method. The design must target the requirements of KN University’s four campuses in Melbourne, Sydney, Brisbane, and Adelaide and deliver a secure, reliable, scalable wireless network. It caters to academic, administrative, and guest users, making it easy to have connectivity on all the floors in every building on both campuses.

## Requirements Analysis

-	Coverage Requirements:
The wireless network should cover all indoor areas such as lecture rooms, classes, offices, libraries, and selected parts of outdoor spaces like the compound and fields.
-	User Requirements: 
The network must be capable of providing service in areas of high user density and where a user may have multiple devices (laptops, smartphones, tablets), all needing to access the network and providing high availability.
-	Application Requirements: 
Supporting high bandwidth applications such as video conferencing, video streaming, cloud computing, and online learning platforms requires support.
-	Security Requirements: 
The adopted security measures for the network are as follows, namely WPA3 encryption, 802. 1X authentication and VLAN segmentation from other university areas are used to enhance the security of these resources.

## Network Architecture
-	Centralized Wireless Controller: 
Each campus will have a Cisco catalyst 9800-80 wireless controller, which manages all wireless access points in its network. These controllers have numerous functionalities like RF management, seamless roaming, and cutting-edge availability.
-	Access Points: 
The new Wireless Access Points that would be used are the Cisco Catalyst 9136 Wi-Fi 6E for low-density areas (perimeter and open areas) and high-density areas such as lecture halls and libraries. Cisco Catalyst 9124AXE Access Point will provide outdoor coverage.

-	VLAN Implementation: 
VLANs will be utilized to separate the network based on the identity of its users: students, faculty, staff, and guests. They will also be based on IoT devices and printing services.

## Device Selection
-	Wireless Controllers: 
The selected wired and wireless controllers will be the Cisco Catalyst 9800-80 Wireless Controllers, able to support up to 8000 access points and a further 64000 clients.
-	Access Points:
Indoor coverage will be provided by Cisco Catalyst 9136 Wi-Fi 6E access points. These APs are also compatible with the latest Wi-Fi 6E standard, which delivers better throughput and density. Cisco Catalyst 9124AXE APs will be deployed outdoors as they resist weather conditions and provide sufficient coverage.

Coverage and Capacity Planning
•	AP Placement: 
A site location survey will be conducted to ensure the best positioning of the APs. The survey will include the number of floors in buildings, the number of users in an area, and the availability of routes with restricted access. These APs will be installed typically to minimize interferences and to ensure adequate coverage.
•	High-Density Areas:
 In zones where users are most densely located, like auditoriums and libraries, more access points will be installed so the bandwidth can be enough without conflict.
•	Power over Ethernet (PoE): 
All of the APs will be powered from PoE++ switches for easier installation and the standardization of power management.


Security Implementation
•	Network Segmentation: 
VLANs will separate traffic flow between users (e.g., students, lecturers, staff) and services (e.g., guest access, smart devices). This segmentation increases security as data and access rights are enclosed and limited.
•	Authentication and Encryption: 
WPA3 encryption and 8021X authentication will make the network highly secure so as only to allow genuine user access to university resources. For guests, a different SSID will be created with captive portal authentication.
•	Access Control: 
To enhance security policies in the network, ACLs will be implemented on the wireless controllers and used to further enhance security policies according to user roles and device types.
Implementation Plan
Step 1: Implement and set up the Cisco Catalyst 9800-80 Wireless Controllers at every campus’s main data centre.
Step 2: A survey of the areas that will accommodate the APs should be carried out based on the number of floors and user density of the intended campuses.
Step 3: Based on the survey results, deploy the Cisco Catalyst 9136 Wi-Fi 6E and 9124AXE Access Points to ensure proper coverage while ensuring optimisation of the APs.
Step 4: Organisation VLANs, SSIDs, and security policies on wireless controllers and APs, as well as implement correct segregation and secure access.
Step 5: Perform coverage, performance, and security tests on the established network. Depending on the result of the tests, rearrange or alter the placement and configurations of an AP.
