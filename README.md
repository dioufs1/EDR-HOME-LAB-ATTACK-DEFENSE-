<h1>EDR Home Lab: Attack & Defense</h1>

<h2>Description</h2>
This project sets up an **Endpoint Detection and Response (EDR) home lab** using **Microsoft Azure, Sentinel, and a Windows VM**. The lab simulates real-world cyber threats by exposing a VM to the internet, allowing for **attack detection, monitoring, and response** using a Security Information and Event Management (SIEM) system. The SIEM dashboard visualizes attacker locations, failed login attempts, and other security insights. This project is for **educational and research purposes** to enhance cybersecurity skills.

<h2>Technologies Used</h2>
<ul>
  <li><b>Microsoft Azure</b></li>
  <li><b>Windows Virtual Machine</b></li>
  <li><b>Microsoft Sentinel</b></li>
  <li><b>Log Analytics</b></li>
  <li><b>Kusto Query Language (KQL)</b></li>
</ul>

<h2>Setup Guide</h2>

<h3>1. Set Up the Azure Environment</h3>

<p align="center">
Launch Azure on your preferred browser: <br/>
<img src="https://i.imgur.com/pnZoj39.png"/>
<br /><br />
Create a new resource group:  <br/>
<img src="https://i.imgur.com/kmeTBLJ.png"/>
<br /><br />
Create a Virtual Machine: <br/>
<img src="https://i.imgur.com/iNFVqNA.png"/>
<img src="https://i.imgur.com/QvdgWia.png"/>
<img src="https://i.imgur.com/Uq4hi4f.png"/>
<img src="https://i.imgur.com/X4aE60A.png"/>
</p>

<h3>2. Configure the Firewall</h3>
<p align="center">
Modify the VM's firewall inbound rule to allow all traffic: <br/>
<img src="https://i.imgur.com/VOMH05e.png"/>
<img src="https://i.imgur.com/ehyUepy.png"/>
</p>

<h3>3. Connect to the VM</h3>
<p align="center">
Use Remote Desktop Connection and enter the VM admin credentials: <br/>
<img src="https://i.imgur.com/Gxa0Rig.png"/>
<img src="https://i.imgur.com/mmpQU9f.png"/>
Now logged into the Windows VM: <br/>
<img src="https://i.imgur.com/AsOFOVz.png"/>
</p>

<h3>4. Disable Windows Firewall</h3>
<p align="center">
Turn off the Domain, Private, and Public profiles in Windows Firewall: <br/>
<img src="https://i.imgur.com/poOecP5.png"/>
</p>

<h3>5. Simulate Attacks</h3>
<p align="center">
From your local machine, ping the VM's public IP to simulate external access: <br/>
<img src="https://i.imgur.com/z1fNrzP.jpeg"/>
Monitor login attempts using Windows Event Viewer: <br/>
<img src="https://i.imgur.com/uqrJ2mR.png"/>
</p>

<h3>6. Integrate with Microsoft Sentinel</h3>
<p align="center">
Create a Log Analytics workspace in Azure: <br/>
<img src="https://i.imgur.com/0Odywt3.png"/>
Enable Microsoft Sentinel and link it to Log Analytics: <br/>
<img src="https://i.imgur.com/kuC0gSi.png"/>
</p>

<h3>7. Collect Security Events</h3>
<p align="center">
Go to **Sentinel > Content Hub**, search for "Security Event", and install it: <br/>
<img src="https://i.imgur.com/yVR2Epo.png"/>
Configure Windows Security Event logging via Azure Monitor Agent (AMA): <br/>
<img src="https://i.imgur.com/FqDygVS.png"/>
Create a **Data Collection Rule** to collect security events from the VM: <br/>
<img src="https://i.imgur.com/k3ac7Cu.png"/>
<img src="https://i.imgur.com/dU3n34X.png"/>
</p>

<h3>8. Run KQL Queries in Log Analytics</h3>
<p align="center">
Once data collection is active, query the logs in **Azure Log Analytics**: <br/>
<img src="https://i.imgur.com/K3hgqye.png"/>
Example query to filter failed login attempts:
<img src="https://i.imgur.com/3rvujMl.png"/>
</p>

<h3>9. Add Geolocation to Attacker Data</h3>
<p align="center">
Since KQL does not provide geolocation, download a **GeoLite** database to map attacker IPs: <br/>
<img src="https://i.imgur.com/ak8yrNP.png"/>
Create a **Watchlist** in Microsoft Sentinel to store geolocation data: <br/>
<img src="https://i.imgur.com/63dAAVQ.png"/>
Upload the **GeoLite CSV** and link it to the network security key: <br/>
<img src="https://i.imgur.com/pSeNvOf.png"/>
</p>

<h3>10. Create a SIEM Dashboard</h3>
<p align="center">
Go to **Sentinel > Workbook**, create a new dashboard, and enter the JSON query: <br/>
<img src="https://i.imgur.com/ihqkExM.png"/>
Execute the query to generate a **heatmap of attacker locations**: <br/>
<img src="https://i.imgur.com/vNQLpct.png"/>
<img src="https://i.imgur.com/NGKE90C.png"/>
</p>

<h2>Conclusion</h2>
This home lab demonstrates how to **detect, monitor, and analyze security threats** using **Azure Sentinel and KQL**. You can expand on this by integrating **custom threat intelligence feeds**, **automating responses with playbooks**, and **exploring more advanced SIEM use cases**.  

🔥 **For educational purposes only. Do not use for malicious activities!** 🔥  


