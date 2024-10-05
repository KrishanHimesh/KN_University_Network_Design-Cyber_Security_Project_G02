# Prototype Design and Implementation

## Introduction
This artefact synthesises the KN University network prototype demonstration plan's design and implementation plan. The goal is to combine physical network infrastructure, AD function, IoT connectivity, and web page services. The working prototype will implement a multiple-access University Network in a half-physical and half-cloud environment, emphasising role-based access control, web hosting security, and IoT.

## Artefact Summaries

### 1.	Physical Network Demonstration
This demonstration describes the creation of a physical layer network for KN University utilizing Cisco equipment (Cisco 1941 Router, Cisco Catalyst 3560 Switch, and TP-Link Archer C24 Access Point) for VLAN for students, academic faculty, and network administrators. The network configuration overlay sets VLANs, DHCP, and Network Address Translation (NAT). Other measures, which include facility security and shutdown on unused ports, were also used to improve security.
Key Features:
#### 1.	VLANs: 
For instance, VLAN10 is identified for students, VLAN20 for academic staff, and VLAN52 for network management.
#### 2.	Router Configuration: 
These are routing between VLANs, Dynamic Host Configuration Protocol (DHCP) and Network Address Translation (NAT).
#### 3.	Switch Configuration: 
The distribution of VLAN to the switch ports and the trunk ports.
#### 4.	Wireless Access Point: 
Allocated to VLAN52, overseeing the wireless network for network administration.




### 2.	AD Configuration and Demonstration
This demonstration shows how to structure Active Directory or AD using Oracle VirtualBox in a Windows Server 2022 setting. It implements the Role Based Access Control (RBAC) to control the university’s users, which include students and non-academic staff. Some best practices that were shown included policies for access control, installing applications, and rules for controlling network traffic, such as banning access to Facebook.
Key Features:
#### 1.	RBAC Implementation: 
Applied to access information regarding a user based on the roles defining the user (Students, Academic Staff, Non-Academic Staff).
#### 2.	Active Directory Setup: 
An active directory is implemented with different OUs for different user groups.
#### 3.	PfSense Firewall: 
Assigned to use the RADIUS for authentication and VLAN options for the corresponding user type.
#### 4.	Group Policies: 
Like enforcements at the operating system level, this includes application install policies, resource access policies, and firewall policies.
 
### 3.	IoT Demonstration
This artefact explains the implementation of the Internet of Things for monitoring temperature and humidity in real-time using Node-RED. Sensors are connected with Azure IoT Hub to capture, monitor and analyse information presented on a dashboard. Especially when temperature or humidity exceeds some predefined values, the system notifies the users, and the information is collected in the cloud for further evaluation.
Key Features:
#### 1.	IoT Sensors: 
Temperature and Relative Humidity measuring.
#### 2.	Node-RED Setup: 
It facilitates data communication and is also connected to Azure IoT Hub.
#### 3.	Dashboard: 
Shows operational data in integrated gauge meters and line graphs.
#### 4.	Alerts: 
It has a temperature and humidity alert notification system.

### 4.	Web Server Demonstration
This artefact provides documentation of Azure Virtual Machine hosting a web server using XAMPP for hosting Moodle at KN University. The web server enables students to enter their accounts and see academic scores while the personnel can modify many records. Communication between the components of the system uses SSL, which is accessed by firewalls and authorization based on roles, respectively.
Key Features:
#### 1.	Azure VM: 
They hosted the Moodle system with the help of XAMPP for PHP and MySQL.
#### 2.	Web Application: 
The marks are viewable to students, while records are modifiable to the staff.
#### 3.	Security: 
The options included are SSL for communication and an IP access list.

## Implementation Plan
The system will be fully integrated into the prototype, combining all the components discussed in the artefacts above. The following steps outline the implementation phases:

### 1.	Physical Network Setup:
-	The Physical Network Demonstration artefact dictates the configuration of the physical devices: router, switch, and access point.
-	Build VLANs and the ability to test the routing between VLANs and perform the necessary VLAN troubleshooting.
-	Check connectivity, port protection, and other types of restraints from the network.

### 2.	Active Directory Configuration:
-	Configured Active Directory on the Windows Server VM.
-	Develop subgroups of students, academic and non-academic members.
-	Set up a firewall to enable different groups of computers to be controlled, and generally set up AFL rules to prevent traffic.

### 3.	IoT Integration:
-	Introduction of Node-RED environment, connection with Azure IoT Hub.
-	Plug the IoT sensors for temperature and humidity.
-	Grab the direction of actual data that clients would see it on a dashboard and set alerts.

### 4.	Web Server Setup:
-	Host Moodle of KN University on an Azure VM with XAMPP.
-	Defined positions of students and staff of the university while defining the access level as per the artefact provided.
-	Issues of SSL enablement and proper firewall installation should be tackled to enhance security.

 
## Demonstration Plan
The demonstration will cover the following components:

### 1.	Physical Network Demonstration:
-	Explain how the VLAN setup works and the configuration of the devices.
-	Demonstrate inter-VLAN communication, DHCP server and internet connectivity.
-	For example, substantiate the security benefits, such as portal security, and cover points like disabling the unused ports.

### 2.	Active Directory and Access Control:
-	Explain how to log in for students and academic staff: show the implementation of RBAC.
-	Use the group policies to block program installation and control locality to group resources.
-	An example using PfSense is to demonstrate that new firewall rules are filtering traffic flow, such as Facebook access.

### 3.	IoT Dashboard and Alerts:
-	Introduce the real-time graphical display of temperature and humidity measured by sensors.
-	Using threshold triggers of the sensor data.
-	Explain how they send data to the Azure IoT for processing.

### 4.	Web Server and Moodle Platform:
-	Explain the process of student/staff login.
-	Explain how students can see marks and how staff can change them.
-	Memorably display SSL-secured communication and Firewall protection.

This will be a live demonstration showing how the network, security policies, IoT functionalities and web application services work in a robust security network at KN University.

