# IP Addressing and Naming Scheme

## IP Addressing Scheme
The IP addressing and the subnetting required for security purposes and for the proper establishment of access control will be under the line of user communities. VLANs will also be an additional but internal subnet in a particular community. Moreover, an internet VPN tunnel between the four campuses will be developed to ensure secure communication between the four campuses: Melbourne, Sydney, Brisbane, and Adelaide. This setup enhances security in communication between the various campuses and provides easy access to some vital resources.

## Subnets
### User Community Subnets
![image](https://github.com/user-attachments/assets/e9e83359-c7cc-47ec-b5a1-e6651baae4bd)

### Common Network Services
![image](https://github.com/user-attachments/assets/c5acde20-d15a-441e-96ce-452c5664063e)

## VLAN Implementation
These will be further split into VLANs to increase the network's security level. Every user community will be assigned different VLANs for wireless and common devices.

### VLAN Configuration by User Community
![image](https://github.com/user-attachments/assets/28345f43-cc23-43e6-8227-54f0289e16be)

### VLAN Configuration by Common Services

![image](https://github.com/user-attachments/assets/37ee5eb6-04ac-440b-bbb0-27ed0f922c79)

## VPN Implementation

![image](https://github.com/user-attachments/assets/627e96b7-6cae-4d3f-bdaa-c8a8946b75ff)

## Access Control Implementation- Firewall Rules

![image](https://github.com/user-attachments/assets/03c901c4-e18f-452c-b8c2-e84f5085442c)

## Wi-Fi Access Points as Extenders

Access points (APs) can be configured to operate in a way that enhances their ability to act as range extenders to ensure full coverage of the university campuses. These APs can assign the same IP range for the user community so that devices do not have to change their IPs as they move around the campus, even floors. 

## Naming Scheme
To simplify network management and promote the practice of standardization, the naming convention will comprise the type of device, campus, floor number, and number. 

### Naming Convention
Format: [Campus]-[Floor]- [Device Type]- [(**Location Number). Device Number]

**Classroom, office or Lab number(Only for Workstations)


*Examples*
#### Routers
-	Melbourne Floor 1 Router: MEL-01-RTR-01
-	Sydney Floor 2 Router: SYD-02-RTR-01
-	Brisbane Floor 3 Router: BNE-03-RTR-01
-	Adelaide Floor 4 Router: ADL-04-RTR-01


#### Switches
-	Melbourne Floor 1 Switch: MEL-01-SW-01
-	Sydney Floor 2 Switch: SYD-02-SW-01
-	Brisbane Floor 3 Switch: BNE-03-SW-01
-	Adelaide Floor 4 Switch: ADL-04-SW-01



