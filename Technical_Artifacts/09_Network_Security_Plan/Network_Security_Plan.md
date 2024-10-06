# Network Security Plan

A Network Security Plan guarantees the university's network is safeguarded against dangers, keeps up with data integrity, and gives secure access to assets. The following is a consolidated arrangement that covers key components of network security.
## Objectives
-   Confidentiality: Ensuring the secrecy of sensitive data incorporates a comprehensive technique that integrates data characterization, access control frameworks, encryption, secure data storage, access methodologies, checking and inspecting, client preparing, and a vigorous incident reaction plan.
-  	Integrity: Ensuring data integrity incorporates executing measures that safeguard information from unapproved change and debasement, guaranteeing its precision and consistency all through its lifecycle. This consolidates cycles, advancements, and systems planned to detect and prevent information modifying, as well as components to really look at data precision.
-  	Availability: Guaranteeing the accessibility of network assets is critical for staying aware of nonstop access to information and services for students, Labor force, and staff. This incorporates completing measures to forestall downtime, promptly recover from interferences, and stay aware of ideal execution.
- 	Compliance: Consistence with genuine and regulatory requirements is principal for staying aware of the uprightness, privacy, and availability of organization assets while ensuring the school complies with material guidelines, rules, and standards.


  ![Image 5](https://github.com/user-attachments/assets/b310c1f9-6a1e-4210-b721-43778eda24c6)

The KN University network security design is displayed in the above diagram. The network's first line of protection is perimeter security. The router that connects the college's network to the web is one of its parts. By filtering and managing all information entering and leaving the network, the firewall fills in as a security barrier. By restricting admittance to the network to simply protect and support traffic, this setup prepares for outside dangers coming from the Web. The network of the university is protected from inside by inward security. Inside the network, information flow is controlled and coordinated by the Core Switch. An interior firewall safeguards basic assets by watching out for and overseeing inward interchanges. This adds an additional layer of protection. The university stores and keeps up with its essential information in the Data Centre, which fills in as the hub of the network's data frameworks.
By utilizing a VPN Gateway, Access Control ensures that main approved clients can interface with the college network, even from distant areas. Using a SIEM framework to follow and inspect security action is known as security management. This recognizes and address potential dangers. To improve and keep up with its advanced administrations, the organization additionally utilizes cloud administrations, which lay out associations with outside cloud suppliers. The method involved with defending delicate data is called encryption. Data-at-Rest encryption safeguards protects information by ensuring that, regardless of whether somebody accesses it, they can't peruse it without the essential authorisation. Data-in-Transit Encryption shields information while it goes over the organization, forestalling block attempt or control while it is being sent starting with one area then onto the next.
The figure shows how the different components of network security are associated with one another and add to the general security of the KN University network.


## Key Components

## Firewalls
- Purpose: Their fundamental intention is to make an obstruction between a trusted interior network, and untrusted outside networks, like the web. In this way, firewalls help to protect against unapproved access, digital dangers, and information breaks. Model: Norton 360 Suite
  
## Types:
-   Perimeter Firewalls: Their basic role is to make a barrier between a trusted internal network, and untrusted external networks, like the web. 
-   Internal Firewalls: Inner firewalls, generally called segmenting firewalls, are sent inside an internal network to make different security zones. Internal firewalls can isolate fundamental or fragile regions like finance, HR, or imaginative work from the rest of the network.
  
## Intrusion Detection and Prevention Systems (IDPS)
-  Purpose:  Intrusion Detection and Prevention Systems (IDPS) are planned to recognize and prevent malicious activities inside a network or structure. They have a huge impact in online protection by perceiving anticipated risks, cautioning administrators, and taking mechanized actions to mitigate risks.
  
## Types:
-  Network-based IDPS: Network-Based IDPS (NIDPS) are conveyed to monitor and take apart network traffic for signs of malevolent movement. They are regularly arranged at central issues inside a network, like gateways, switches, and routers, to give broad oversight of the information flowing through the network.
-  Host-based IDPS: Host Based IDPS (HIDPS) are presented straightforwardly on individual gadgets or hosts, like servers, workstations, or endpoints. They focus on observing and examining activities well defined for each host to distinguish and prevent dangers.
  
## Virtual Private Network (VPN)
-  Purpose: A Virtual Private Network (VPN) is an innovation that gives secure distant induction to a network over the web. VPNs use strong encryption shows to shield data on the way, ensuring that any caught data is ambiguous without the encryption keys.
  
## Types:
-  Site-to-Site VPN: A Site-to-Site VPN is a strategy used to interface no less than at least two networks, regularly corporate or various levelled LANs, over the web securely. The primary job of a Site-to-Site VPN is to securely interface geologically dissipated campuses, allowing them to share resources and data securely over a public network like the web.
-  Client-to-Site VPN: A Client-to-Site VPN, generally called Remote Access VPN, licenses individual clients to connect with a confidential network from distant regions. The fundamental job of a client-to-Site VPN is to give distant clients secure and encoded admittance to an association inside network. This ensures that sensitive data and communications stay secured, regardless, when gotten to over conceivably temperamental public networks like home Wi-Fi or public hotspots.
  
## Encryption: 
-  Encryption is a security cycle that changes data into an encoded plan, making it indiscernible to unapproved clients. Solid encryption algorithms, for instance, AES-256, give major areas of strength for an against digital dangers, guaranteeing the secrecy and security of information sent over conceivably unreliable networks.

## Access Control
-  Purpose: Access control is a safety measure that manages who or what can view or involve assets in a computing environment. The fundamental role of access control is to limit access to fragile data and critical systems considering client roles and consents.
  
### Mechanisms:
-   Role-Based Access Control (RBAC): RBAC is a strategy for managing access to resources considering the jobs of individual clients inside an association. The principal job of RBAC is to rearrange and streamline the administration of client permissions by assigning jobs rather than individual authorizations to each client. This approach ensures that clients have fitting access in view of their work abilities and commitments.
-   Multi-Factor Authentication (MFA): MFA is a security mechanism that anticipates that clients should give something like at least two verification factors to gain access to a resource. The fundamental job of MFA is to decrease the risk of unapproved access by ensuring that whether one approval factor is compromised, other factors are expected to gain access.

## Security Information and Event Management (SIEM)
-   Purpose: Security Information and Event Management (SIEM) is a far-reaching way to deal with cyber security that solidifies Security Information Management (SIM) and Security Event Management (SEM) to give ongoing examination, checking, and response to security occasions inside an association. The principal job of SIEM is to further develop a network security present by giving integrated detectable quality into network activities, recognizing potential security risks, and enabling speedy response to incidents.
  
## Features:
-   Log Management: Log management alludes to the process of gathering, storing, and dissecting log data made by various devices, applications, and structures inside a network. SIEM structures assemble log data from many sources, including network devices (switches, routers), security machines (firewalls, IDS/IPS), servers, applications, and endpoint gadgets.
-   Event Correlation: Event correlation is the technique associated with analysing and comparing log data from different sources to recognize patterns and distinguish potential security risks. SIEM systems use predefined rules, heuristics, and advanced assessment to correlate events and make critical security alerts.
-   Incident Response: Incident Response alludes to the activities started by a university to recognize, inspect, and answer security events. SIEM frameworks have a basic impact in working with and mechanizing the incident reaction process.

## Patch Management
-  Purpose: The purpose of patch management is to guarantee that product and frameworks are up to date with the latest patches and updates. This is urgent for keeping up with the security, stability, and performance of systems.
  
## Process:
-  Inventory Management: Inventory management includes maintaining a comprehensive list of all products, applications, and frameworks inside an organization.
-  Patch Deployment: Patch deployment is the process of applying patches to programming and frameworks to address weaknesses, fix bugs, or improve functionality.
-  Testing: Testing includes approving that patches and updates are applied accurately and don't present new issues or conflicts.

## Vulnerability Testing

Vulnerability Testing was done of KN University web server using Nmap and Nessus.

 ![image](https://github.com/user-attachments/assets/051e25c3-0a3f-46dd-b683-46370ff2bfb0)

Fig: Vulnerability Testing

### Nessus testing for vulnerabilities
![image](https://github.com/user-attachments/assets/37c1b552-68f8-4396-97c8-1bfa81438611)

 
### Nessus Scan Report – Vulnerability by Host 
 ![image](https://github.com/user-attachments/assets/a02eb142-ba06-4a53-a0c0-1a2bdd1a8abc)
 ![image](https://github.com/user-attachments/assets/5aee3ed7-85a6-438d-88d8-61f17eb3f30a)


INFO
N/A	-	110723 Target Credential Status by Authentication Protocol - No Credentials Provided
 
* indicates the v3.0 score was not available; the v2.0 score is shown

 
## Policies and Procedures
At KN University, the Policies and Methods segment frames fundamental principles and rules that govern network security, data protection, and client conduct to guarantee a solid, consistent, and well-working IT infrastructure. Here is a breakdown of key components:
-  Network Security Policy: The Network Security Policy lays out rules for shielding the university's network from unapproved access, data breaches, and other security dangers. This guarantees that main approved people with explicit jobs and obligations approach the organization assets they need to play out their duties. The network security policies for KN University are:
-  Access Control: Clients (students, staff, or any clients) are allowed admittance to just the network assets essential for their jobs. For example, staff individuals could approach student records, while students just access individual academic data.
-  Patch Management: Consistently update and patch software, systems, and network devices to safeguard against known weaknesses.
-  Data Encryption: Encrypt sensitive data, including student records and exploration information, both in transit and at rest.
- Incident Response Plan: This plan frames the steps the university will take to answer security incidents, for example, network breaks, data breach, or cyberattacks. The objective is to rapidly distinguish and relieve dangers while limiting harm and interruption to the university's activities. 
Steps for incident response:
-	 Detection: Identifying the presence of a potential security incident.
-	 Investigation: Assessing the nature and effect of the incident.
-	 Containment: Making quick moves to restrict the spread of the danger.
-	 Eradication: Eliminating the reason for the incident (e.g., malware, unapproved access).
-	 Recuperation: Reestablishing ordinary tasks and securing systems against future incidents.
-	 Illustrations Learned: Post-incident audit to comprehend what turned out badly, report upgrades, and improve future response procedures.
   
## Data Protection Policy:
This arrangement establishes the legitimate administration, characterization, and handling of data inside KN College, guaranteeing consistency with nearby and worldwide guidelines like GDPR. Information security measures are basic in forestalling unapproved admittance to delicate data, such as student records, research information, or financial transactions.

### Key Parts:
-  Data Arrangement: Characterizing data classifications given awareness (e.g., public, interior, confidential).
Taking care of Methodology: Rules for storing, communicating, and sharing information safely, including encryption and access controls.
-  User Training: KN University focuses on teaching clients about normal security dangers and best practices. Normal instructional meetings are led for the two students and staff, covering fundamental subjects to assist them with remaining educated and cautious.
  
### Training Subjects:
-  Phishing Awareness: Recognizing and avoiding email and electronic phishing endeavours that look to take individual data.
Password Management: Best practices for creating strong passwords, utilizing password managers, and shielding login certifications.
-  Safe Web Use: Rules for safe perusing, perceiving malevolent sites, and keeping away from dangerous internet-based conduct.
These approaches and strategies intend to defend KN University's IT frameworks, safeguard information, and engage clients to act dependably inside the network. They contribute to a safe environment that is helpful for scholarly and administrative functions.



## Network Security Policies:

### Access Control Policy

 ![image](https://github.com/user-attachments/assets/d98d8689-8dac-4381-98d5-97d26ee603aa)

Fig 1: Access Control Policy

![image](https://github.com/user-attachments/assets/36e79c7e-24c8-4a22-a5c3-8a1051707cc9)

 Fig 2: Access Control Methods and Security

 ![image](https://github.com/user-attachments/assets/539b9094-5ac2-4b51-8e8a-750e6ec737e9)

Fig 3: Policy Enforcement

### Data Backup and Redundancy Policy

 ![image](https://github.com/user-attachments/assets/269ad2c6-26c2-4732-a664-f9f9ab9d71e2)

Fig 4: Data Backup and Redundancy Policy

![image](https://github.com/user-attachments/assets/8f4fdb2f-b102-4361-a278-bc9cf4772926)

 Fig 5: Data Redundancy and Security

![image](https://github.com/user-attachments/assets/683fd263-ad94-4b8b-8e5d-b5ef0d8906ad)

 Fig 6: Disaster Recovery


### Device and Endpoint Security Policy

 ![image](https://github.com/user-attachments/assets/b2160c41-d775-4b38-b3f5-fb75bef26bda)

Fig 7: Device and Endpoint Security

![image](https://github.com/user-attachments/assets/fe9684ff-6a9e-42d6-ab9e-c0af77577266)

 Fig 8: Authentication and Endpoint Monitoring

 ![image](https://github.com/user-attachments/assets/3e10d46d-f883-4b73-865c-4d6c7628b70c)

Fig 9: Data Loss Prevention


### Physical Security Policy

 ![image](https://github.com/user-attachments/assets/3e061be8-d6f2-4341-ad50-19b5f01e989c)

Fig 10 : Physical Security

 ![image](https://github.com/user-attachments/assets/e6b25b1a-4f81-40e8-b739-ac1ae4d0422b)

Fig 11: Key Administration and Security Awareness

### Incident Response Policy

![image](https://github.com/user-attachments/assets/f947df80-0cad-4ede-9161-36ae6a2977be)

 Fig 12: Incident Response

 ![image](https://github.com/user-attachments/assets/7c126bf2-bad7-43a3-ad94-dae9e95d424b)

Fig 13: Incident Reporting

 
## Risk Management

Purpose: Risk assessment is a fundamental part of risk management. Its principal job is identifying, evaluating, and focusing on dangers to an affiliation's assets, assignments, and objectives. By understanding these risks, affiliations can foster methodologies to mitigate or manage them effectively, ensuring the continuity and strength of their activities.

 ![image](https://github.com/user-attachments/assets/7b4e8bae-74e5-4388-8a87-8c6f72e18077)

Fig: Risk Assessment

### Risk Mitigation
Risk mitigation implies implementing methodologies and exercises to diminish the probability and impact of recognized risks. The goal is to restrict risks and shortcomings, shielding network assets, errands, and objectives. Convey firewalls to control and screen network traffic, forestalling unapproved access and mitigating external risks. Sporadically survey and update security approaches and strategies to ensure they stay significant and fruitful in watching out for current risks. Provide training on broad security works, including perceiving phishing endeavours, safe web use, and genuine treatment of sensitive information.


### Risk Analysis
Risk analysis at KN University implies distinguishing, surveying, and mitigating expected dangers to its IT framework, data, and activities. Key dangers incorporate cybersecurity threats (e.g., data breaks), functional interruptions, information security concerns, and physical hazards. Risks are assessed in view of probability and effect, with high-priority dangers, for example, data breaches or system blackouts getting the most consideration. Mitigating procedures incorporate cybersecurity measures, regular data backups, disaster recuperation plans, and client training. Nonstop observing, reviews, and clear communication guarantee that the risk management interaction adjusts to new difficulties, helping shield the university's systems and data.

### Continuous Monitoring 
Constant checking incorporates the consistent impression of a college's IT environment to recognize and answer security risks and execution issues dynamically. Network observing gadgets track the exhibition, availability, and security of the network system. They give pieces of information about network traffic, device status, and potential issues that could influence network performance or security.
