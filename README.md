<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create 2 Virtual Machines 
- Observe ICMP Traffic
- Observe DNS Traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/KZy9Dni.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Utilizing an Azure subscription we will need to create two Virtual machines, One running on windows 10 and the other running Linux. Then obtain the IPAdress of VM 1 (Windows) and access via remote desktop tool. 
</p>
<br />

<p>
<img src="https://i.imgur.com/44rgO4R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install Wire Shark in order allow us to view traffic flow between virtual machines. First we will want to observe ICMP Traffic by filtering out all other traffic, to do this we will enter "ICMP" into the filter window. At first there will not be anything displayed as there will not be any traffic from ICMP. The reason for this is ICMP is used to ping for connectivity. To create traffic we will have to obtain the IP address from the other VIrtual Machine to send a ping to Virutal Machine 1, then creating traffic between the two as they will then be communicating.
</p>
<br />

<p>
<img src="https://i.imgur.com/t4P0WFw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
with allowing traffic we are also capable of "blocking" traffic by setting specific rules within the network security groups. For this we would open up the inbound security rules for the Virtual Machine and select "deny" access from any source trying to execute the ICMP protocol. This can be done universally.
</p>
<br />
