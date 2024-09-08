# Wireless Network Design

## Overview
The wireless network design for KN University is developed based on the top-down wireless network design method. The design must target the requirements of KN University’s four campuses in Melbourne, Sydney, Brisbane, and Adelaide and deliver a secure, reliable, scalable wireless network. It caters to academic, administrative, and guest users, making it easy to have connectivity on all the floors in every building on both campuses.

## Requirements Analysis

####	Coverage Requirements:
The wireless network should cover all indoor areas such as lecture rooms, classes, offices, libraries, and selected parts of outdoor spaces like the compound and fields.
####	User Requirements: 
The network must be capable of providing service in areas of high user density and where a user may have multiple devices (laptops, smartphones, tablets), all needing to access the network and providing high availability.
####	Application Requirements: 
Supporting high bandwidth applications such as video conferencing, video streaming, cloud computing, and online learning platforms requires support.
####	Security Requirements: 
The adopted security measures for the network are as follows, namely WPA3 encryption, 802. 1X authentication and VLAN segmentation from other university areas are used to enhance the security of these resources.

![image](https://github.com/user-attachments/assets/3350bc93-8680-40bd-a275-7cdc36f29898)


Usage Categories. 
-	Casual: Low-priority, non-essential services like browsing, light streaming, and music.
-	Instructional: Critical academic services include video conferencing, online testing, and lecture streaming.
-	General: Administrative or high-volume services like file sharing, printing, and database access. as segmentation

![image](https://github.com/user-attachments/assets/1196606f-dbae-4c43-b080-ce3ef220b75d)


## Network Architecture
####	Centralized Wireless Controller: 
Each campus will have a Cisco catalyst 9800-80 wireless controller, which manages all wireless access points in its network. These controllers have numerous functionalities like RF management, seamless roaming, and cutting-edge availability.
####	Access Points: 
The new Wireless Access Points that would be used are the Cisco Catalyst 9136 Wi-Fi 6E for low-density areas (perimeter and open areas) and high-density areas such as lecture halls and libraries. Cisco Catalyst 9124AXE Access Point will provide outdoor coverage.

####	VLAN Implementation: 
VLANs will be utilized to separate the network based on the identity of its users: students, faculty, staff, and guests. They will also be based on IoT devices and printing services.

![image](https://github.com/user-attachments/assets/484b4940-4ea7-4f8a-b82f-5e8d4442d071)


## Device Selection
####	Wireless Controllers: 
The selected wired and wireless controllers will be the Cisco Catalyst 9800-80 Wireless Controllers, able to support up to 8000 access points and a further 64000 clients.
####	Access Points:
Indoor coverage will be provided by Cisco Catalyst 9136 Wi-Fi 6E access points. These APs are also compatible with the latest Wi-Fi 6E standard, which delivers better throughput and density. Cisco Catalyst 9124AXE APs will be deployed outdoors as they resist weather conditions and provide sufficient coverage.

## Coverage and Capacity Planning
####	AP Placement: 
A site location survey will be conducted to ensure the best positioning of the APs. The survey will include the number of floors in buildings, the number of users in an area, and the availability of routes with restricted access. These APs will be installed typically to minimize interferences and to ensure adequate coverage.
####	High-Density Areas:
In zones where users are most densely located, like auditoriums and libraries, more access points will be installed so the bandwidth can be enough without conflict.
####	Power over Ethernet (PoE): 
All of the APs will be powered from PoE++ switches for easier installation and the standardization of power management.

### Heat Map of the Wireless Network
The following map of floor three explains the placement of the Access points to provide seamless coverage within the building. Other floors have the same coverage to provide users with highly available, seamless wireless network coverage throughout the university. 

![image](https://github.com/user-attachments/assets/e36754e4-48ec-4e0c-a613-8488dbd6c937)


## Security Implementation
####	Network Segmentation: 
VLANs will separate traffic flow between users (e.g., students, lecturers, staff) and services (e.g., guest access, smart devices). This segmentation increases security as data and access rights are enclosed and limited.
####	Authentication and Encryption: 
WPA3 encryption and 8021X authentication will make the network highly secure so as only to allow genuine user access to university resources. For guests, a different SSID will be created with captive portal authentication.
####	Access Control: 
To enhance security policies in the network, ACLs will be implemented on the wireless controllers and used to further enhance security policies according to user roles and device types.

## Implementation Plan
**Step 1:** Implement and set up the Cisco Catalyst 9800-80 Wireless Controllers at every campus’s main data centre.

**Step 2:** A survey of the areas that will accommodate the APs should be carried out based on the number of floors and user density of the intended campuses.

**Step 3:** Based on the survey results, deploy the Cisco Catalyst 9136 Wi-Fi 6E and 9124AXE Access Points to ensure proper coverage while ensuring optimisation of the APs.

**Step 4:** Organisation VLANs, SSIDs, and security policies on wireless controllers and APs, as well as implement correct segregation and secure access.

**Step 5:** Perform coverage, performance, and security tests on the established network. Depending on the result of the tests, rearrange or alter the placement and configurations of an AP.

## Wireless Network Equipment by Campus 

![image](https://github.com/user-attachments/assets/275327dd-6c81-48f0-811b-0b0096742e22)


### Summary of Total Equipment
-	**Total Wireless Controllers: 4**
-	**Total Low-Density Indoor APs (Cisco Catalyst 9136 Wi-Fi 6E): 67**
-	**Total High-Density Indoor APs (Cisco Catalyst 9136 Wi-Fi 6E): 12**
-	**Total Outdoor APs (Cisco Catalyst 9124AXE): 16**

### Overview of the Devices
#### 1.	Cisco Catalyst 9800-80 Wireless Controller
![image](https://github.com/user-attachments/assets/015d18f7-f679-4825-a5f7-7defdd0750bc)

![image](https://github.com/user-attachments/assets/0c6b18a3-8710-4969-bb8a-e425e8b982ef)

#### 2.	Cisco Catalyst 9136 Wi-Fi 6E Access Point
![image](https://github.com/user-attachments/assets/6509bee8-755f-4c3b-9ee9-880ac80a3069)

![image](https://github.com/user-attachments/assets/49ae91ee-b3d2-4d00-afd3-98bde456baa5)

#### 3.	Cisco Catalyst 9124AXE Access Point 
![image](https://github.com/user-attachments/assets/a735405b-d3fe-489b-adf1-929b2de3556c)

![image](https://github.com/user-attachments/assets/76053742-749b-49d7-a6fe-8bab37caa19c)

### Key Considerations:
-	Wi-Fi 6E Support: The Cisco Catalyst 9136 Series Access Points are in the new generation of the latest Access Points in the market that support Wi-Fi 6E, including the 6GHz band. This enhancement brings more spectrum, reduces congestion, and enhances performance, particularly in dense usage emplacements.
-	PoE++ (802. 3bt): The 9136 Series APs are PoE++ (802. 3bt) powered and deliver higher power levels needed by the multiple radios and processing of these enhanced APs.
-	Cisco Catalyst 9800-80 Controllers: These are primarily targeted for big-scale enterprises where flexibility, big data handling capacity, excellent I/O rates, and enhanced security are profound. These are especially useful where many APs and users will spread over several campuses.
-	Outdoor Coverage: The Cisco Catalyst 9124AXE APs are weather resistant and thus suitable for use outdoors, for instance, in yards, parking lots, and sporting fields.

## References
- Cisco 2022, Cisco Catalyst 9800-80 Wireless Controller Data Sheet, Viewed  03 September 2024, https://www.cisco.com/c/en/us/products/collateral/wireless/catalyst-9800-series-wireless-controllers/nb-06-cat9800-80-wirel-mod-data-sheet-ctp-en.html
- Cisco 2023, Cisco Catalyst 9124AX Series Access Points Data Sheet, Viewed 02 September 2024, https://www.cisco.com/c/en/us/products/collateral/wireless/catalyst-9100ax-access-points/nb-06-cat9124-ser-ap-ds-cte-en.html
- Cisco, 2023. Cisco Catalyst 9136 Series Access Points Data Sheet, Viewed 02 September 2024, https://www.cisco.com/c/en/us/products/collateral/wireless/catalyst-9100ax-access-points/nb-06-cat9136-access-point-ds-cte-en.html




