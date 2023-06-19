
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
  
- Click on the Windows Server 2023 (In this example, it is named DC-1).
- Click Networking under settings on the left.
- Click the highlighted link after Network Interface:.
- Click IP configurations under settings on the left.
- Under Private IP Address, Click on the word Dynamic.
- Click on Static and then Save to make the IP address static.
 

<p>
<img src="https://i.imgur.com/ZYbzgnt.gif"/>
</p>
<br />

<p>
<b> Within Azure Virtual Machines, we need to make sure both the Domain Controller and Client are on the same Virtual Network:</b>
  
- Click on either Domain Controller DC-1 or the Client.
- Check under Virtual network/subnet and make note of the Virtual Network to make sure both are the same.

  
<p>
<img src="https://i.imgur.com/kwpwubM.gif"/>
 
</p>
<br />

<p>
<b>Ensure Connectivity between the Client and Domain Controller:</b>
  
- Get Client's Public IP address within Azure.
- Open Remote Desktop Connection from your desktop, and use Client's IP address from above to connect to the Client VM. (You must also have the client userid and password when you created this Client VM earlier, to gain access via Remote Desktop Connection.)
- Copy DC-1 Public IP address and Private IP address within Azure.
- Open Remote Desktop Connection from your desktop, and use DC-1 IP address from above to connect to the DC-1 VM. (You must also have the DC-1 userid and password when you created this DC-1 VM earlier.)
- In order to Ping DC-1 from Client, ICMP traffic has to be allowed through DC-1 firewall. Open Windows Defender Firewall with Advanced Security via search bar.
- Click Inbound Rules on the left, Sort Protocol and look for ICMPv4. Then Enable the two rules named "Core Networking Diagnostics -ICMP Echo Request (ICMPv4-In)".
- From Client's desktop, open CMD and use the ping -t (DC-1 private IP address). You will now see ping replies back from DC-1.

<p>
<img src="https://i.imgur.com/uppU2oY.gif"/>
</p>
<p>

</p>
<br />

<h2>Installing Active Directory on Domain Controller</h2>
<p>

- Login to DC-1 via Remote Desktop Connection and open Server Manager.
- Click Add roles and features
- Click Next about 3 times, then under Roles select Active Directory Domain Services. Click Next a few times, then Click Install. Click Close to finish installation.
<p>
<img src="https://i.imgur.com/rhmvVGw.gif"/>
</p>  
<p>

<b>Post-deployment Configuration of Domain Services:</b>
- Click on highlighted link "Promote this server to a domain controller'. This is found by moving your cursor to the yellow triangle.
- Select "Add a new forest", and type in a name for the field Root domain name:. Then click Next.
- Type in a Password: and select Next.
- Click Next a few times, then click Install. Once confirguration is complete, the program will restart DC-1. You will have to reconnect to DC-1 via Remote Desktop Connection again.
<p>
<img src=https://i.imgur.com/IvISX3h.gif"/>
</p>
<p>

<br />


<h2>Creating Organizational Units</h2>
<p>
From the Server Manager Dashboard of the Domain Controller:

- Click On Tools (top right) and choose Active Directory Users and Computers.
- From the user interface to creat Organizational Units, right-click on mydomain.com, choose New, choose Organizational Units.
- Type a name for the org unit. In this case, _EMPLOYEES is used.
- Create another org unit. This one is _ADMINS
- The two created org units are now under mydomain.com.
<p>
<p>
<img src="https://i.imgur.com/8s01CpT.gif"/>
</p>
<p>

</p>
<br />


<b>Creating Admin user/account:</b>

- Select _ADMINS, right-click choose New and User
- Name the user Jane Doe, User logon name: jane_admin, click Next
- Choose a paswword, for this exercise Uncheck User must change password at next logon, Check Password never expires, Click Next.
- Last steps to make jane_admin an admin: Right-click on jane doe, from the Member Of tab - Click Add, tyep Domain Admins and click OK twic, then Click Apply and then OK.
- Disconnect or logoff from DC-1, and logon onto DC-1 using jane_admin credentials: user id -  mydomain.com/jane_admin and its password.
<p>
<p>
<img src="https://i.imgur.com/RcavIwJ.gif">
</p>
<p>
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
