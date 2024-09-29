# Physical Network Demonstration
## Overview
KN University is a prestigious university in Australia with Melbourne, Sydney, Brisbane, and Adelaide campuses. The university offers undergraduate programs across four faculties. The schools include those in engineering, technology, law, and business. Every campus has teaching and administrative facilities that enhance education provision.
This artefact describes all the steps we followed in designing and implementing the prototype demonstration of the Physical network design. 

## Layout and Implementation Plan of the Physical network

Before implementing the Physical network Design, the following logical diagram has been developed in the Cisco Packet Tracer.
 
![image](https://github.com/user-attachments/assets/4f702d98-06fa-407e-b164-999ca6a6415c)

We plan to implement three VLANS, VLAN10, VLAN20, and VLAN52, as explained in the Technical Artefact “IP addressing and Naming Scheme”. We use a router, switch, access point, and three workstations for the physical design. After designing the logical diagram of the physical network, we selected the devices available from the network lab, as follows.


1.	Cisco 1941 Series Router (we selected the latest C921-P, but it does not support VLANs. Therefore, we used Cisco 1941 series.)
 
![image](https://github.com/user-attachments/assets/69d0b91f-d5fd-4cdd-8cfb-b9f412cf4bc9)


2.	Cisco Catalyst 3560-CX Series Switch

 
![image](https://github.com/user-attachments/assets/ec71d878-5ca3-4c50-b12c-412f0e185907)


3.	TP-Link Archer C24
            
![image](https://github.com/user-attachments/assets/519d6703-c39d-40fb-9505-1c43e61f3e1a)


4.	Two workstations have a wired connection and one with a wireless connection to demonstrate and test each VLAN.
 
![image](https://github.com/user-attachments/assets/16b42eeb-3fa2-441b-a560-0d4e47f8a784)


## Physical Network Design Implementation

The following image shows the setup of the physical network demonstration of the KN University network design.
 
![image](https://github.com/user-attachments/assets/312e30bc-1594-488e-bc5b-cc2114894a94)


After completing the physical setup, the devices were configured to create a cutting-edge, highly secure, highly available network. The next steps explain the step-by-step configuration of each device. 

## Configuring Devices
### Configuring router
Connect the router to the COM Port in the PC and use a terminal connecting application like PuTTY to connect to the Router configuration CLI. Enable the router and set the router's hostname as MEL-02-RTR-01 to comply with the naming convention scheme.
 
![image](https://github.com/user-attachments/assets/8c61c323-86af-45d1-ab93-bda4cb72548d)

#### 1.	Configure interfaces for VLANs
The next step is to configure sub-interfaces on the router for each VLAN. For the demonstration, we use the VLAN10, VLAN20 and VLAN52
1.	VLAN10 for Students
 
![image](https://github.com/user-attachments/assets/054c93c5-d9bb-4527-a0f4-b9bfa01b608b)

2.	VLAN20 for Academic Staff
 
![image](https://github.com/user-attachments/assets/f10bfded-132e-4405-af2d-4cbd97907588)

3.	VLAN52 for Network Management
 
![image](https://github.com/user-attachments/assets/6eeb7323-fb96-4af8-bd56-e3064f7302e1)

#### 2.	Configuring DHCP Pools
Then, the DHCP pools for each VLAN are configured, as shown in the screenshot below. We have used all subnet masks as /24 for all three subnets only for the demonstration. 
1.	VLAN10 – Students – 10.10.0.1/24
2.	VLAN20 – Academic Staff – 10.20.0.1/24
3.	VLAN52 – Network Management – 10.255.2.1/24
 
![image](https://github.com/user-attachments/assets/62adefcb-e3de-4bf7-bdda-84e40fd1baa2)

The Run ‘show ip dhcp pool’ command to verify that the DHCP configuration has been assigned properly. The following screenshot shows the configured DHCP configuration.
We haven’t excluded any IP addresses in this configuration. But we can assign a reserved IP address pool for each VLAN according to the future requirement of static IPs from each VLAN using the command,
`ip dhcp excluded-address [Starting IP] [Finish IP]`
		 

 
![image](https://github.com/user-attachments/assets/e9a65899-d1f3-42ad-a5d6-35decb35861a)

#### 3.	Configure NAT
Configure the Network Address Translation (NAT) on the Router for each interface to allow devices to access the Internet, as shown below.
 
![image](https://github.com/user-attachments/assets/551ea33b-af05-402e-806b-82d74f31a521)


#### 4.	Configure the IP route
Configure an IP route to allow internal devices to share a single public IP.
 
![image](https://github.com/user-attachments/assets/e18cc032-9247-42b5-90a4-3916513d64c2)

Testing the Internet access of the Router 
Then, test the router's internet connection by pinging the outside address from the router as below. Router internet access was successful, as shown in the screenshot. 
 
![image](https://github.com/user-attachments/assets/45fe5a61-464a-4475-b8f4-6da2e5ba2ad7)



#### 5.	Configuring the Router for Inter VLAN communication
1.	Router RIP
 
![image](https://github.com/user-attachments/assets/b1670600-af67-45c8-b8ba-c917cee4a623)

2.	Trunk port 13
 
![image](https://github.com/user-attachments/assets/fbbf33f4-98da-41c9-b1e1-df8779aab921)

After configuring the router, Test the inter-VLAN configuration as follows. *** Note: To test the configuration, server configuration should also be completed. ***
 
![image](https://github.com/user-attachments/assets/a1587b48-66ba-45d8-9e51-a77c1ae95cdf)

#### 6.	Save configuration
After completing the router configuration, save the configurations to load in the next reboot.

 ![image](https://github.com/user-attachments/assets/b6e4bde0-ced9-459d-a714-27539b846531)

 
### Switch Configure
#### 1.	Change hostname
Connect the Switch using the console cable to the terminal. The set the hostname of the switch as follows
 
![image](https://github.com/user-attachments/assets/b97ed363-32b5-4d5b-a936-337e99c35701)

#### 2.	Configuring VLANs
Configure the VLANs by giving them names and descriptions.
 
![image](https://github.com/user-attachments/assets/40a1c1f8-c350-41f0-83a7-240cef14ef74)

#### 3.	Assigning switch ports to VLANs
 
![image](https://github.com/user-attachments/assets/620acafb-a03c-4844-ae2a-ecbae7e73ebf)

#### 4.	Trunk Switch Ports
Trunk the switch port for Inter VLAN communication and communication between different network components.
 
![image](https://github.com/user-attachments/assets/8bb2c44e-3d1f-47d8-ac29-dca0b56f7648)

After completing the configurations, it was saved like the router to load from the next reboot. 
 
![image](https://github.com/user-attachments/assets/02411aee-bdba-4033-b12b-5e46b99baae5)


 
### Configure the Wireless Access Point
Wireless AP connected to the VLAN52, network management and completed the basic setting by setting the SSID as *KNU_WIFI* and adding a secured password. The following screenshot shows the IP address assigned for the wireless router before changing the TP-Link Archer C24 as a wireless access point. 
 
![image](https://github.com/user-attachments/assets/86a0a78b-da12-4b83-a42b-903c99af9715)

Then, from advanced, change the operation mode to the access point, as shown below. 
*The original plan was deviated as this router does not support RADIUS authentication. I planned to configure the RADIUS server to access the AP using the username and Password.*
 
![image](https://github.com/user-attachments/assets/db75def5-6004-45fb-88a5-b5d583df5c76)

### Testing
The following main aspects were tested to verify the KNU Prototype network.
1.	IP address assigned according to the VLAN
2.	Pinging to an external IP address to verify the Internet Connectivity
3.	Pinging internal IP address to verify the Inter VLAN connectivity.
The following image shows the port assigned to the testing. 
 
![image](https://github.com/user-attachments/assets/d0024e0a-e32d-45c6-b6d0-a08db635a4d4)

Testing was carried out on each device after setting up the ports for each device. The screenshots are taken from each device to check the IP address assigned and Pinging to google.com (external IP). 
 
#### Device from Student VLAN
IP address assigning and the connectivity to the student VLAN. The assigned IP address was 10.10.0.2 from VLAN10. 
 
![image](https://github.com/user-attachments/assets/32faeacb-9c37-49a0-b0b9-e5460659058c)

 
#### Device from Academic Staff VLAN
IP address assigning and the connectivity to the student VLAN. The assigned IP address was 10.20.0.2 from VLAN20. 
 
![image](https://github.com/user-attachments/assets/09dfa24c-c96d-4569-a9cf-ad461b78ff9b)

 
#### Device from Network Management VLAN
IP address assigning and the connectivity to the student VLAN. The assigned IP address was 10.255.2.3 from VLAN20. 
 
![image](https://github.com/user-attachments/assets/a12e0d9f-1b68-4bd9-8b7a-a898904e86e2)

## Implementing Security

After configuring and setting up the Network, the KNU Robust network security plan was implemented to secure the network and provide redundant connectivity. 
### 1.	Setting up password access for Router and Switch
Setting up the password access for the configuration terminal of the Switch and the Rouster as follows to restrict unauthorised access to the configuration of the devices. 
 
 ![image](https://github.com/user-attachments/assets/b377cfc8-696a-4a87-9760-001ec6bf167f)

### 2.	Implementing Security by shutting down unused interfaces
Shutting down the unused ports in the server to prevent any unauthorised devices from connecting to the network is as follows: 
 
![image](https://github.com/user-attachments/assets/d107bbdc-6970-4e20-b301-6f459623c726)

 ![image](https://github.com/user-attachments/assets/b2c73578-c92d-4db5-80a1-6824210e071b)


### 3.	Configuring Port Security for ports
Configure the port security to allow only one Mac address per port to prevent unauthorised devices from being connected to a port by unplugging the devices. 
 
![image](https://github.com/user-attachments/assets/b6c99f70-5852-41cd-a876-3319b6ea4dc7)


