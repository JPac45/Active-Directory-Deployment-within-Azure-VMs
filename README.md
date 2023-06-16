
<p align="center">
<img src="https://i.imgur.com/RYQyOsV.png"/>
</p>

<h1>Active Directory Deployment within Azure VMs</h1>
This tutorial will demonstrate the functionality of Active Directory by creating an Admin user and Organizational Units and allowing the user access into the domain.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Windows Server 2022

<h2>Prerequisites</h2>

This tutorial assumes you have already created a Win10 VM and Windows Server 2022(Domain Controller) VM.  <a href="https://github.com/JPac45/Creating-VMs-within-Azure">CLICK HERE</a> for the VM Creation Tutorial.   Active Directory will be installed on the Windows Server 2022 VM, while the Win10 VM will be used to gain access to the Domain Controller.


<h2>Configuring IP addressess on both VMs</h2>
<p>
<b>
This is needed to make sure both VMs are on the same Virtual Network.

  Within Azure Virtual Machines, select the Windows Server 2022 VM:</b>
  
- Click on the Windows Server 2023 (In this example, it is named DC-1)
- Click Networking under settings on the left
- Click the highlighted link after Network Interface:
- Click IP configurations under settings on the left
- Under Private IP Address, Click on the word Dynamic
- Click on Static and then Save to make the IP address static
 

<p>
<img src="https://i.imgur.com/ZYbzgnt.gif"/>
</p>
<br />

<p>
<b> Within Azure Virtual Machines, we need to make sure both the Domain Controller and Client are on the same Virtual Network:</b>
  
- Click on either Domain Controller DC-1 or the Client
- Check under Virtual network/subnet and make note of the Virtual Network to make sure both are the same

  
<p>
<img src="https://i.imgur.com/kwpwubM.gif"/>
 
</p>
<br />

<p>
<b>Ensure Connectivity between the Client and Domain Controller:</b>
  
- Get Client's Public IP address within Azure
- Open Remote Desktop Connection from your desktop, and use Client's IP address from above to connect to the Client VM. (You must also have the client userid and password when you created this Client VM earlier, to gain access via Remote Desktop Connection.)
- Copy DC-1 Public IP address and Private IP address within Azure
- Open Remote Desktop Connection from your desktop, and use DC-1 IP address from above to connect to the DC-1 VM. (You must also have the DC-1 userid and password when you created this DC-1 VM earlier.)
- In order to Ping DC-1 from Client, ICMP traffic has to be allowed through its firewall. Open Windows Defender Firewall with Advanced Security via search bar.
- Click Inbound Rules on the left, Sort Protocol and look for ICMPv4. Then Enable the two rules named "Core Networking Diagnostics -ICMP Echo Request (ICMPv4-In)"
- Get Client's Public IP address with Azure 
- Get Client's Public IP address with Azure 
- Check under Virtual network/subnet and make note of the Virtual Network to make sure both are the same
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<h2>Installing Active Directory on Domain Controller</h2>
<p>
<b>

- Click Create 
- Click Azure Virtual Machine
- Choose an existing Resource Group that you previously created
- Give the VM a name
- Select the region (it should be the same as the resource group)
- Select Windows 10 under Image
- Choose Standard size
- Create username and password; and confirm password
- Click Create once validation is passed VM will be created.</b>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. 
</p>
<br />

<h2>Creating Admin User and Organizational Units</h2>
<p>
<b>

- Click Create 
- Click Azure Virtual Machine
- Choose an existing Resource Group that you previously created
- Give the VM a name
- Select the region (it should be the same as the resource group)
- Select Windows 10 under Image
- Choose Standard size
- Create username and password; and confirm password
- Click Create once validation is passed VM will be created.</b>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. 
</p>
<br />

<h2>Creating Admin User and Organizational Units</h2>
<p>
<b>

- Click Create 
- Click Azure Virtual Machine
- Choose an existing Resource Group that you previously created
- Give the VM a name
- Select the region (it should be the same as the resource group)
- Select Windows 10 under Image
- Choose Standard size
- Create username and password; and confirm password
- Click Create once validation is passed VM will be created.</b>
<p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. PLACE MY OWN TEXT HERE. 
</p>
<br />
