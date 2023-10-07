<h1>Virtual Machine Traffic</h1>
This is a brief tutorial where communication traffic between the virtual machines created in the VM-Set-up lab will be observed using Wireshark.<br />

<h2>Prerequisite</h2>

- Creation of Virtual machines from https://github.com/SedinamA/VM-Set-up

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Resource Group and Virtual Machines)

<h2>Operating System & Languages Used </h2>

- HP Windows 11 laptop
- Command Prompt
- Wireshark

<h2>Traffic Set-up and Demonstration </h2>

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/dc7a6665-09e7-4095-bbe0-8025948746ad)

Navigate to the virtual machine section in Azure through the search bar or by clicking on the virtual machine icon.Click on Virtual Machine 1 (VM-Windows). 

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/a119ee6e-d015-41cb-9535-b5a0c9b8624d)

Move your cursor over to the public IP address line of “VM-Windows” overview page and copy the IP address from the upper right portion where it says Public IP Address. Note that your IP address may be different.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/0de3ffa7-4032-430c-b40d-de5d4ea45c65)


On the search bar of your computer’s  taskbar, search for “Remote Desktop Connection” the app should look something like this when you open it. Paste the IP address in the computer bar, and click “Connect”.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/1db8c61d-3743-4c83-90e8-56ba42868ae4)

Click on “more choices” and then select “use a different account”

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/19ed9d66-ccab-4130-b117-dfecca7c0ecd)

Enter the Username “Windows10” and the created password from the “VM-Set-up” lab, then click ok.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/ae1615e8-454d-4154-a0c5-51325b35a26c)

If you get this warning message, click “yes” to proceed.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/a3595979-5a91-4f3a-b1aa-83708ffa8cd8)

Switch all options to “No” they will not be needed during this lab.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/369752be-9f81-4fdc-9fe5-06f177116469)

Access the internet through VM-Windows using Microsoft Edge. We will be installing wireshark to observe traffic between this machine and the Ubuntu server (VM-U). Type in “download Wireshark” in the Google search bar. select the first listing.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/b24ff26e-dde8-468b-858e-72aa903bd497)

Be sure to download the installment package that says “Windows installer (64-bits)”. 

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/0ff74678-e8e1-4e8a-8d31-54fda621076e)
![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/b5c7493f-a19e-438d-8c43-93ae1e9712bc)
![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/6a1669c1-36d3-44b9-94e2-7574532ecd48)
![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/3da0ab8d-0e85-46ea-baf4-703a772220ed)

Once downloaded, run the installer and follow the process(keep clicking "next") until you reach the end and click the finish button. After that close the internet browser. During the download process, click agree to any other prompts that show up like the one in the Npcap 1.71 window.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/7e5ce58b-7916-4a41-9e71-71e9fa99125f)

From the search bar on the taskbar, type in “Wireshark” or just select the icon in the start section.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/91baeefe-9b86-40bc-af25-41c0abbffb3d)
![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/daecc5d1-e3ca-46d7-ae65-85434dd7486d)

On this screen, make sure to select “Ethernet” and then click the blue icon in the upper left corner, this is the button to “start capturing packets”. We will be using this to see the live traffic between the two machines when we ping the IP address of VM-U from the command prompt on VM-Windows.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/a3810d72-f691-4fe6-8b1d-78e62115215d)

In the search bar beneath the blue icon, type “ICMP” and press enter or click the right arrow next to the search bar. The Internet control messaging protocol (ICMP) is what we will be using to observe live traffic since it is the protocol that ping uses. 

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/19d4a29b-d0a5-434e-9c74-55316b1167b7)

Now we need to locate the Private IP address required to ping VM-U so minimize (do not close it) the VH-Windows screen, and navigate to the VM-U overview page of the virtual machines resource group. 

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/9e78c8a0-c927-43c9-a061-8ec04ddbb0ea)

In the “Networking” section of VM-U’s overview, copy the private IP address listed (or memorize it). Note that all IP addresses will be different on your end should you run this tutorial yourself.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/19569454-3089-4564-a3d8-619659caad0b)
![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/27f685eb-3f10-405c-96bb-e06ec576f3e5)

Go back to VM-Windows and open the “Command Prompt” app. In the command line type “ping (insert IP)”  and press enter.

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/997290ca-05ec-49ee-95b6-2e505c0a1f89)

Witness the traffic displayed in the back on Wireshark, where requests and replies are being listed, this means that successful communication between the machines is occurring; where requests from VM-Windows(IP 10.0.0.4) are being replied to by VM-U(IP 10.0.0.5).

![image](https://github.com/SedinamA/VM-Traffic/assets/146953803/d2ad5304-74a3-4390-887c-a7371995591b)

This concludes this portion of the lab, once all activities are completed, remember to delete everything created to prevent subscription costs for storage of the resource groups and virtual machines.
