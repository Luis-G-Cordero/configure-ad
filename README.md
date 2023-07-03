<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

  

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)



<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/1c585577-f0d1-402f-92ef-3525a30c6885" height="60%" width="60%" alt=Steps/>
</p>
<p>
To start off, create a virtual machine that will be used for the Domain controller. Name the virtual machine "DC-1".
</p>
<br />



<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/2cc34cbe-25fe-4a62-b699-0bd8c8a21d7d" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Next, Set Domain Controller’s NIC Private IP address to be static.
</p>
<br />





<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
</p>
</p>
</p>
</p>

<br />



<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/97e49057-1fbf-4b49-aa78-dbdeb55e5d2e" height="60%" width="60%" alt="Steps"/>
</p>
<p>
</p>

<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/343d1ec5-80fe-4563-90f5-522d35791e52" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Ensure that both VMs are in the same Vnet.
</p>
</p>
</p>
</p>
</p>
</p>
</p>
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/4cb8f1d4-1c36-47b2-ae3d-b46cc9574850" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Login to Client-1 with Remote Desktop and ping DC-1’s private IP address with ping -t (ip address) (perpetual ping).
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/73d4e056-cab4-420c-9bc0-6483c0b0bb19" height="60%" width="60%" alt="Steps"/>
</p>
<p>
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/5eb81af0-dcf3-4330-bd2e-ff08eeec6ad3" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Login to the Domain Controller and enable ICMPv4 in on the local windows Firewall.
</p>
</p>
</p>
</p>
</p>
</p>
</p>
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/81227e07-0dff-4dc8-9bb4-1023dfa620f4" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Check back at Client-1 to see the ping succeed.
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/ddd3ba7f-d498-432d-a96a-17c12b8d899c" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Login to DC-1 and install Active Directory Domain Services.
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/4b4f7c62-0099-4e5b-ab9f-89c1bfd94d2b" height="60%" width="60%" alt="Steps"/>
</p>
<p>
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/26146473-8419-4f00-bd33-5e1dfea56940" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is). Complete all sections on the left by clicking next until you click install. Once installation is complete, the virtual machine will restart and you'll log back in as "mydomain.com\labuser" and use whatever password you created during the installation process.
</p>
<br />



<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dd879aeb-b70d-460f-9e66-0d76e3594d72" height="60%" width="60%" alt="Steps"/>
</p>
<p>
In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”.
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />





<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/6b37247d-ae40-4ced-a144-b28e50def69e" height="60%" width="60%" alt="Steps"/>
</p>
<p>
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/1028a6ca-5610-4a5c-a7cd-50233c2ea7d6" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new employee named “Jane Doe” (same password) with the username of “jane_admin”.
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/fbc097b2-be29-46d3-8c80-48d403ce2978" height="60%" width="60%" alt="Steps"/>
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/3e594844-b8b7-49e4-9478-3af5cacb5326" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Add jane_admin to the “Domain Admins” Security Group.
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d2c5a85e-d5c3-45c1-95ff-2e7a59287899" height="60%" width="60%" alt="Steps"/>
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/f39bf070-5005-4551-a0f6-479e25386929" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Log out/close the Remote Desktop connection to DC-1 and log back in as “mydomain.com\jane_admin”. Use jane_admin as your admin account from now on.
</p>
<br />





<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/36acf6c2-31a8-47a8-84d7-554976209d74" height="60%" width="60%" alt="Steps"/>
</p>
<p>
From the Azure Portal, set Client-1’s DNS settings to the DC’s Private IP address.
</p>
<br />





<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/acfbf7e8-3f7b-4500-9b67-0c4091a9605e" height="60%" width="60%" alt="Steps"/>
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/0744d44a-2242-4c96-a728-07dea4193f53" height="60%" width="60%" alt="Steps"/> 
<p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d2ae865e-bef0-4ac9-b0f1-6e92cd1d09ee" height="60%" width="60%" alt="Steps"/> 
<p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/f3b47692-5ce8-4b30-bb84-47ee24e73670" height="60%" width="60%" alt="Steps"/> 
<p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/ea9c30c6-4b65-47ff-9430-d9635920f33f" height="60%" width="60%" alt="Steps"/> 
<p>
Login to Client-1 (Remote Desktop) as the original local admin (labuser) and join it to the domain (computer will restart).
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/de27f42b-9d71-4818-a611-3aea07833cdc" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Login to the Domain Controller (Remote Desktop) and verify Client-1 shows up in Active Directory Users and Computers (ADUC) inside the “Computers” container on the root of the domain.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/afd5254d-bcf8-4692-a79b-c39ac7ab0ae5" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_CLIENTS” and drag Client-1 into there.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/62fe9c64-3a46-4122-9bc2-1dc71a5b85bb" height="60%" width="60%" alt="Steps"/>
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/71e9e0ce-90ba-425f-aad8-d50e2f199d98" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Log into Client-1 as mydomain.com\jane_admin and open system properties. Click “Remote Desktop”, allow “domain users” access to remote desktop.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />






<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/d4dee933-3ad8-4dc5-bdb9-3a902beafaae" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create a new OU named “_ADMINS”.
</p>
<br />
