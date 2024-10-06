# Web Server Demonstration
## Introduction
In the present educational environment, the need for digital platforms that improve on academic administration is more important than any time in recent memory. Colleges are progressively taking on web-based systems that permit students and staff to consistently associate with academic data. This project intends to set up a web server on an Azure Virtual Machine (VM) utilizing XAMPP to have a college Moodle framework. The framework will act as a focal centre point where students can undoubtedly see their academic marks and staff can productively manage student records, including altering and erasing marks. This web-based system will further develop availability and usability for both students and staff.
This technical artifact records the setup and configuration of a web server utilizing XAMPP facilitated on an Azure Virtual Machine (VM). It includes network integration, web server configuration on Virtual Machine and sample of web server running. The exhibit is pointed toward displaying the integration of this web server inside KN University's network for hosting internal web services and databases.

## Azure Virtual Machine Setup
To host the web server on the cloud, an Azure Virtual Machine has been provisioned with the following specifications:

### Virtual Machine Specifications:
•	Size: Standard B1s (1 vCPU, 1 GiB memory) to handle moderate web traffic and database operations.
•	Operating System: Linux Ubuntu 22.04 LTS, chosen for its stability, wide support, and compatibility with XAMPP.
•	Storage: 30GB SSD for OS, XAMPP files, website content, and MySQL databases.
•	Azure Region: East US

![image](https://github.com/user-attachments/assets/39911ecb-7090-44c6-9806-bc97292a462b)

 
                                   Fig: 1.1 Creating Virtual Machine

Public IP Address: A static public IP address 4.227.162.127 is assigned to the VM, ensuring that the web server is always accessible through the same IP. 
Networking:
The VM is part for a Virtual Network (VNet) with subnet designs for communication among university and cloud environments.
Firewall: Azure Network Security Group (NSG) rules permit inbound traffic on ports 80 (HTTP), 443 (HTTPS), and 3306(SQL).
 
Fig: 1.2 Allowed Ports

## XAMPP Installation
XAMPP is an open-source cross-platform web server arrangement that incorporates Apache (for HTTP server), MySQL (for datasets), PHP, and Perl. There are screenshots below how installer is made executable and how is it installed.

 
Fig: 2.1 XAMPP Installation
After installation is completed, XAMPP services are started, and it is running successfully. 
 
Fig: 2.2 Starting XAMPP
Apache is configured to listen on ports 80 and 443. Ensuring these ports are open in both the Azure NSG and the operating system level firewall.
 
Fig: 2.3 Port setting on XAMPP Configuration File

### Website Directory:
The root directory for hosting website files is in htdocs:
•	Linux: /opt/lampp/htdocs/
HTML, PHP, or other web application files to this directory for public access are added.

Apache error logs:
 
Fig: 2.4 Apache Error Logs

### Security Configurations:
To secure the web server with HTTPS, an SSL certificate is installed.
•	Self-signed certificate is used.
•	 Apache’s SSL configuration in httpd-ssl.conf is updated.
 
Fig: 2.5 Self-Signed Certificate
### MySQL Connection:
Database kn_university relates to the public IP Address of VM. This database contains all the data of university with login details, name, address as well as marks of the students. 
 
Fig: 2.6 SQL Database Connection

 
Fig: 2.7 XAMPP Database Dashboard



### Access Control:
XAMPP's administrative devices (phpMyAdmin, control panel) are limited to explicit IPs or expect verification to prevent unapproved access.

### Firewall Rules:
NSGs and Azure firewall rules are designed to permit traffic just from believed campus networks.

### Backup and Redundancy:
VM Backup: Regular snapshots of the VM are taken utilizing Azure Backup Services, guaranteeing recoverability in the event of system failure or information loss.


## Web Server (Moodle of KN University)

### Welcome Page:
Welcome Page provides access to login from student and staff account.
 
Fig: 3.1 Welcome Page of KN University Moodle


### Student Login:
It displays the Student Login interface for KN University, asking users to input their StudentID and Password for authentication.
 
Fig: 3.2 Student Login Page 


### Student Welcome page:
Displays a personalized interface for students to select a course and view marks. Includes dynamic buttons for each course (e.g., "KNU10" and "KNU12"), which lead to their respective marks page. Authentication and session management are implied through personalized welcome messages and the "Logout" option.
 
Fig: 3.3 Welcome Page for Students

### Marks:
Fetches and displays the student's marks for the selected course in a simple table where students can only view their marks.
 
Fig: 3.4 Marks 

### Staff Login Page:
It displays the Staff Login interface for KN University, asking users to input their StaffID and Password for authentication.
 
Fig: 3.5 Staff Login Page 

### Staff Welcome page:
Displays a personalized interface for staffs to select a course he/she is teaching and view as well as edit marks. Includes dynamic buttons for each course (e.g., "KNU10" and "KNU12"), which lead to their respective manage marks page. Authentication and session management are implied through personalized welcome messages and the "Logout" option.

 
Fig: 3.6 Welcome Page for Staffs

### Manage marks:
It provides functionality for staff to view, edit, and delete student marks. Each row displays student details, with respective "Edit" and "Delete" options. 
 
Fig: 3.7 Staff Dashboard

### Edit Marks:
Fetches and displays the student's marks for the selected course in a simple table where staffs can update their marks.
 
Fig: 3.8 Edit Marks
### Delete marks:
Staff can delete the student’s marks. When delete button is clicked, virtual machine will ask for the confirmation.
 
Fig: 3.9 Delete Marks

