# Active Directory Configurations and Demonstration

## Overview

KN University is a prestigious university in Australia with Melbourne, Sydney, Brisbane, and Adelaide campuses. The university offers undergraduate programs across four faculties. The schools include those in engineering, technology, law, and business. Every campus has teaching and administrative facilities that enhance education provision.
This document describes all the steps for Designing and implementing the active directory and user authentication using the Oracle Virtual Box Virtual Machines. Four virtual machines have been used for the demonstration, including 

1.	Windows Server VM.
2.	Two Windows 10 client VMs
3.	Pfsense Network management VM.

We have chosen Role Base Access Control (RBAC) as our Access Control method for the KN University. Before explaining the steps of the Active Directory, we have discussed the advantages of using RBAC. 
 
## Justification for Choosing Role-based Access Control (RBAC)

- *Role Base Access Control (RBAC)* is scalable, efficient, and consistent; hence, it suits large organizations by grouping users into roles so permissions can be easily managed (Ni et al. 2010). Auditing is made easier by it and performs very well with complex structures. However, configuring RBAC requires some effort, and it may also be challenging to work with numerous roles. It also has a limitation of no flexibility for exception handling.

- *Discretionary Access Control (DAC)* is another access control where the user has some control and where the resource owner determines the access (Sandhu & Munawer 1998). Though it is simple to apply and requires little authorization in smaller workplaces, it carries security issues due to the decentralized nature of the system. It cannot be applied to large institutions like universities.

- *Mandatory Access Control (MAC)* provides the highest level of security and tight centralised control over the whole system used in security-sensitive organizations, such as government or military organizations (Xu et al. 2009). However, it is rigid, very complex to administer, and unsuitable for commercial applications where flexibility is important.

- *Rule-based access control* is not static and is much more granular and flexible than Role-based access control (Bertolissi & Uttha 2013). However, managing many rules makes it very difficult to identify what exactly is happening. Therefore, it is more appropriate for those organisations that require condition access rather than a simple one like a university.

- *Policy-Based Access Control (PBAC)* is centralized in management, highly adaptive, and scalable to accommodate the constantly changing environment (Pal et al. 2018). However, it involves complicated initialization, can be tricky to apply, and possibly brings about performance impacts caused by multiple policy executions.
  
Therefore, RBAC is most appropriate for KN University since it is scalable, efficient and provides centralized user access control. Since it serves the entire community, including students and academic and non-academic staff across the various campuses, roles eliminate the complexity of permission assignment by categorizing users according to their roles. This also increases the level of security and decreases the burden of administrative work because permissions will have been centralised for a specific group of users, thus eliminating divergent opportunities for human errors.

Also, RBAC's effectiveness in maintaining secure and consistent access policies complements the university’s requirement of preserving the privacy of information it stores, including academic records and research data, while simultaneously providing flexibility in information resource access across faculties and departments. Due to its well-ordered procedure for distributing roles and documented delegation, RBAC offers the finest blend of security, simplicity of audit, and adaptability to the complex requirements that KN University’s growing number of interconnected structures possess.


## Setting Up Active Directory

The most crucial demonstration step is setting up Windows Active Directory (AD). AD is a Microsoft directory service that helps manage a domain's users, computers and network resources. It runs on Windows Server platforms and uses the LDAP, Kerberos, and DNS to authenticate and authorise. AD can provide IT administrators the right to manage permissions, security policies, and access rights to resources in a network. It provides the layered structure of networks in terms of domains, trees, and forests, providing more scalability and security for organizations.

### 1.	Creating the Virtual Machine and AD
These are the main steps of creating the VM.
1.	Install Oracle Virtual Box and create a VM using the following configurations.
•	RAM – 4GB
•	CPU – 4core
•	HDD – 50GB
2.	Install the Windows Server 2022, downloaded using this link.
3.	Complete the general startup settings to add the Administrator user. 
4.	Open the Server Manager, click Add Role and Features, then add the Active Directory Domani Service (AD DS) and complete the following process.
 
