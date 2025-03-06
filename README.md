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
Now open up the windows firewall and turn off domain profile - private & public profile hit apply and okay
<img src="https://i.imgur.com/poOecP5.png"/>
<br />
<br />
Next we go back on our local computer and pin our VM's IP using the terminal so it can be reached via the internet:  <br/>
<img src="https://i.imgur.com/z1fNrzP.jpeg"/>
Now we go back to our VM and open up Event viewer and we can start seeing all these different attempts to login 
<img src="https://i.imgur.com/uqrJ2mR.png"/>
Next we go back to Azure and create a new log analytics
<img src="https://i.imgur.com/0Odywt3.png"/>
Now we open Microsoft Sentinel on Azure and add our log analytics into the workspace
<img src="https://i.imgur.com/kuC0gSi.png"/>

<img src="https://i.imgur.com/0Odywt3.png"/>
<img src="https://i.imgur.com/0Odywt3.png"/>
<img src="https://i.imgur.com/0Odywt3.png"/>
<img src="https://i.imgur.com/0Odywt3.png"/>
<img src="https://i.imgur.com/0Odywt3.png"/>
<img src="https://i.imgur.com/0Odywt3.png"/>
<img src="https://i.imgur.com/0Odywt3.png"/>
<br />
<br />
As you can see, it displays the recorded keystrokes of the credentials!:  <br/>
<img src="https://i.imgur.com/QdLbxvx.png"/>
<br />
<br />
Now there you have a simple keylogger built with Python using Pycharm, capturing and logging keystrokes for educational purposes. Remember to use this knowledge ethically and responsibly 😁
</p>


