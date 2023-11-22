<p align="center">
<img src="https://i.imgur.com/T1otXpv.png" alt="osTicket logo"/>
</p>

<h1>Wireshark - Using Wireshark to observe network traffic</h1>
This is a tutorial on how to use Wireshark and observe network traffic. 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- PowerShell
- Wireshark

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Linux (Ubuntu)

<h2>Lab Steps</h2>
<p>
<img src="https://i.imgur.com/A9PQGhP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create two virtual machines. One of them will be running Windows 10, while the other will be running Linux (Ubuntu). 
</p>
<br />

<p>
<img src="https://i.imgur.com/wat4byn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open up the Microsoft 10 virtual machine and download Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/1usOMVb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Powershell, ping the other VM running Linux, and ping www.google.com. The ping should be successful with no packets lost.  
</p>
<br />

<p>
<img src="https://i.imgur.com/VFdqX8w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Perpetual ping the private IP address of the virtual machine running Linux from the VM running Windows 10. Open the network security group the Linux VM is using and disable incoming ICMP traffic. Observe the traffic on wireshark and command line ping activity. Re-enable ICMP traffic for your Linux VM. Back in the Windows 10 VM, observe the ICMP traffic in Wireshark and the command line ping activity.
</p>
<br />


<img src="https://i.imgur.com/gUvRDy5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

While observing Wireshark, you will notice the ICMP traffic gets busy when you ping the VM running Linux or ping www.google.com. When you disable incoming ICMP traffic you should see Wireshark coming back with "no response". This will change when you re-enable ICMP traffic. 


<img src="https://i.imgur.com/neulSXX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Connect your Windows 10 VM to the VM using Linux using SSH.


<img src="https://i.imgur.com/32yFNQ3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Filter for SSH traffic only. You can now see the SSH traffic in Wireshark due to connecting the VMs with SSH. 


<img src="https://i.imgur.com/jTa7Td5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Set Wireshark to filter DHCP traffic only. Using your Windows 10 VM, attempt to issue your VM a new IP address from the command line using the command "ipconfig/ renew".

<img src="https://i.imgur.com/CJTdINV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Observing Wireshark, you can see DHCP traffic appear. Getting a new IP address uses DHCP which is why we can view the traffic. We are done with the lab so we can delete the VMs so it does not continue to accrue charges.