![image](https://github.com/user-attachments/assets/ebfa8bab-1a1e-446b-a809-bfb77a349bb8)

5.	Promote the Server to a Domain controller from the Notification flag shown in Figure 1.3 and add a new forest, give the domain name as knu.local and complete the process by providing the Directory  Services Restore Mode (DRSM) password. 
 
![image](https://github.com/user-attachments/assets/1fb4129d-2ba7-493a-9460-82707d86aca1)

6.	Re-boot the Windows Server VM to complete the process.
7.	Configure the DNS settings and provide the 10.255.2.10 as the Static IP.
The following screenshot shows the completed AD DC. 
 
![image](https://github.com/user-attachments/assets/94643de7-e02f-4bc1-b779-66e81550ca4a)

### 2.	Creating Organisational Units
Then, create the User groups using the following steps for each user group. For the demonstration, we created only three user groups 
1.	Students
2.	Academic Staff
3.	Non-Academic
Active Directory Users and Computers will create New > Organizational Units (UOs) for creating students, academic staff, and non-academic staff.

The following screenshot shows the creation of the Organisational units.
 
![image](https://github.com/user-attachments/assets/8f61f499-0ec3-40ef-a244-51cc81672df4)

Then, add the dummy data to each organisational unit. We used the following notation to add the users for testing. 
-	Username [initial of first name]. [last-named]
-	Default password: [initials of the username] @[date of birth in the format of ddmmyy]
 
![image](https://github.com/user-attachments/assets/6d69f076-c80e-4ea5-a3aa-af8d985d811b)
 
### 3.	Setup DHCP Server
For the demonstration, the DHCP server has been installed in the same Server 10.255.2.10
 
![image](https://github.com/user-attachments/assets/054c9382-2538-48ce-9642-de720b270942)

 After installing the DHCP server, configure it as follows: 
 
*Configuring DHCP Server*
1.	After installation, open DHCP Manager from Server Manager > Tools.
2.	Right-click IPv4 and select New Scope.
3.	Configure DHCP scopes for each VLAN/subnet:

![image](https://github.com/user-attachments/assets/1fd1ee09-f233-4b87-9c9e-568fde67b491)



4.	For each scope, right-click the scope and select Configure Options.
5.	Add the following options:
-	003 Router: Enter the default gateway for the subnet (e.g., 10.10.0.1 for Students).
-	006 DNS Server: Enter the DNS server address (e.g., 10.255.2.10).

 
![image](https://github.com/user-attachments/assets/391cfd07-7b3f-4e1f-8d33-90eded317c17)


 
### 4.	Set Up Network Policy Server (NPS) 
Set Up Network Policy Server (NPS) for RADIUS access and VLAN Assignment. Install the NPS role by adding a new Role and Feature as follows. 
 
![image](https://github.com/user-attachments/assets/5fa69bb3-7fc3-428d-80c7-3d7b50f9b2ea)
 
Installed Network Policy Server (NPS) using the following steps:
1.	Open Server Manager > Add Roles and Features.
2.	Select Network Policy and Access Services and click Next.
3.	Choose Network Policy Server (NPS) and install the role.

Then follow the following steps to Register NPS in Active Directory:
1.	Open NPS from Server Manager > Tools > Network Policy Server.
2.	Right-click NPS (Local) and select Register server in Active Directory.
3.	Confirm the registration, allowing NPS to authenticate users based on AD groups.


Then, create Network Policies for Each User Group using the following steps
1.	Go to NPS, expand Policies, right-click Network Policies, and choose New.
2.	Name the policy for each user group in the New Network Policy Wizard.

##### a.	New Policy for Students:
- Name: Students_Network_Policy.
- Conditions: Add a condition for User Groups and choose Students_Group from AD.
- Constraints: Set up PEAP for authentication. Ensure that MS-CHAPv2 is selected for the authentication method within PEAP.
- Settings: Under RADIUS Attributes > Standard, add Tunnel-Pvt-Group-ID and set the VLAN ID to VLAN 10.

##### b.	New Policy for Academic Staff:
- Name: AcademicStaff_Network_Policy.
- Conditions: Add AcademicStaff_Group from AD.
- Constraints: Set up PEAP for authentication. Ensure that MS-CHAPv2 is selected for the authentication method within PEAP.
- Settings: Under RADIUS Attributes > Standard, add Tunnel-Pvt-Group-ID and set the VLAN ID to VLAN 20.

##### c.	New Policy for Non-Academic Staff:
- Name: NonAcademicStaff_Network_Policy.
- Conditions: Add NonAcademicStaff_Group from AD.
- Constraints: Set up PEAP for authentication. Ensure that MS-CHAPv2 is selected for the authentication method within PEAP.
- Settings: Under RADIUS Attributes > Standard, add Tunnel-Pvt-Group-ID and set the VLAN ID to VLAN 30.

3.	Complete the wizard and ensure the policy is enabled.
4.	These policies will now assign Students to VLAN 10, Academic Staff to VLAN 20 and Non-Academic Staff to 30 upon successful authentication.
 
![image](https://github.com/user-attachments/assets/e6fb18ab-def2-450f-986e-3e3f2e37ec58)

 
### 5.	Setup Group Policies

After setting up and configuring the VMs, the final step is to configure the Group policies to control the access of each user group.

1. Configure Group Policies (GPOs)
Before creating the controls, we made all the Group Policies for each user group using the following steps:

        I.	Open Group Policy Management.

        II.	Right-click on the Group Policy Objects container and select New.
  
        III.	Name the policy: 

          a.	StudentPolicy, 

          b.	AcademicStaffPolicy, 

          c.	NonAcademicStaffPolicy

        IV.	Edit the policy by right-clicking and selecting Edit.

        V.	Set user and computer configurations (e.g., restrict access to certain network drives for students).


The following screenshot shows the GPOs
 
![image](https://github.com/user-attachments/assets/143da5e7-6acc-488c-8a39-ec1edea47935)

After creating the GPOs, 

2.	Link GPOs to Organisational Units (OU)s:

        i.	Right-click on the OU and select Link an Existing GPO.
  	
        ii.	Choose the appropriate GPO
 
## Setting up the PfSense VM

Download the ISO of the Netgate PfSense using the following link: 
https://www.pfsense.org/download/   
Then, Installed PFsense into the VM of the Virtual Box as below
 
![image](https://github.com/user-attachments/assets/02df9838-2d54-4a4a-bc25-f8f391160fa9)

Then, two network adapters are added to the network settings, and one adapter is set as the Bridge adapter to connect to the Internet directly. The second adapter is the Internal Network and selects the internal network, and the internal network is KNU. As a backup, we added another adapter as a NAT for the third adapter, as shown in the screenshots below, Image 5.1, Image 5.2 and Image 5.3. 


 
![image](https://github.com/user-attachments/assets/57c69806-475e-42c3-b274-7ad63c093029)

 
![image](https://github.com/user-attachments/assets/69414350-c7a1-4e67-9f1f-ddf6193a57da)

 
![image](https://github.com/user-attachments/assets/3d6641b9-b9ff-465e-b767-e47516e604f5)


After installing and setting up the VM, open the Pfsense terminal as follows and configure the IP address as 10.25.2.1, MEL-02-RTR-01 as following image 5.5.

 
![image](https://github.com/user-attachments/assets/a6ec3219-7dd6-47d3-87a5-fc82fe45581d)

Then, Configure the PfSense to create VLANs for students and Academic Staff as follows:
 
![image](https://github.com/user-attachments/assets/d14debed-a272-4d43-bb38-b499583714c2)

After finishing the network configuration, set up Radius on the PfSense. For that, log in to the Router GUI using the Server machine, as shown in Figure 5.7
Login using the default username and password.
 
![image](https://github.com/user-attachments/assets/6e300599-33ea-4665-b121-55575d56d9b9)


The next figure shows the Dashboard of the PfSense
 
![image](https://github.com/user-attachments/assets/4a3ed313-3508-4c95-9585-feba5783cc61)

Before setting up the RADIUS client, we set up the RADIUS server on the server machine, as shown in the screenshot, Image 5.8.
Then, use the following steps to create the RADIUS Client on the Server
1.	Create a New RADIUS Client from the RADIUS Server.


        I.	Go to NPS in the tools and expand RADIUS Clients and Servers.
  	
        II.	Right-click on RADIUS Clients and choose New.
  	
        III.	Name it MEL-02-RTR-01
  	
        IV.	Enter the IP address of MEL-02-RTR-01 in Address (10.255.2.1)
  	
        V.	Enter a Shared Secret (this will be used later in pfSense to link RADIUS).
  	
        VI.	Click OK.

 
![image](https://github.com/user-attachments/assets/f2397007-a39a-4796-b88a-587709cb297b)


2.	Configure pfSense to Use RADIUS Authentication


Then, I configured pfSense to use RADIUS for authentication and linked it with the Active Directory server.

    1.	Go to System > User Manager > Authentication Servers in pfSense.
    
    2.	Add a New Authentication Server:
    
      I.	Click Add to create a new server.
      
      II.	Set Type to RADIUS.
      
      III.	Set the name as KNU_RADIUS

      IV.	Hostname or IP: 10.255.2.10
      
      V.	Authentication port: The default RADIUS port is 1812.
      
      VI.	Shared Secret: Used the shared secret configured earlier on the NPS server.
      
      VII.	Authentication Timeout: Default.
      
      VIII.	NAS IP Address: 10.255.2.1.
      
      IX.	Click Save to apply the settings.
 
![image](https://github.com/user-attachments/assets/d2991ad4-3435-4a25-9ff7-e3c33a73cd8b)


3.	Set Up pfSense to Assign VLANs Based on RADIUS Groups


        I.	Go to Interfaces > Assignments in pfSense.
        II.	Enable Dynamic VLANs (WPA2-Enterprise)
            - Go to Interfaces > VLAN10 > Advanced.
            - Under VLAN Tagging, enable Dynamic VLAN Assignment.
        III.	Configure the Firewall Rules for VLAN Interfaces to communicate between VLANs and NAT, as shown in Figure 5.10. 
            - Add rules under Firewall > Rules for each VLAN.
        IV.	Set up pfSense Captive Portal for RADIUS-based authentication for wireless users:
            - Using WPA2-Enterprise, link it to RADIUS for dynamic VLAN assignment.

 
![image](https://github.com/user-attachments/assets/680fabd3-172c-4234-9363-ab2d24faa806)


 
## Creating the Client VM with Windows 10

For the demonstration of the users, we are using two VMs installed with Windows 10 operating system. The following screenshot shows the installation of Windows 10 in the VM. 
 
![image](https://github.com/user-attachments/assets/7e2133b6-97da-4017-b305-31b4e5593fc0)


After the installation, set up the VM as a standard Windows 10 and name the PC according to the naming convention MEL-01-WS-01. Then, configure the network settings of the VM and connect to the internal network using the Virtual Box Network Adapter shown below in Figure 5.2. 

 
![image](https://github.com/user-attachments/assets/b6d64058-d061-413f-98c5-5e54d5f7b4d0)


Then, a clone of the VM will be created to demonstrate the student and staff simultaneously. 
After setting up the network configurations in the virtual box, go to the properties of the VM in Windows 10 and select the domain as the knu.local, as shown below.
 
![image](https://github.com/user-attachments/assets/27a19623-c693-4201-bbd2-b22d9a70d079)


Then, sign in as a user from the domain to set it up and connect to the KNU.LOCAL, as shown below in Figure 6.4. 
 
![image](https://github.com/user-attachments/assets/e0de8737-6e46-4b21-9a5e-f2c572dcf40f)


After signing and successfully connecting to the domain, the VM should be restarted, as prompted in the screenshot below, to log in as the client of the KNU Domain. 
 
![image](https://github.com/user-attachments/assets/f589ccce-cc1a-469a-ac22-c847ee81783b)
 

After restarting the VM, it will link and ask to log in using the username and password as shown below and then all the users set in the AD DC can log in using the machine using the credentials.  Figure 6.6 shows the login to the user Krishan Himesh, which we set up in the AD DC.
 
![image](https://github.com/user-attachments/assets/6737fac8-fa18-47ec-b0c6-6494f414be26)


After setting up all the machines, the next step is implementing the Access Control and User Policies in the AD CD server to demonstrate the security levels and administration. 

## Implementing three access control protocols and Testing

Then implemented the demonstration of the three access control features to distinguish between Students and the Academic Staff

### 1.	Application installation Policy
The first policy is to set only academic staff to install the applications, whereas students cannot install any applications in their user accounts or on local machines. 
Enabled Run-only specified Windows applications to install only chrome.exe for Staff OU. 
 
![image](https://github.com/user-attachments/assets/592d50ba-1443-453c-8ece-3725f2a44e94)


Restrict installation of applications in the Student OU as follows:
 
![image](https://github.com/user-attachments/assets/b4fb2491-077e-4ba3-8d6e-0559b44cbf5e)

 ![image](https://github.com/user-attachments/assets/eae2ba85-31ee-483b-be58-a4377093ab99)

Add Policy only to use installed programs in the C:\ to create the allow list.
 
![image](https://github.com/user-attachments/assets/d2a9f84a-3395-4b13-ae6a-02e763326bf5)

Provide User Access to Staff OU Ito installs Chrome.exe application
 
![image](https://github.com/user-attachments/assets/04404f82-6e30-42fc-85bb-c463e0b8881f)

 
![image](https://github.com/user-attachments/assets/f9d968b4-87cb-4201-9592-9b55a3655af5)


 
### 2.	Implementing access control for academic resources drive 
Create a folder in the Main Server and share it with permissions as shown below to demonstrate the access control to the Academic Resources. 
 
![image](https://github.com/user-attachments/assets/a7b3f21c-bb81-4817-95b9-edae254e032d)

 
![image](https://github.com/user-attachments/assets/5f7c5493-7dc8-4a9a-bf75-04e5e42f10b4)

Then, the permission level for each Organisational Unit is set as follows. 
 
![image](https://github.com/user-attachments/assets/8c1bc0b1-94d3-46c1-b477-24edfab23674)

 
![image](https://github.com/user-attachments/assets/1e7c84a1-e323-4600-ae3a-e90dc90464c9)

### 3.	Configure the Firewall rules to block traffic from Facebook.com
Using the GUI of the Pfsense, configure the firewall to block the traffic from Facebook.com. 
For that, we have blocked the public IP range of Facebook, which is 157.240.8.0/24. 
 
![image](https://github.com/user-attachments/assets/0004089e-7534-4d5a-8997-a9c0bec554a5)


After creating the policies, Update the policies in the clients using the following command 
 
![image](https://github.com/user-attachments/assets/e1d00414-d0f7-44a8-91b5-d793acf28aeb)


In addition to the main policies, we have set up a Common Policy for Turnoff Windows  Updates.
 
![image](https://github.com/user-attachments/assets/3a1e0af8-2612-4aa8-95c2-38080885aea3)


 ![image](https://github.com/user-attachments/assets/f2f78276-0f0e-4726-b1b2-c1c013348b62)


 
### Testing
1.	The following screenshot shows the access to the file with the student and the staff Ous. Staff can Edit, Delete and create files that Students can only read. 
 
![image](https://github.com/user-attachments/assets/39c6960e-e3e9-46f2-a358-22b72dd584d9)

2.	Test the Application Access Control by installing Chrome.exe on the student and Staff machines. 
 
![image](https://github.com/user-attachments/assets/37569613-c5a1-4fca-b12b-212fddf4cdfd)

 
![image](https://github.com/user-attachments/assets/abbc3806-9c54-4ad2-991f-56d1262436fa)



3.	Restrict access to Facebook.com for Students and staff using the firewall. 
 
![image](https://github.com/user-attachments/assets/0fdd3d4f-122a-4943-8eb5-9bba0fe97a5d)


 
## References
- Bertolissi, C & Uttha, W 2013, 'Automated analysis of rule-based access control policies', in Proceedings of the 7th workshop on Programming languages meets program verification, ACM, pp. 47-56.
- Ni, Q, Bertino, E, Lobo, J, Brodie, C, Karat, CM, Karat, J & Trombeta, A 2010, 'Privacy-aware role-based access control', ACM Transactions on Information and System Security (TISSEC), vol. 13, no. 3, pp. 1-31.
- Pal, S, Hitchens, M, Varadharajan, V & Rabehaja, T 2018, 'Policy-based access control for constrained healthcare resources', in Proceedings of the 2018 IEEE 19th International Symposium on A World of Wireless, Mobile and Multimedia Networks (WoWMoM), IEEE, pp. 588-599.
- Sandhu, R & Munawer, Q 1998, 'How to do discretionary access control using roles', in Proceedings of the third ACM workshop on Role-based access control, ACM, pp. 47-54.
- Xu, L, Zhang, H, Du, X & Wang, C 2009, 'Research on mandatory access control model for application system', in Proceedings of the 2009 International Conference on Networks Security, Wireless Communications and Trusted Computing, vol. 2, IEEE, pp. 159-163.
