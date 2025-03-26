<h1>EDR HOME LAB: ATTACK & DEFENSE </h1>



<h2>Description</h2>
This project sets up an Endpoint Detection and Response (EDR) home lab using Microsoft Azure, Sentinel, and a Windows VM. We will deliberately expose our firewall to the internet, allowing real-world attack attempts. The goal is to analyze and visualize incoming threats using a Security Information and Event Management (SIEM) system. The SIEM dashboard will display attacker locations and failed login attempts. This project is for educational and research purposes, helping to understand real-world cyber threats and how to detect, monitor, and respond effectively.


<h2>Utilities Used</h2>

- <b>Microsoft Azure</b> 
- <b>Windows WM</b>


<h2>Program walk-through:</h2>

<p align="center">
Launch Azure on your preferred browser: <br/>
<img src="https://i.imgur.com/pnZoj39.png"/>
<br />
<br />
Create a new resource group:  <br/>
<img src="https://i.imgur.com/kmeTBLJ.png"/>
<br />
<br />
Create a Virtual Machine: <br/>
<img src="https://i.imgur.com/iNFVqNA.png"/>
  <img src="https://i.imgur.com/QvdgWia.png"/>
  <img src="https://i.imgur.com/Uq4hi4f.png"/>
  <img src="https://i.imgur.com/X4aE60A.png"/>
  
<br />
<br />
Configure VM Firewall inbound rule to any:  <br/>
<img src="https://i.imgur.com/VOMH05e.png"/>
<img src="https://i.imgur.com/ehyUepy.pngg"/>
<br />
<br />
Now launch a Remote Desktop Connection Using the Windows App and enter the admin credentials of the VM:  <br/>
<img src="https://i.imgur.com/Gxa0Rig.png"/>
<img src="https://i.imgur.com/mmpQU9f.png"/>
Now we are logged into the Windows VM:
<img src="https://i.imgur.com/AsOFOVz.png"/>
Now open up the Windows firewall and turn off the domain profile - private & public profile, hit apply, and okay
<img src="https://i.imgur.com/poOecP5.png"/>
<br />
<br />
Next, we go back to our local computer and pin our VM's IP using the terminal so it can be reached via the internet:  <br/>
<img src="https://i.imgur.com/z1fNrzP.jpeg"/>
Now we go back to our VM and open up Event Viewer, and we can start seeing all these different attempts to log in 
<img src="https://i.imgur.com/uqrJ2mR.png"/>
Next, we go back to Azure and create a new log analytics
<img src="https://i.imgur.com/0Odywt3.png"/>
Now we open Microsoft Sentinel on Azure and add log analytics into the workspace
<img src="https://i.imgur.com/kuC0gSi.png"/>
Now head inside Sentinel > Content Hub > type 'security event' on the search bar > install Windows Security Event and then click on Manage
<img src="https://i.imgur.com/yVR2Epo.png"/>
On the Windows Security Event page > Select Windows Security Event via AMA > Click on Open Connector Page
<img src="https://i.imgur.com/FqDygVS.png"/>
On the connector page > click on ' +Create data collection rule'
<img src="https://i.imgur.com/k3ac7Cu.png"/>
Enter the rule name of choice > Select Appropriate Azure Subscription> And select the resource group > then click 'Next'
<img src="https://i.imgur.com/dU3n34X.png"/>
Then select the appropriate assigned VM > Collect 'All security Events' > Create the rule
<img src="https://i.imgur.com/nUeH9AG.png"/>
Once the rule is created, head back to the VM and wait till the status of the AzureMonitorWindowsApplication is succeeded
<img src="https://i.imgur.com/zoTsDU2.png"/>
Back to our Log Analytics > Select the appropriate. VM > Logs > New Query > In the KQL query editor, type and run ' SecurityEvent'. Now we can see that it reports all the attempted logins
<img src="https://i.imgur.com/K3hgqye.png"/>
<br />
<br />
Now we can query search for a certain user or attributes as displayed on the KQL query editor:  <br/>
<img src="https://i.imgur.com/3rvujMl.png"/>
For example, using the functions 'where' and 'project' to display the shown attributes
<img src="https://i.imgur.com/AC3ACKA.png"/>
Since  KQL doesn't show the geolocation name, we can download a free geolocation database source from GeoLite, and essentially the attacker's IP will fall into an ISP that owns a group of IP addresses in a certain region, and we will use that to display the region the attacks are coming from in our SIEM 
<img src="https://i.imgur.com/ak8yrNP.png"/>
Open up Microsoft Sentinel > Watchlist > Create a New Watchlist 
<img src="https://i.imgur.com/63dAAVQ.png"/>
Input the 'geoip' for name and alias > Select 'next' 
<img src="https://i.imgur.com/IOjEoN5.png"/>
For the source, upload the geoip csv > select network as the security key> then create
<img src="https://i.imgur.com/pSeNvOf.png"/>
We can now go back to the Watchlist we can see that 55k items have been uploaded 
<img src="https://i.imgur.com/KOqpowj.png"/>
Now we can go back to Sentinel > Workbook > Create a New Workbook > delete the prepopulated workbook, paste or type in the JSON 
<img src="https://i.imgur.com/ihqkExM.png"/>
<img src="https://i.imgur.com/vNQLpct.png"/>
<img src="https://i.imgur.com/NGKE90C.png"/>


<br />
<br />
Now there you have a simple keylogger built with Python using Pycharm, capturing and logging keystrokes for educational purposes. Remember to use this knowledge ethically and responsibly 😁
</p>


