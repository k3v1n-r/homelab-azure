# Setting Up a Home Lab Using Azure Virtual Machines

## Project Overview

This guide walks you through setting up a home lab environment using Azure Virtual Machines (VMs). Azure allows you to create scalable and customizable VMs to simulate various server configurations, test environments, or run applications in isolation. With this home lab setup, you can experiment with different technologies without the need for physical hardware.

## Prerequisites

- An **Azure account**. You can start with a free account, which provides some free credits.
- **Basic knowledge of Azure** and the **Azure Portal**.
- **Azure CLI** (optional, but useful for managing resources from the command line).
  
## Steps to Set Up Your Home Lab in Azure

### Step 1: Create an Azure Virtual Machine

1. Log into your Azure account at [Azure Portal](https://portal.azure.com).
2. Navigate to the **Virtual Machines** section.
3. Click **+ Create** to start the creation wizard.
4. Choose a **Subscription** and a **Resource Group**. (If you don't have a resource group, you can create one.)
5. Choose a **Region**. Select a region close to your location for better performance.
6. Under **Image**, choose the operating system for your VM (e.g., Windows Server, Ubuntu, or any custom image).
7. Specify the **Size** of your VM. For testing, the **B1s** (Basic) or **Standard D2s v3** VM sizes are good choices, balancing cost and performance.
8. Provide a **VM name**, and set **Administrator username** and **Password**.
9. Click **Next** and configure additional settings (such as storage, networking, etc.). For simplicity, you can leave default options for now.
10. Click **Review + Create**, verify your settings, and click **Create** to provision the VM.

### Step 2: Connect to Your Virtual Machine

1. Once the VM is deployed, go to the **Virtual Machines** section in the Azure Portal.
2. Select the VM you created.
3. Under **Overview**, find the **Public IP Address**. This will be used to connect to your VM.
4. Use **Remote Desktop Protocol (RDP)** for Windows VMs or **SSH** for Linux VMs.
   - **Windows**: Open the **Remote Desktop Client** and enter the **IP address**, then use the **username** and **password** you provided.
   - **Linux**: Use an SSH client (e.g., `ssh username@ip-address`) and provide your password.

### Step 3: Configure Your Virtual Machine

Once connected to your VM, you can configure it as needed:
- Install any necessary software (e.g., web servers, databases, or development tools).
- Create additional users or configure network settings.
- Set up networking between multiple VMs if you plan to simulate a network of virtual machines.

### Step 4: Create Additional Virtual Machines (Optional)

You can repeat the above process to create additional VMs for your lab environment:
- Create separate VMs for **Active Directory**, **SQL Server**, **Web Servers**, **Client Machines**, or any other configuration you need.
- Make sure to adjust networking settings so the VMs can communicate with each other (using Virtual Networks or Public IPs as needed).

### Step 5: Set Up Networking (Optional)

If you need to connect multiple VMs or configure advanced networking:
1. Go to the **Virtual Network** section in the Azure Portal.
2. Create a new virtual network (VNet) to define the IP address range and subnets.
3. Ensure that all VMs are connected to the same VNet or configure appropriate subnets.

### Step 6: Automation and Management (Optional)

You can automate and manage your VMs using:
- **Azure Automation**: Automate common tasks like patch management, backups, and scaling.
- **Azure CLI**: Use the command-line interface to create, manage, and configure resources.
- **PowerShell**: Automate tasks with PowerShell scripts tailored for Azure.

### Step 7: Cost Management

Be mindful of the costs:
- **Azure pricing**: Ensure you monitor your usage in the **Cost Management + Billing** section.
- Stop or delete VMs when not in use to avoid unnecessary costs.
  
## Conclusion

By following these steps, you can easily set up a home lab in Azure, experiment with different setups, and test various technologies. Azure offers a flexible, cost-effective environment to build a robust lab