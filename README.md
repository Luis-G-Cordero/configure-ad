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
