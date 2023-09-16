# Project-Obelisk (Currently In Progress)
## An Active Directory Virtualization Project between a Windows Server virtual machine and 2 client virtual machines running Windows 11 Enterprise  

![All the virtual machines](https://github.com/NowlinB/Project-Obelisk/assets/38094031/bc26da95-27e4-4afe-894a-6b2ef9d28cdf)     

## Goals for the Project
To create an identity and access management solution for a fictitious company called Obelisk.     

To simulate an enterprise domain environment while ensuring security best practices. This will be achieved through the management of group policy and implementation of the principle of least privilege
## Initial Setup
I started with the creation of the Windows server vm. After installing the os I added active directory to the roles and features.  

After the clients operating systems were installed on the vms a static ip address was configured representing the dns server on the server vm   

![Changing Users DNS Server to Use the Windows Server's DNS](https://github.com/NowlinB/Project-Obelisk/assets/38094031/e0bf4a2a-c75e-4696-9a56-8452bf9e54dc)

All of the vms are able to communicate with one another since they are on the same nat network of 10.0.2.0/24  

Next I created the user accounts that the clients will need to log in to the domain after joining it  

![Created Users](https://github.com/NowlinB/Project-Obelisk/assets/38094031/16c9df92-cdac-4904-9736-7041f56d0afa)  

Now that the users were created I then joined each client to the domain  

![Joining Users to Domain](https://github.com/NowlinB/Project-Obelisk/assets/38094031/4474b509-bdc7-48a3-b2a7-95a79ccdc87b)


![User Domain Login](https://github.com/NowlinB/Project-Obelisk/assets/38094031/a157e52f-fd13-4f95-88f1-61c9636239fe)   

As we can see the client is now apart of the local domain, named obelisk

     
## Group Policy 
![Audit Policy Sample](https://github.com/NowlinB/Project-Obelisk/assets/38094031/307c3410-de59-4c70-a681-af063d318a8d)    


A sample of the audit policy whereby I have configured auditing for failed logon attempts, successful logins, successful and failed logoffs and finally special logons (administrative equivalent privileges)
