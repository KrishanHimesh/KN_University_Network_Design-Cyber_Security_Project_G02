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


#### Access Points
-	Melbourne Floor 1 Access Point: MEL-01-AP-01
-	Sydney Floor 2 Access Point: SYD-02-AP-01
-	Brisbane Floor 3 Access Point: BNE-03-AP-01
-	Adelaide Floor 4 Access Point: ADL-04-AP-01

#### Servers
-	Melbourne Floor 1 Server: MEL-01-SVR-01
-	Sydney Floor 2 Server: SYD-02-SVR-01
-	Brisbane Floor 3 Server: BNE-03-SVR-01
-	Adelaide Floor 4 Server: ADL-04-SVR-01

#### Workstations
-	Melbourne Floor 1 Workstation: MEL-01-WS-01.01
-	Sydney Floor 2 Workstation: SYD-02-WS-2.01
-	Brisbane Floor 3 Workstation: BNE-03-WS-3.01
-	Adelaide Floor 4 Workstation: ADL-04-WS-4.01

#### IoT Devices
-	Melbourne Floor 1 IoT Device: MEL-01-IOT-01
-	Sydney Floor 2 IoT Device: SYD-02-IOT-01
-	Brisbane Floor 3 IoT Device: BNE-03-IOT-01
-	Adelaide Floor 4 IoT Device: ADL-04-IOT-01

#### Common Devices (Printers, Wireless Displays)
-	Melbourne Floor 1 Printer: MEL-01-PRN-01
-	Sydney Floor 2 Printer: SYD-02-PRN-01
-	Brisbane Floor 3 Printer: BNE-03-PRN-01
-	Adelaide Floor 4 Printer: ADL-04-PRN-01
-	Melbourne Floor 1 Wireless Display: MEL-01-WD-01
-	Sydney Floor 2 Wireless Display: SYD-02-WD-01
-	Brisbane Floor 3 Wireless Display: BNE-03-WD-01
-	Adelaide Floor 4 Wireless Display: ADL-04-WD-01


