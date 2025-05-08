## 4. Hands-On Labs

Practical experience is paramount for the AZ-104 exam. Perform these labs in your own Azure subscription (a free trial or pay-as-you-go). Refer to the official [Microsoft Learning AZ-104 GitHub labs](https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator) for detailed steps.

### Azure CLI and PowerShell Basics
* **Objective:** Familiarize yourself with command-line tools for Azure management.
* **Tasks:**
    1.  Install Azure CLI and Azure PowerShell module.
    2.  Log in to Azure using `az login` and `Connect-AzAccount`.
    3.  Practice basic commands:
        * List resource groups: `az group list`, `Get-AzResourceGroup`
        * Create a resource group: `az group create`, `New-AzResourceGroup`
        * View resources in a resource group: `az resource list`, `Get-AzResource`
        * Get help for commands: `az group --help`, `Get-Help New-AzResourceGroup -Full`
    4.  Explore output formats (JSON, table).
    5.  Practice querying output (e.g., using `--query` in CLI or `Where-Object` in PowerShell).

### Deploying VMs in Azure
* **Objective:** Understand the process of creating and configuring Azure VMs.
* **Tasks:**
    1.  **Using Azure Portal:**
        * Create a Windows Server VM. Configure size, region, networking (new VNet/subnet), and diagnostics.
        * Create a Linux VM (e.g., Ubuntu). Configure SSH key authentication.
        * Connect to the Windows VM using RDP and Linux VM using SSH.
        * Add a data disk to one of the VMs. Initialize and format it.
    2.  **Using Azure CLI/PowerShell:**
        * Deploy a VM using `az vm create` or `New-AzVM`.
        * Stop, start, deallocate, and delete a VM.
        * Resize a VM.
    3.  **Availability:**
        * Deploy two VMs into an Availability Set.
        * Deploy two VMs into different Availability Zones (if your region supports it).

### Configuring Azure Storage Accounts
* **Objective:** Learn to create and manage storage accounts, blobs, and file shares.
* **Tasks:**
    1.  **Using Azure Portal:**
        * Create a general-purpose v2 storage account. Explore redundancy options (LRS, GRS, ZRS).
        * Create a blob container. Set public access level. Upload some sample files (blobs).
        * Generate a SAS token for a blob and access it.
        * Configure soft delete for blobs.
        * Create an Azure file share. Mount it on your local machine or an Azure VM.
        * Take a snapshot of the file share.
    2.  **Using Azure Storage Explorer:**
        * Connect to your storage account.
        * Manage blobs and files (upload, download, delete).
    3.  **Using AzCopy:**
        * Upload files to blob storage.
        * Download files from blob storage.

### Setting up Azure Virtual Networks
* **Objective:** Gain experience with VNet creation, peering, NSGs, and DNS.
* **Tasks:**
    1.  **VNet and Subnets:**
        * Create a VNet with multiple subnets using the Azure portal.
        * Deploy VMs into different subnets.
    2.  **VNet Peering:**
        * Create a second VNet.
        * Configure VNet peering between the two VNets.
        * Test connectivity between VMs in peered VNets (ensure OS firewalls allow pings).
    3.  **Network Security Groups (NSGs):**
        * Create an NSG.
        * Create inbound rules to allow RDP/SSH to your VMs and block other traffic.
        * Associate the NSG with a subnet or a NIC.
        * Test the rules.
    4.  **Azure DNS:**
        * Create an Azure Private DNS zone. Link it to your VNet.
        * Observe automatic registration of VM DNS records.
        * Create a Public DNS zone (if you have a domain) and add some records.
    5.  **Azure Load Balancer (Optional, but good practice):**
        * Deploy two web server VMs.
        * Create a public Load Balancer and configure it to distribute traffic to the web servers.

### Monitoring with Azure Monitor & Log Analytics
* **Objective:** Learn to monitor resources, query logs, and set up alerts.
* **Tasks:**
    1.  **Metrics Explorer:**
        * Navigate to Azure Monitor and explore metrics for one of your VMs (CPU, Network In/Out).
        * Pin a chart to an Azure dashboard.
    2.  **Log Analytics:**
        * Create a Log Analytics workspace.
        * Configure Diagnostic Settings for a VM and a storage account to send logs and metrics to the workspace.
        * Wait for data to populate, then run basic KQL queries (e.g., `AzureActivity | take 10`, `Perf | where CounterName == "% Processor Time"`).
    3.  **Alerts:**
        * Create a metric alert (e.g., when VM CPU > 80% for 5 minutes).
        * Create an action group to send an email notification.
        * Trigger the alert (e.g., by stressing the VM CPU) and verify the notification.
    4.  **VM Insights (Optional):**
        * Enable VM Insights for one of your VMs and explore the performance and map views.
