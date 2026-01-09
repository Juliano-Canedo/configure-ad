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

- Step 1: Set (DC-1) Domain Controller’s NIC Private IP address to be static
- Step 2: Set Client-1’s DNS settings to DC-1’s Private IP address
- Step 3: Ping DC-1’s private IP address to ensure the connectivity
- Step 4: Open PowerShell and run ipconfig /all -
The output for the DNS settings should show DC-1’s private IP Address


<h2>Actions and Observations</h2>

<p>
<img width="2992" height="1934" alt="image" src="https://github.com/user-attachments/assets/7990e396-1dba-4020-8dc8-d99e9406654a" />

</p>
<p>
After creating both Virtual Machines (Server and client) in your Azure portal, go to: Virtual Machines - Select the Server (DC-1) - Click on Networking, Network Settings - Click on Network Interface / IP configuration - Click on ipconfig1 and under Private IP address settings change your allocation from Dynamic to Static and assing the correct IP address (10.0.0.4) then click SAVE.
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
<br /># configure-ad
