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
Login to the Domain Controller and enable ICMPv4 in on the local windows Firewall.
</p>
<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/5eb81af0-dcf3-4330-bd2e-ff08eeec6ad3" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />



<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />




<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />





<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />





<p>
<img src="https://github.com/Luis-G-Cordero/configure-ad/assets/135280915/dba74b4d-fe52-4b96-8e82-ccaaf55c458a" height="60%" width="60%" alt="Steps"/>
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”..
</p>
<br />
