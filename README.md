<p align="center">

<h1>Configuring DNS A-Records and DNS Cache</h1>
The objective of this project was to observe what happens when a client attempts to resolve a hostname that doesn't have a DNS record, create a record for the hostname, and then observe how the DNS cache affects changes to the record.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>

<p>
<img width="811" height="479" alt="(DNS) ping mainframe fail" src="https://github.com/user-attachments/assets/bc90617b-b21b-4bb9-9e04-8baad3d03f14" 
/>
</p>
<p>
On my client virtual machine, I attempted to ping “mainframe”, but because there was no DNS record associated with “mainframe,” the ping ultimately failed.
</p>
<br />

<p>
<img width="701" height="486" alt="(DNS) adding mainframe to dns server" src="https://github.com/user-attachments/assets/2282a88a-4856-4449-95cb-7da3c8d16f6e" />

</p>
<p>
I switched over to my domain controller virtual machine, which was also functioning as the DNS server in the virtual network.

In the domain controller, I created an A record for mainframe and mapped it to the IP address of the DNS server/domain controller

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
