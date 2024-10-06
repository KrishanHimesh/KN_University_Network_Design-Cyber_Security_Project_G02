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

 ![image](https://github.com/user-attachments/assets/a5ce2766-2f60-4035-901e-a61d6bdfda36)

   Fig: 1.2 Allowed Ports

## XAMPP Installation
XAMPP is an open-source cross-platform web server arrangement that incorporates Apache (for HTTP server), MySQL (for datasets), PHP, and Perl. There are screenshots below how installer is made executable and how is it installed.

 ![image](https://github.com/user-attachments/assets/dc39dade-8f8e-4e5a-904f-c5af48058230)

Fig: 2.1 XAMPP Installation
After installation is completed, XAMPP services are started, and it is running successfully. 

 ![image](https://github.com/user-attachments/assets/e2715394-9b04-4a48-80f3-1fe493c1099d)

Fig: 2.2 Starting XAMPP
Apache is configured to listen on ports 80 and 443. Ensuring these ports are open in both the Azure NSG and the operating system level firewall.
 ![image](https://github.com/user-attachments/assets/72b7b897-fa9c-49cf-af68-9ddcd80b9a02)

Fig: 2.3 Port setting on XAMPP Configuration File

### Website Directory:
The root directory for hosting website files is in htdocs:
•	Linux: /opt/lampp/htdocs/
HTML, PHP, or other web application files to this directory for public access are added.

Apache error logs:
 ![image](https://github.com/user-attachments/assets/06932488-cd60-4360-9850-aa6d23024bf0)

Fig: 2.4 Apache Error Logs

### Security Configurations:
To secure the web server with HTTPS, an SSL certificate is installed.
•	Self-signed certificate is used.
•	 Apache’s SSL configuration in httpd-ssl.conf is updated.

 ![image](https://github.com/user-attachments/assets/770dbc25-803a-425a-ac0b-8c6da243847b)

Fig: 2.5 Self-Signed Certificate
### MySQL Connection:
Database kn_university relates to the public IP Address of VM. This database contains all the data of university with login details, name, address as well as marks of the students. 

 ![image](https://github.com/user-attachments/assets/8f4d4615-9a6d-483e-bc2a-2883679d1b71)

Fig: 2.6 SQL Database Connection

 ![image](https://github.com/user-attachments/assets/3dc9b14d-5daa-4081-b5c4-2f896627ea2f)

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

 ![image](https://github.com/user-attachments/assets/e30066be-da9b-4e21-9ac8-329c761d92a9)

Fig: 3.1 Welcome Page of KN University Moodle


### Student Login:
It displays the Student Login interface for KN University, asking users to input their StudentID and Password for authentication.

 ![image](https://github.com/user-attachments/assets/56e89ce7-1c3e-4a7c-9271-fa137e83dc54)

Fig: 3.2 Student Login Page 


### Student Welcome page:
Displays a personalized interface for students to select a course and view marks. Includes dynamic buttons for each course (e.g., "KNU10" and "KNU12"), which lead to their respective marks page. Authentication and session management are implied through personalized welcome messages and the "Logout" option.

 ![image](https://github.com/user-attachments/assets/ec37483a-fd45-4027-bf0a-1a9fdb4cea3f)

Fig: 3.3 Welcome Page for Students

### Marks:
Fetches and displays the student's marks for the selected course in a simple table where students can only view their marks.

 ![image](https://github.com/user-attachments/assets/d87fcb14-e5c5-49d2-bb67-bec4654af28a)

Fig: 3.4 Marks 

### Staff Login Page:
It displays the Staff Login interface for KN University, asking users to input their StaffID and Password for authentication.

 ![image](https://github.com/user-attachments/assets/51674261-7bc6-4c9b-adea-26a71d54bd8a)

Fig: 3.5 Staff Login Page 

### Staff Welcome page:
Displays a personalized interface for staffs to select a course he/she is teaching and view as well as edit marks. Includes dynamic buttons for each course (e.g., "KNU10" and "KNU12"), which lead to their respective manage marks page. Authentication and session management are implied through personalized welcome messages and the "Logout" option.

 ![image](https://github.com/user-attachments/assets/3fc80bc7-d356-4ed9-b90a-fe8d158c8b23)

Fig: 3.6 Welcome Page for Staffs

### Manage marks:
It provides functionality for staff to view, edit, and delete student marks. Each row displays student details, with respective "Edit" and "Delete" options. 

 ![image](https://github.com/user-attachments/assets/db25f946-94f0-4fed-aa60-1a8b4178a81e)

Fig: 3.7 Staff Dashboard

### Edit Marks:
Fetches and displays the student's marks for the selected course in a simple table where staffs can update their marks.

 ![image](https://github.com/user-attachments/assets/2e185ee6-6772-4109-9180-5d1112721a63)

Fig: 3.8 Edit Marks
### Delete marks:
Staff can delete the student’s marks. When delete button is clicked, virtual machine will ask for the confirmation.

 ![image](https://github.com/user-attachments/assets/b8ec5ed0-ee01-453c-928f-e00fa1ae8513)

Fig: 3.9 Delete Marks

