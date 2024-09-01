# Project Report

##	Introduction

In today’s academic environment, all educational and administrative processes are based on digital connectivity, and a high-quality, scalable, and reliable network infrastructure is a crucial factor. The KN University network design project is a large-scale project that will design a modern multi-campus network for KN University as a prestigious educational establishment. The work includes the development of a complex network topology encompassing all campuses of KN University in Melbourne, Sydney, Brisbane, and Adelaide, which are mainly distinct with different infrastructure and demands.

 ![image](https://github.com/user-attachments/assets/93b36a78-7310-45e5-815c-11ee27e9ae5a)

*Figure 1.1 KN University (DaLLE, 2024)*

The project's main objective is to build a highly available, redundant, secure, high-standard network for KN University. It can meet the university’s current operational requirements and potentially address future requirements. It covers the wired and the wireless infrastructure and integrates with the latest network technology to enhance robust performance, security and scalability. 

In addition to the basic computer networking components, the project integrates IoT devices as an essential component that increases client experiences, monitors and controls environment standards, and strengthens security. Cloud computing capacities are also embedded in the design to provide flexible and scalable resources that support the university’s academic and organisational activities.

The project employs a top-down network design approach, which involves analysing the organisation's requirements to develop the network design from the top of the OSI layer and then implement it. There are three layers in the hierarchical structure of the network: Core layer, Distribution Layer and Access Layer. The core layer connects all campuses via two ISP connections, the distribution layer contains redundant switches for high availability, and the access layer connects the end devices. The logical topology has been designed to comprise twin distribution switches to accommodate redundant switches and minimize unavailability due to faults in the existing equipment. 

Security is one of the main features of this design, and it is supported by VLAN segmentation, WPA3 encryption, and the 802. 1X authentication is used to ensure the security of resources in a university. Network design also contains a comprehensive risk assessment to identify and mitigate potential threats.

This document is the final report on the network design for the KN University project and includes information concerning the design process, generated technical artefacts, and outcomes achieved. It is intended for all the stakeholders, internal partners such as the university’s IT department, project mentors, and external evaluators, who would get comprehensive information about the approach used to design the network to align it with the strategies of KN University and the university’s mission to provide top-notch education and research options.


##	System Overview

KN University network design project involves designing and deploying a high-performance network system for KN University, which has four campuses: Melbourne, Sydney, Brisbane and Adelaide. This project aims to solve the problem of designing a high-standard network that caters to students, lecturers, other employees, and visitors and is highly available, scalable, and secure.

### 2.1	Network Topology Diagrams
Network topology diagrams offer the visualisation of the general structure of the network by indicating how certain network elements are logically connected and interact with each other to create a working KN University Network. The diagrams include physical and logical topologies with the building layouts of campuses. 

####	Physical Topology: 

Illustrates physical mapping of the complete network, including the physical location of four campuses (Fig 2.1.1), floor plans, and the devices, including routers, switches and access points across the campuses. This diagram also shows where devices are physically located and the redundancy built into the network to achieve high availability.

 ![image](https://github.com/user-attachments/assets/92458a4a-232b-4fe8-9159-011931443675)

*Figure 2.1.1 Physical Topology Across Campuses (Google Maps, 2024)*

####	Logical Topology: 

Logical topology (Figure 2.1.2) visualises all the logical connections within the KN University network using layers, such as the Core, Distribution, and Access layers. It illustrates all the connections of the network devices and end nodes. The logical topology assists in understanding the flow and the regulation of data across different network sections.

 ![image](https://github.com/user-attachments/assets/cce18537-d42e-49c0-a286-57bd29104b3d)

*Figure 2.1.2 Logical topology of KN University*

These diagrams are important for the identification of the structure of the network and are described in detail in the [Network Topology Diagrams](https://github.com/KrishanHimesh/KN_University_Network_Design-Cyber_Security_Project_G02/blob/main/Technical_Artifacts/05_Network_Topology_Diagrams/Network_Topology_Diagrams.md) technical artefact.

### 2.2	Wired Network Design 
The wired network infrastructure forms the main framework and the backbone of the university’s network, providing reliable, high-speed connectivity across all campuses. The design follows a hierarchical structure consisting of core, distribution, and access layers. 
####	Core Layer: 

The Core Layer is more centralised, and all the campuses are connected through two high-speed ISP links to ensure availability. It is designed to support a high traffic volume and ensure that the network always has the necessary redundancy to ensure the continuity of the network operations. Core Routers are equipped with two power sources and have redundant connection links to minimize a single failure point.

####	Distribution Layer: 

Distribution switches are installed on every campus to connect with the core layer routers. Two distribution switches are shown in the Logical Topology Diagram to achieve redundancy and availability. These switches aggregate traffic from the access layer and control the routing between VLANs and users.


####	Access Layer: 

The access layer contains switches that connect to the end devices, such as computers, printers, and servers. The access layer switches are installed on every floor to provide complete coverage and functionality.

The wired network design ensures that the network infrastructure supports the current demands and is capable of scalability to accommodate the institution's future growth. Additional information on the wired network design plan and the specific switch type and placement is provided in the [Wired Network Design](https://github.com/KrishanHimesh/KN_University_Network_Design-Cyber_Security_Project_G02/blob/main/Technical_Artifacts/07_Wired_Network_Design/Wired_Network_Design.md) technical artefact.

### 2.3	Wireless Network Design
The overall design of the wireless network must reflect the need for mobility and connectivity across all the campuses. The design leverages the latest Wi-Fi 6E technology to provide high-speed, high-density wireless access.

####	Access Points (APs): 

Cisco Catalyst 9136 Wi-Fi 6E Access Points are installed across the campuses to provide maximum coverage. These APs are designed to handle high-user density areas such as lecture halls and libraries and are created to deliver high performance irrespective of the higher demand. 

####	Wireless Controllers:

Centralized Cisco Catalyst 9800-80 Wireless Controllers control the wireless access points, which offer functionalities like RF Management, Mobility, and Security. It is crucial to have these controllers to maintain the integrity and performance of the wireless network.

####	VLAN Segmentation: 

The wireless network is segmented into multiple VLANs according to users such as students, academic staff, Non-academic staff and guests, and services such as IoT devices and printers. This segmentation helps improve security within the organisation and ensures that every user group is granted permissions according to the access control policy. 

The document includes the precise assessment of the access point location, VLAN structure, and security measures. The technical artefact of [Wireless Network Design](https://github.com/KrishanHimesh/KN_University_Network_Design-Cyber_Security_Project_G02/blob/main/Technical_Artifacts/08_Wireless_Network_Design/Wireless_Network_Design.md) shows all the design details. 

### 2.4	IP Addressing and Naming Scheme
KN University IP addressing and naming plans offer all campuses a logical and efficient network resource management strategy. The scheme is based on user communities, and specific subnets are designated for students, academic staff, non-academic staff and guests. This segmentation not only improves security but also facilitates network management and troubleshooting.

####	User Community Subnets: 
The subnets are assigned for each user community to enhance the traffic flows between the various subnets, which are well controlled and managed.
####	VLAN Segmentation: 
VLANs are used to extend the physical segmentation of the network, with certain VLAN numbers reserved for specific types of devices, such as workstations, VoIP phones, wireless devices, etc.
####	Naming Convention: 
Network devices are assigned consistently using this naming convention: [campus]-[floor]-[device type]-[device number] (e.g., MEL-01-RTR-01: Melbourne campus, Floor 1, Router 1).
More details about the IP addressing and naming scheme and the detailed subnetting information and examples can be obtained from the ‘group02-ip-addressing-and-naming-scheme’ technical artefact.

### 2.5	Network Security Plan
A network security plan for KN University is intended to safeguard the university's computerized framework, delicate information, and client protection while guaranteeing the consistent activity of academic and administrative functions.

 ![image](https://github.com/user-attachments/assets/9f297a49-1c32-41ff-9784-58025eeb9c3a)

*Figure 3.5.1 Network Security Plan of KN University*
•	Firewalls: 
At KN University, firewalls erect a wall between trustworthy internal networks and untrusted external ones to guard against unwanted access and online threats. These can be internal firewalls that divide and guard critical network sections or perimeter firewalls that guard the network's edge. In addition, this KN University network has two firewalls, i.e., a physical firewall and a cloud firewall.
•	IDPS: 
Intrusion Detection and Prevention Systems (IDPS) notify university administrators of potentially dangerous activity and take automated measures to reduce them by identifying and stopping them within a network or system. They can be host-based, which concentrates on a single device, or network-based, which tracks activity throughout the network.
•	VPN: 
A virtual private network (VPN) encrypts all university data as it is being transmitted to guarantee its confidentiality and allow for safe remote access to a network. VPNs is used to securely link numerous networks together (Site-to-Site) or to enable remote access to a private network for a single user (Client-to-Site). 
•	SIEM: 
Security Information and Event Management (SIEM) offers ongoing examination and response to security events by joining log management, event connection, and incident response. By giving concentrated permeability and working with ideal identification and reaction to potential dangers, the network security of KN University has moved along.
•	Encryption: 
Encryption like AES-256 is utilized, which gives strong areas of strength against cyber dangers, guaranteeing the secrecy and security of information sent over conceivably uncertain networks. Besides, HTTPS is likewise utilized for the security of a network.

2.6	Cloud Integration Plan
A Cloud Integration Plan for KN University Network guarantees consistent communication and interoperability between on-premises frameworks and cloud administrations to improve operations, versatility, and flexibility.
 Figure 3.6.1 Network Security Plan of KN University

•	Cloud Service Provider: 
Various providers like Azure Cloud, IBM Cloud, and Google Cloud offer cloud services. For this project, Azure Cloud will be used for both demonstration and other purposes.
•	Cloud Integration Strategy: 
The Hybrid Cloud Model consolidates on-premises infrastructure with public cloud administrations to establish a unified environment, upgrading data portability, disaster recuperation, and consistency. A Cloud Gateway works with a secure network between on-premises networks and cloud benefits, overseeing and safeguarding the data of KN University. API is utilized as a concentrated gateway for controlling programming interface demands, executing safety measures, and handling versioning, with consistent checking and documentation to guarantee effective reconciliation. 
•	Security and Consistency: 
User authentication is used to enhance security with multi-factor authentication (MFA) for universities. Using Role-Based Access Control (RBAC) and Least Privilege, access control policies define and enforce user access. IAM roles are assigned based on job functions to minimize unauthorized access, while directory services integration manages identities across environments. Data is encrypted both in transit (using TLS) and at rest with robust encryption methods, with key management systems (KMS) overseeing encryption key handling. Data masking reduces exposure risk while maintaining usability.
•	Backup and Redundancy: 
For KN University, maintaining data backups protects against loss from deletion, corruption, or system failures by using automated plans and cloud storage. As per the design, there is only one backup on this network. Redundant systems guarantee continuous operation, while high accessibility arrangements like clustering decrease downtime. Regional redundancy shields against site-explicit issues by storing backups and systems in different geographic areas.

2.7	IoT Integration Plan
The IoT Integration Plan at KN College is fixated on deploying smart gadgets, including shrewd locks and natural sensors, to upgrade security and procedures on campus. To increment in general efficiency and client experience, this involves coordinating IoT technologies for further developed administration, checking, and data examination.
•	IoT Devices: 
The IoT gadgets at KN College incorporate energy-effective brilliant lighting systems, smart locks with secure access the executives like the Igloo home Bluetooth Smart Deadbolt 2S ($279), and environmental sensors like the D23-NB ($179) for temperature and air quality observing. Innovation like the BenQ MX560 projector ($649) further develops homeroom executives and improves learning conditions.

 
Figure 3.7.1 IoT Integration Plan of KN University
•	Network Division: 
A committed IoT VLAN is set up at KN College to isolate IoT traffic from the fundamental network. This further develops data transfer capacity management to keep significant applications moving along as expected and increments security by preventing likely dangers from spreading. Since customized policies are permitted in this arrangement, overseeing IoT gadgets is additionally made more straightforward. To diminish security dangers, firewall rules are created to confine connections between the IoT VLAN and significant network fragments. To shield essential network services, these guidelines force severe limitations by allowing just vital traffic, denying unnecessary protocols, and looking out for oddities.
•	Information Collection and Management: 
The IoT gateway at KN College incorporates gathering information from different IoT gadgets, filtering and collecting the information before sending it to the cloud or server centre. Furthermore, it changes numerous communication conventions into a typical configuration, using encryption and confirmation to ensure safe data transfer. Information is kept in adaptable, secure data sets that might be tracked down nearby or in the cloud to guarantee security and consistency. Access controls and encryption are set up. Computerized backups given by cloud administrations further develop security and information storage, and investigations are finished to optimize operations and decision-making at campuses.
•	Security: 
Gadget checks at KN College involves endorsing and verifying Internet of Things (IoT) gadgets before network access through enlistment processes, unmistakable characters, and safe onboarding procedures, including multi-factor or certificate-based authentication. Information is encoded during transmission between Internet of Things gadgets and network endpoints to forestall unwanted access, utilizing algorithms like AES and TLS protocols. This ensures end-to-end encryption, and to keep up with high security and fix arising shortcomings, encryption guidelines are refreshed consistently.
2.8	Network Implementation Plan
The execution plan at KN College calls for introducing, designing, and configuring network gear and programming, followed by thorough testing and system combination. To guarantee smooth progress, ensure end clients get training, exhaustive documentation, and client manuals.
•	Project Planning: 
A comprehensive schedule involving stages, dates, and achievements is made to ensure timely completion of KN College's task arranging. Assets for equipment and staff are apportioned, alongside monetary administration and the execution of communication and hazard management plans. Keeping up with documentation and setting up representative preparation upholds the smooth execution of new systems and viable project management.
•	Deployment: 
At KN University, deployment comprises a few basic processes. Equipment installation is finished by introducing network gadgets, such as switches and routers, as per the plan, guaranteeing legitimate power and network cable connections, and setting gadgets for best execution. Then, software is arranged by doling out IP addresses, VLANs, and routing protocols and applying safety efforts like encryption and firewalls. Finally, the new equipment should be integrated into the current system and tested completely to guarantee consistent communication and similarity with present frameworks and applications.
•	Testing and Approval: 
At KN University, early testing is finished to confirm that all network equipment and programming have been appropriately introduced and arranged as per the plan details. This incorporates approving programming settings and equipment associations. Execution testing guarantees that the network satisfies speed, unwavering quality, and well-being norms, while functionality testing assesses fundamental network functions. Any shortcomings found are recorded and investigated using diagnostic apparatuses to lay out their underlying causes. After making fixes, impacted parts are retested. At long last, approval tests ensure that the network proceeds as expected while staying secure and solid. 
