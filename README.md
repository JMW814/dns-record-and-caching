<p align="center">

<h1>Configuring DNS A-Records and DNS Cache</h1>
The objective of this project was to observe what happens when a client attempts to resolve a hostname that doesn't have a DNS record, create a record for the hostname, and then observe how the DNS cache affects changes to the record.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- DNS Manager
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
<img width="748" height="443" alt="(DNS) mainframe sucess" src="https://github.com/user-attachments/assets/c1d6da76-b94e-48d1-b9f6-1a3dc918f21c" />

</p>
<p>
 I returned to the client virtual machine to nslookup “mainframe’ and ping it.

The nslookup correctly showed “mainframe” as the domain controller, and the ping was also successful, meaning that DNS was now able to resolve “mainframe” to the domain controller's IP address.

</p>
<br />

<p>
<img width="1648" height="919" alt="image" src="https://github.com/user-attachments/assets/ce200daf-ad31-44e7-9e36-de8541eac3b7" />

</p>
<p>
Next, I went back into the domain controller and updated the mainframe A record to now resolve to Google’s web server instead of the domain controller.
</p>
<br />

<p>
<img width="1406" height="818" alt="image" src="https://github.com/user-attachments/assets/7573cebf-5485-4378-b7dd-2b7cc21e7f3f" />

</p>
<p>
I returned to the client virtual machine and pinged “mainframe” again.
Even though the A record on the DNS server had been changed, the client continued to resolve “mainframe” to the old IP address.
 
This occurred because the client had cached the previous DNS response. The client did not immediately need to ask the DNS server for the hostname again because it already had a cached result.

</p>
<br />

<p>
<img width="1325" height="789" alt="image" src="https://github.com/user-attachments/assets/4c88941f-b462-457d-90da-27788b81bf13" />


</p>
<p>
Finally, to remove the now-outdated DNS info, I used ipconfig /flushdns to clear the DNS cache so the client can now receive the updated DNS info.

I then re-pinged “mainframe,” and it then successfully resolved to Google’s web server.

</p>
<br />
<h2>Conclusion</h2>
This project demonstrated the complete process of DNS name resolution by failing to find a name, creating an A record, successfully resolving the hostname, changing the record, observing how the DNS cache works, and then clearing the cache to receive the updated DNS information
