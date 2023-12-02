<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)
- Powershell

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create 2 virtual machines (windows 10 & linux)
- Use microsoft remote desktop to connect to VM1 (windows 10)
- Install wireshark
- Use wireshark, powershell and VM2's private IP address to inspect network traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/bOFzGU1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After downloading wireshark, it launched successfully. Live traffic was reciprocated. 
</p>
<br />

<p>
<img src="https://i.imgur.com/wmsB7Mj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I was able to block ICMP's traffic on VM2's firewall by creating a inbound security role in VM's network security group and denying the traffic. The ping timed out and VM2 was unable to receive it and send a reply. I then went back and allowed ICMP traffic again.  
</p>
<br />

<p>
<img src="https://i.imgur.com/Oosw72n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To find out some of the IP addresses that disney.com uses, I asked the DNS server using nslookup. 
</p>
<br />

<p>
<img src="https://i.imgur.com/zulH3PT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Lastly, I observed RDP traffic using tcp.port == 3389. Although you're unable to see the movement, the traffic was busy because there's was a live RDP session on my computer to VM1. Any movement or action that was made allowed the traffic to keep going. 
</p>
<br /
