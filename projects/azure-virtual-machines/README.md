# Creating Virtual Machines in Azure

![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

![Azure virtual machines project banner](https://github.com/user-attachments/assets/da4722c2-4fef-4904-af58-030e10c90afd)

## Project Overview

This project documents how to create Windows and Linux virtual machines (VMs) in Microsoft Azure. The walkthrough covers organizing resources, selecting operating systems and VM sizes, configuring networking, and confirming successful deployments.

This environment provides a foundation for hands-on IT support, networking, and system administration practice.

## Skills Demonstrated

- Navigating the Microsoft Azure portal
- Organizing cloud resources in a resource group
- Deploying Windows and Linux virtual machines
- Selecting operating system images, virtual CPUs, and memory
- Configuring virtual networks and remote access settings
- Reviewing deployment results and managing VM power states

## Lab Configuration

| Component | Configuration Used in This Walkthrough |
|---|---|
| Cloud platform | Microsoft Azure |
| Resource group | `Project-IT` |
| Region | East US 2 |
| Windows VM | `windows-vm` — Windows 10 Pro, version 22H2 |
| Linux VM | `linux-vm` — Ubuntu Server |
| VM size | `Standard_D2s_v5` — 2 vCPUs and 8 GiB of memory |
| Networking | Both VMs use the same virtual network |

The settings below document this lab. Available images and VM sizes may differ in your subscription.

## Step 1: Create a Resource Group

A resource group is a logical container for related Azure resources. In this lab, it keeps the virtual machines and their supporting resources organized.

### Open Resource Groups

Sign in to the Azure portal and navigate to the home page.

![Azure portal home page](https://github.com/user-attachments/assets/1c322ef5-b6ee-48d7-9886-16a5f3fa86e6)

In the search bar at the top of the portal, enter **resource** and select **Resource groups**.

![Searching for Resource groups in the Azure portal](https://github.com/user-attachments/assets/ab254c56-9036-402c-8b5e-e65e986c95ce)

Select **+ Create**. If your subscription already contains resource groups, they will appear in this list.

![Resource groups page before creating the lab resource group](https://github.com/user-attachments/assets/7d24c2d9-29f5-42f5-a224-f3106a3a4777)

### Enter the Resource Group Details

1. **Subscription:** Select the Azure subscription for this lab.
2. **Resource group:** Enter `Project-IT`.
3. **Region:** Select **(US) East US 2** for this walkthrough.
4. Continue to **Review + create**.

![Subscription, resource group name, and region settings](https://github.com/user-attachments/assets/72ed9cb1-2fb2-421f-9b6d-1847a559aee6)

Review the configuration, then select **Create**. Record the resource group name and region for the remaining steps.

![Reviewing the resource group configuration](https://github.com/user-attachments/assets/b368faaa-8578-4c6e-9c5f-6728164ba05b)

After creation, confirm that `Project-IT` appears on the **Resource groups** page.

![Newly created resource group in Azure](https://github.com/user-attachments/assets/943ed209-b487-49f0-a453-83350dd99ed5)

## Step 2: Create a Windows Virtual Machine

### Open the VM Creation Wizard

Use the portal search bar to search for **vm**, then select **Virtual machines**.

![Searching for Virtual machines in the Azure portal](https://github.com/user-attachments/assets/173624af-7e30-43e9-9298-3e750dfadaf7)

Select **+ Create**, then choose **Azure virtual machine**.

![Create menu on the Virtual machines page](https://github.com/user-attachments/assets/2b341cf3-1560-419c-a8df-b6e11e312e94)

### Configure the Basic Settings

1. Confirm the correct **Subscription**.
2. Select the **Project-IT** resource group.
3. Enter `windows-vm` as the **Virtual machine name**.
4. Select **(US) East US 2** as the **Region**.

![Basic settings for the Windows virtual machine](https://github.com/user-attachments/assets/443b3e69-a4ae-4c9e-9fa2-0b7cddcd9e34)

For this lab, the Windows image is **Windows 10 Pro, version 22H2**. The image determines which operating system is installed on the VM.

Select **Standard_D2s_v5**, which provides **2 vCPUs and 8 GiB of memory**. If it is not listed, select **See all sizes** and review the available options. This walkthrough uses at least 2 vCPUs and 8 GiB of memory.

![Windows operating system image and VM size settings](https://github.com/user-attachments/assets/4251ae16-b665-42b3-91a8-0c9f05cc3c57)

### Configure the Administrator Account

Create an administrator username and password. These credentials will be used when connecting to the Windows VM through Remote Desktop Protocol (RDP). Store them securely for later use.

Review the **Licensing** section and confirm the acknowledgment only if you meet its stated requirements. Continue to **Next: Disks**, review the disk settings, then select **Next: Networking**.

![Windows administrator account and licensing settings](https://github.com/user-attachments/assets/a4d26b1f-f8a9-4365-a7d5-428a199b0e2a)

### Configure Networking

Create a virtual network for the lab and record its name. The Linux VM will use this same network.

Review the subnet, public IP, and RDP settings before continuing. This walkthrough prepares the Windows VM for a later Remote Desktop connection.

Select **Review + create**.

![Virtual network and remote access settings for the Windows VM](https://github.com/user-attachments/assets/a054046a-8f85-4e03-9ce6-808da7436e62)

### Review and Deploy

Confirm the subscription, resource group, region, VM name, image, size, and networking settings. After validation succeeds, select **Create**.

Wait for the deployment to finish. When Azure displays **Your deployment is complete**, the Windows VM has been created.

![Completed Windows virtual machine deployment](https://github.com/user-attachments/assets/1bde59b1-06b8-4b36-b252-9486d5dd5048)

Select **Create another VM** to begin the Linux deployment.

## Step 3: Create a Linux Virtual Machine

### Configure the Basic Settings

1. Use the same subscription and **Project-IT** resource group.
2. Enter `linux-vm` as the **Virtual machine name**.
3. Select **(US) East US 2** as the **Region**.
4. Select the **Ubuntu Server** image for the Linux VM.

![Basic settings and Ubuntu image selection for the Linux VM](https://github.com/user-attachments/assets/1aae138b-852b-4068-8032-bc87453c6b47)

### Select the Size and Authentication Method

Select **Standard_D2s_v5**, matching the Windows VM's **2 vCPUs and 8 GiB of memory**.

For the password-based setup documented in this lab, select **Password** under **Authentication type** and create administrator credentials. Store these credentials securely.

Continue to **Disks**, review the default settings, then proceed to **Networking**.

![Linux VM size and administrator authentication settings](https://github.com/user-attachments/assets/8e18ebeb-90c5-4d76-9f63-5c9007782aaf)

### Use the Existing Virtual Network

Select the virtual network created for the Windows VM. Review the remaining networking settings, then select **Review + create**.

![Selecting the existing virtual network for the Linux VM](https://github.com/user-attachments/assets/26d75469-4f81-462f-91e3-460d766d967b)

### Review and Deploy

Review the Linux VM configuration. After validation succeeds, select **Create** and wait for deployment to finish.

![Linux virtual machine deployment in progress](https://github.com/user-attachments/assets/d3753973-3beb-4a64-9737-06d89334b738)

Confirm that Azure reports a successful deployment.

![Completed Linux virtual machine deployment](https://github.com/user-attachments/assets/a4d7a2ff-e89a-423d-9844-375a02f9b8e8)

## Step 4: Verify Both Virtual Machines

Search for **Virtual machines** in the portal and open the VM list.

![Returning to the Virtual machines page after deployment](https://github.com/user-attachments/assets/8649f879-23e4-4d31-a709-509a43ef17b2)

Confirm that both `windows-vm` and `linux-vm` appear. Review their resource group, location, operating system, and power state. Open each VM's networking settings to confirm that both use the intended virtual network.

![Windows and Linux virtual machines listed in Azure](https://github.com/user-attachments/assets/099d4a9f-b1e2-4116-88a5-d1c997dbcb95)

## Managing the Lab Resources

Use **Start**, **Restart**, and **Stop** in the Azure portal to manage each VM's power state.

When you finish practicing, stop the VMs through the portal and confirm that their status changes to **Stopped (deallocated)**. Deallocation stops VM compute charges, but disks and some networking resources can continue to incur charges. See [Microsoft's explanation of VM states and billing](https://learn.microsoft.com/en-us/azure/virtual-machines/states-billing).

If you no longer need the lab, review the contents of `Project-IT` before deleting the resource group. Deleting it removes the resources it contains, so first save anything you need to keep.

## Project Summary

This walkthrough documents the deployment of a Windows VM and an Ubuntu Linux VM in Microsoft Azure. Both machines are organized under one resource group and configured to use the same virtual network.

The project demonstrates foundational cloud administration skills: organizing resources, selecting compute configurations, configuring networking, and verifying deployment results. The environment can support further practice with remote connections, operating system administration, and network troubleshooting.
