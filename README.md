# Project-Obelisk
## An Active Directory Virtualization Project between a Windows Server virtual machine and 2 client virtual machines running Windows 11 Enterprise  

![All the virtual machines](https://github.com/NowlinB/Project-Obelisk/assets/38094031/bc26da95-27e4-4afe-894a-6b2ef9d28cdf)     

# Table of Contents
[Goals](#goals)   

[Initial Setup](#initial-setup)      

[Group Policy](#group-policy)   

[Remote Desktop](#remote-desktop)

## Goals for the Project  <a name="goals"></a>
To create an identity and access management solution for a fictitious company called Obelisk.     

To simulate an enterprise domain environment while ensuring security best practices. This will be achieved through the management of group policy and implementation of the principle of least privilege.
## Initial Setup  <a name="initial-setup"></a>
I started with the creation of the Windows server vm. After installing the os I added active directory to the roles and features.  

After the clients operating systems were installed on the vms a static ip address was configured representing the dns server on the server vm.   

![Changing Users DNS Server to Use the Windows Server's DNS](https://github.com/NowlinB/Project-Obelisk/assets/38094031/e0bf4a2a-c75e-4696-9a56-8452bf9e54dc)

All of the vms are able to communicate with one another since they are on the same nat network of 10.0.2.0/24. 

Next I created the user accounts that the clients will need to log in to the domain after joining it.  

 ![Created Users](https://github.com/NowlinB/Project-Obelisk/assets/38094031/36231110-6f63-451d-a237-b223c353ec76)  
  
Now that the users were created I then joined each client to the domain.  

![Joining Users to Domain](https://github.com/NowlinB/Project-Obelisk/assets/38094031/4474b509-bdc7-48a3-b2a7-95a79ccdc87b)


![User Domain Login](https://github.com/NowlinB/Project-Obelisk/assets/38094031/a157e52f-fd13-4f95-88f1-61c9636239fe)   

As we can see the client is now apart of the local domain, named obelisk.

     
## Group Policy  <a name="group-policy"></a>

The group policy on the Windows server follows the naming convention U_Policy and C_Policy for indicating user and computer configuration respectively.

Each policy only does one thing which aims to simplify management and to make future changes much easier.  

![Group policy examples](https://github.com/NowlinB/Project-Obelisk/assets/38094031/94eb8d91-61ad-4e4c-a5ad-641704164b3d)  

For example here is a policy created to block users from accessing the command line, powershell, and powershell ise.

![Block powershell and cmd](https://github.com/NowlinB/Project-Obelisk/assets/38094031/78b5a374-f7af-4018-b7c3-b16756b501c0)   


A sample of the audit policy whereby I have configured auditing for account lockouts, successful logons, successful and failed logoffs and finally special logons. (administrative equivalent privileges)    

![Audit Policy Sample](https://github.com/NowlinB/Project-Obelisk/assets/38094031/307c3410-de59-4c70-a681-af063d318a8d)     

## Remote Connection   <a name="remote-desktop"></a>

I setup remote desktop connections on both computers to allow the server to remotely connect to either client through the privileged domain admin user account named brandon.nowlin@obelisk.local  

![Setting up remote desktop on the client pcs](https://github.com/NowlinB/Project-Obelisk/assets/38094031/bcb46c1f-04a6-4221-a1d1-621e3c3c8543)   

Now I am remoting into client 2 from the Windows server  

![Remoting in to User 2 on the Windows Server](https://github.com/NowlinB/Project-Obelisk/assets/38094031/615c2bf6-3cd6-4a58-8338-85acf5c3385d)  

And success!  

![Remote Connection Success](https://github.com/NowlinB/Project-Obelisk/assets/38094031/301c4d85-582d-4849-a537-f9e5b16710f0)



