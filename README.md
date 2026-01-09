<p align="center">
<img width="1152" height="522" alt="image" src="https://github.com/user-attachments/assets/0dfcaffc-1813-4a2d-ade9-046472f258b0" />

</p>

<h1>  DNS CONFIGURATION</h1>
In this tutorial, within Azure Virtual Network, for a client to join a domain, I will configure the client's DNS IP Address to the same IP address as the Domain Controler. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools

<h2>Operating Systems Used </h2>

- Windows 11 Pro, Version 25H2 - x64 Gen2
- Windows Server 2025 Datacenter: Azure Edition - x64 Gen2

<h2>High-Level Steps</h2>

- Step 1: Creat a Virtual Network - Create 2 Virtual Machines (server and client) ensure they are in the Virtual Network we 1st created
- Step 2: Set (DC-1) Domain Controller’s NIC Private IP address to be static
- Step 3: Set Client-1’s DNS settings to DC-1’s Private IP address
- Step 4: Ping DC-1’s private IP address to ensure the connectivity
- Step 5: Open PowerShell and run ipconfig /all -
The output for the DNS settings should show DC-1’s private IP Address


<h2>Actions and Observations</h2>

<p>
<img width="1024" height="768" alt="1st slide" src="https://github.com/user-attachments/assets/a97ad6d5-b935-4892-a61a-c9d9e28f960a" />

</p>
<p>
Click on Virtual Network, click on Creat, select subscription, name it “Active-Directory-Vnet” click Review and Create. Following the same steps click on Virtual Machines and create a server and a client (observe “operating systems used” for specifics). Under Networking ensure to choose “Active-Directory-Vnet” for both Virtual Machines.


</p>
<br />


<p>
<img width="2992" height="1934" alt="image" src="https://github.com/user-attachments/assets/7990e396-1dba-4020-8dc8-d99e9406654a" />

</p>
<p>
After creating both Virtual Machines (Server and client) in your Azure portal, go to: Virtual Machines - Select the Server (DC-1) - Click on Networking, Network Settings - Click on Network Interface / IP configuration - Click on ipconfig1 - under Private IP address settings, change your allocation from Dynamic to Static and assign the correct IP address (10.0.0.4) then click SAVE. The Reason for setting up a Static IP addresses is for stability, reliability, and easier remote access to specific devices or services like web/email servers, NAS drives, printers, or VPNs, ensuring they are always reachable at the same address for consistent connections, DNS resolution, and controlled network access. Unlike dynamic IPs that change, a static IP provides a permanent digital address, crucial for hosting services, reliable data transfers, IP allowlisting, and simplifying network management.
</p>
<br />


<p>
<img width="1496" height="967" alt="client DNS" src="https://github.com/user-attachments/assets/d09a9eac-86d3-4f8a-b6f6-83c523759c31" />

</p>
<p>
Go to Virtual Machines and select client-1 - click on Networking - click Network Settings - click Network interface / IP configuration - click DNS Servers - click Custom and change it to your DC-1 Private IP in this case (10.0.0.4). Click SAVE. (From observing the previous slide we can see the Private IP for DC-1)
</p>

<p>
<img width="1109" height="280" alt="Screenshot 2026-01-08 at 7 31 12 PM" src="https://github.com/user-attachments/assets/0db3184b-4bc9-43e3-b5f9-a39e95ac1e65" />

</p>
<p>
Copy the  Public Ip Address for the client VM and log into your Remote Desktop with you user name and password. Run Power Shell and use the command: ping 10.0.0.4 
</p>
<br /># configure-ad
