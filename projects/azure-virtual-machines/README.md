# Creating Virtual Machines in Azure

![Status](https://img.shields.io/badge/Status-In%20Progress-blue)

## Project Overview

This project documents the process of creating and configuring virtual machines in Microsoft Azure for hands-on IT support and cloud administration practice.

## Skills Demonstrated

- Microsoft Azure portal navigation
- Virtual machine deployment
- Windows system configuration
- Networking basics
- Remote Desktop connectivity
- Cloud infrastructure administration

<img width="1572" height="750" alt="ChatGPT Image Sep 14, 2026, 04_49_58 PM" src="https://github.com/user-attachments/assets/da4722c2-4fef-4904-af58-030e10c90afd" />
<h2>How To Create a Windows and Linux Virtual Machine in Microsoft Azure<h2>
  
## Documentation

Screenshots, configuration steps, and explanations will be added as the project is completed.

<h2>Step 1: Create a Resource Group in Azure<h2>
- After creating your account in Microsoft Azure navigate to the home page.
<img width="1898" height="982" alt="Screenshot 2026-09-14 170147" src="https://github.com/user-attachments/assets/1c322ef5-b6ee-48d7-9886-16a5f3fa86e6" />

<img width="1902" height="997" alt="Screenshot 2026-09-14 172911" src="https://github.com/user-attachments/assets/ab254c56-9036-402c-8b5e-e65e986c95ce" />
- Locate the Search Bar at the top of your screen and type "resource". Notice the options that populate as you type "resource" into the search bar. Select Resource Groups.
- <img width="1857" height="943" alt="Screenshot 2026-09-14 174047" src="https://github.com/user-attachments/assets/7d24c2d9-29f5-42f5-a224-f3106a3a4777" />
- There should be no resource groups in sight. Click the + Create button and let the games begin!
<img width="1607" height="988" alt="Screenshot 2026-09-14 174250" src="https://github.com/user-attachments/assets/72ed9cb1-2fb2-421f-9b6d-1847a559aee6" />
1. The Subscription box should reflect whatever you chose when setting up your Azure account. If you do not see that, click the drop-down arrow to find it.

2. Name your Resource Group (Project-IT). This group is where our VMs will be stored in the Cloud.

3. Next, choose the Region. Tip: Select (US) East US 2 for ALL Region options. Making sure the Region matches for everything we create. Now click Next at the bottom of the screen.

<img width="1607" height="987" alt="Screenshot 2026-09-14 174640" src="https://github.com/user-attachments/assets/b368faaa-8578-4c6e-9c5f-6728164ba05b" />
- Review the information and click Create. Make a mental note or write down the name and region you used for future reference.
- 
- <img width="1621" height="996" alt="Screenshot 2026-09-14 174917" src="https://github.com/user-attachments/assets/943ed209-b487-49f0-a453-83350dd99ed5" />
- After clicking Create, you will be directed back to the RG (Resource Groups) section. You have successfully created your Resource Group in the Cloud. Now let's create some VMs!
- 
 <h2>Step 2: Creating a Windows VM in Azure</h2>
<img width="1608" height="980" alt="Screenshot 2026-09-14 175250" src="https://github.com/user-attachments/assets/173624af-7e30-43e9-9298-3e750dfadaf7" />
- From this screen, locate the search bar again and enter "vm". Select "Virtual machines" from the options. This will direct you to the Virtual Machines section.

<img width="1541" height="990" alt="Screenshot 2026-09-14 175900" src="https://github.com/user-attachments/assets/2b341cf3-1560-419c-a8df-b6e11e312e94" />
- Simply click the + Create button to get started.

  <img width="1616" height="987" alt="Screenshot 2026-09-14 180137" src="https://github.com/user-attachments/assets/443b3e69-a4ae-4c9e-9fa2-0b7cddcd9e34" />
- Select the first option, "Azure virtual machine," from the drop-down and click the + Create button.
- Your subscription should already be selected.

1. Choose the RG we created earlier.

2. Name the VM "windows-vm".

3. Select the same Region as before. "(US) East US 2". We want the RG and Region to be the same for everything we are creating.

 <img width="1471" height="992" alt="Screenshot 2026-09-14 180442" src="https://github.com/user-attachments/assets/4251ae16-b665-42b3-91a8-0c9f05cc3c57" />
Select "Windows 10 Pro, version 22H2" for the Image. This will be the Operating System (OS) for the VM. Do not select Windows Server
  - Scroll down to select the Size. We want to use the "Standard_D2s_v5 - 2 vCPUs, 8 GiB memory".

- If you do not see this listed, click "See all sizes" to get more options. Sometimes the selected region can cause this specific size to not appear. Make sure the size you pick has at least 2 vCPUs and 8 GiB memory.

<img width="1601" height="986" alt="Screenshot 2026-09-14 180612" src="https://github.com/user-attachments/assets/a4d26b1f-f8a9-4365-a7d5-428a199b0e2a" />
- Next, you will create a username and password for the VM. We will need this to log on later with a Remote Desktop Connection (RDP). *Highly recommend writing down this information for later.*

- Now, locate the Licensing area towards the bottom of the screen. You will need to check the box to confirm. This is required because we are creating a Windows VM. Deployment will not work if left unchecked. Click "Next: Disks," then "Next: Networking" to move on.

<img width="1603" height="988" alt="Screenshot 2026-09-14 180834" src="https://github.com/user-attachments/assets/a054046a-8f85-4e03-9ce6-808da7436e62" />
- Azure may auto-populate a Network name for you. Go ahead and create a new one. Just note what you named the network; we will need it for the Linux VM. You can leave the rest alone and use the Default settings. Azure will automatically assign the Subnet and Public IP for you. Leave the RDP Port as well. We will need to access the VM via Remote Desktop Connection later. Click the "Review + create" button.


-Review all the information for the Windows VM. Our Subscription, RG, and Region are correct. We named the VM "windows-vm". The Image and Size are correct, and we have RDP enabled. Simply click "Create".

<img width="1855" height="942" alt="Screenshot 2026-09-14 181019" src="https://github.com/user-attachments/assets/1bde59b1-06b8-4b36-b252-9486d5dd5048" />
- Once you click "Create", the Deployment of the Windows VM will begin. This can take a few minutes. When it's completed, you will see "Your deployment is complete". Congrats! We just created our first Virtual Machine in the Cloud. Click "Create another VM" to get started on the Linux VM.

<h2>Step 3: Create a Linux VM in Azure</h2>

<img width="1856" height="932" alt="Screenshot 2026-09-14 181131" src="https://github.com/user-attachments/assets/1aae138b-852b-4068-8032-bc87453c6b47" />
Select the same RG that we created earlier. Name the VM "linux-vm" and choose the same Region as before. Since this will be the Linux VM, select "Ubuntu Server 22.02" for the Image.

<img width="1861" height="943" alt="Screenshot 2026-09-14 181237" src="https://github.com/user-attachments/assets/8e18ebeb-90c5-4d76-9f63-5c9007782aaf" />
- Choose the same Size option as before. "Standard_D2s_v5 - 2 vCPUs, 8 GiB memory".

- Next, you will need to select "Password" for Authentication type. Azure defaults to SSH public key. Then, create a Username and Password. You can use the same[Uploading Screenshot 2026-09-14 181408.png…]()
information as the Windows VM to keep it simple. Once you are done, scroll down and click "Disks". Leave these options as default and skip to "Networking".

<img width="1602" height="992" alt="Screenshot 2026-09-14 181311" src="https://github.com/user-attachments/assets/26d75469-4f81-462f-91e3-460d766d967b" />
- Make sure to select the same Virtual Network that we created earlier. We can leave everything else as default. Scroll down and click "Review + create".

<img width="1862" height="947" alt="Screenshot 2026-09-14 181408" src="https://github.com/user-attachments/assets/d3753973-3beb-4a64-9737-06d89334b738" />
- On the next screen you will see the deployment of the Linux VM in progress. This may take a few minutes.

<img width="1472" height="987" alt="Screenshot 2026-09-14 181547" src="https://github.com/user-attachments/assets/a4d7a2ff-e89a-423d-9844-375a02f9b8e8" />
- The Linux VM has been successfully created.

<img width="1862" height="953" alt="Screenshot 2026-09-14 181652" src="https://github.com/user-attachments/assets/8649f879-23e4-4d31-a709-509a43ef17b2" />
- Locate the search bar at the top of the screen and type in "virtual". Select "Virtual machines," and you will be directed to your newly created VMs!

<img width="1863" height="942" alt="Screenshot 2026-09-14 181754" src="https://github.com/user-attachments/assets/099d4a9f-b1e2-4116-88a5-d1c997dbcb95" />
- You can view the Windows and Linux VMs we created in the Cloud. You will notice the RG and Locations match, what OS they are running, Public IP addresses, and more!

*Pro Tip: Notice the Start, Restart, and Stop buttons above the OS and Size area. You can use these to "turn off", "turn on" , or "restart" the VMs like you would your physical PC or Laptop. To save on your subscription, you can "Stop" the VMs from running while you are not using them. Just make sure to "Start" them when you are ready to use them again. If you want extra practice, you can simply delete the RG and recreate everything as needed.*


🎉 Project Wrap Up
And that’s a wrap. In this project, we successfully created a Resource Group, a Windows VM running Windows 10 Pro, and a Linux VM running Ubuntu, all hosted in the cloud. Along the way, we got a hands-on look at the power of cloud computing and virtualization how simple it is to spin up multiple machines without needing physical hardware. With just a MacBook, I was able to set up and access two additional machines running completely different operating systems. No clutter, no pricey setups, just pure cloud efficiency.

This is a perfect example of why businesses are leaning heavy into Cloud Service Providers (CSPs); the flexibility, scalability, and cost-effectiveness are game changers. Before we go, don’t forget to Stop your VMs in Azure when you're done to avoid unnecessary charges. Thanks for following along and being part of this journey. See you in the next project same energy, new level 😎





















