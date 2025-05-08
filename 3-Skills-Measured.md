## 3. Skills Measured

*(This section will detail each domain and its sub-topics as per the outline provided by the user. Each sub-topic will have a brief explanation of the concept and key areas to focus on.)*

### Manage Azure identities and governance (20-25%)

This domain focuses on managing identities within Microsoft Entra ID (formerly Azure Active Directory) and implementing governance features like Azure Policy, resource locks, and tagging.

#### Manage Microsoft Entra users and groups

* **Create users and groups:**
    * **Users:** Understand how to create individual user accounts in Microsoft Entra ID (cloud-only identities), synchronize on-premises users (hybrid identities - though deep AD Connect configuration is more AZ-800/801), and invite guest users (B2B).
    * **Properties:** Know the various user profile attributes (e.g., job title, department, contact info, authentication methods).
    * **Bulk Operations:** Learn to create users in bulk using the portal (CSV import) or PowerShell/Azure CLI.
    * **Groups:** Understand the types of groups (Security and Microsoft 365).
    * **Membership Types:** Differentiate between Assigned, Dynamic User, and Dynamic Device membership for groups. Be able to create groups with dynamic membership rules.
    * **Group Properties:** Manage group owners, members, and settings.
* **Manage user and group properties:**
    * Modifying attributes for existing users and groups.
    * Understanding the impact of property changes (e.g., usage location for license assignment).
    * Managing administrative units to delegate administrative tasks over specific sets of users and groups.
* **Manage licenses in Microsoft Entra ID:**
    * Understand how Microsoft Entra ID P1/P2 and other Microsoft cloud service licenses (e.g., Microsoft 365) are managed.
    * Assign licenses directly to users.
    * Implement group-based licensing: Assign licenses to groups, and users automatically inherit licenses when added to the group. This is the preferred method.
    * Monitor license usage and available licenses.
    * Understand how to handle licensing conflicts or errors.
* **Manage external users (Azure AD B2B):**
    * Understand the concept of Azure AD Business-to-Business (B2B) collaboration.
    * Invite guest users to your Microsoft Entra tenant to collaborate on resources.
    * Manage guest user access and permissions.
    * Understand the redemption process for guest user invitations.
    * Configure settings for external collaboration (e.g., who can invite guests).
* **Configure self-service password reset (SSPR):**
    * Understand the benefits of SSPR for reducing helpdesk calls.
    * Enable and configure SSPR for all users or specific groups.
    * Configure authentication methods for SSPR (e.g., mobile app notification, email, security questions, phone call).
    * Customize the password reset portal and notifications.
    * Understand password writeback if you have a hybrid identity setup (requires Microsoft Entra ID Premium).

#### Manage access to Azure resources

* **Manage built-in Azure roles:**
    * Understand Azure Role-Based Access Control (RBAC).
    * Differentiate between Owner, Contributor, Reader, and User Access Administrator roles.
    * Know the purpose and permissions of common built-in roles (e.g., Virtual Machine Contributor, Storage Blob Data Reader).
    * Understand that roles are sets of permissions (actions like `Microsoft.Compute/virtualMachines/start/action`).
* **Assign roles at different scopes:**
    * Understand the concept of scope in Azure RBAC: Management Group, Subscription, Resource Group, and individual Resource.
    * Know that permissions are inherited from parent scopes.
    * Assign roles to users, groups, service principals, and managed identities.
    * Understand the principle of least privilege when assigning roles.
* **Interpret access assignments:**
    * Use the Azure portal (Access control (IAM) blade) to view who has what access to a resource.
    * Understand how to check your own permissions or the permissions of another principal.
    * Differentiate between direct assignments and inherited assignments.
    * Troubleshoot access denied issues by reviewing role assignments and deny assignments (though deny assignments are less common for AZ-104).

#### Manage Azure subscriptions and governance

* **Implement and manage Azure Policy:**
    * Understand how Azure Policy helps enforce organizational standards and assess compliance at scale.
    * Differentiate between policy definitions, initiatives (sets of policies), assignments, and parameters.
    * Assign built-in policies and initiatives (e.g., allowed locations, allowed VM SKUs, require tags).
    * Understand policy effects (e.g., Deny, Audit, Append, DeployIfNotExists, Modify).
    * View policy compliance and remediate non-compliant resources.
    * Understand the scope of policy assignments (management group, subscription, resource group).
* **Configure resource locks:**
    * Understand the purpose of resource locks: prevent accidental deletion or modification of critical resources.
    * Differentiate between `CanNotDelete` (ReadOnly) and `Delete` lock types.
    * Apply and manage locks at different scopes (subscription, resource group, resource).
    * Understand how locks interact with RBAC permissions (locks apply to everyone, including owners).
* **Apply and manage tags on resources:**
    * Understand the importance of tags for organizing resources, cost management, and automation.
    * Apply tags (key-value pairs) to resources and resource groups.
    * Enforce tagging strategies using Azure Policy.
    * Use tags for cost tracking in Azure Cost Management.
* **Manage resource groups:**
    * Understand that resource groups are containers for resources that share a common lifecycle, permissions, and policies.
    * Create, delete, and manage resource groups.
    * Move resources between resource groups (with limitations).
    * Understand that deleting a resource group deletes all resources within it.
* **Manage subscriptions:**
    * Understand the role of Azure subscriptions as billing and management boundaries.
    * View subscription details and usage.
    * Understand how to obtain new subscriptions (e.g., Enterprise Agreement, Pay-As-You-Go, CSP).
    * Organize subscriptions using Management Groups.
* **Manage costs by using alerts, budgets, and Azure Advisor recommendations:**
    * **Azure Cost Management:** Analyze costs, create budgets, and set up cost alerts.
    * **Budgets:** Configure budgets at various scopes (subscription, resource group) and set thresholds for notifications or actions (e.g., trigger an action group).
    * **Alerts:** Create alerts based on spending thresholds.
    * **Azure Advisor:** Utilize Advisor recommendations for cost optimization, performance, security, and operational excellence. Review and implement relevant recommendations.
* **Configure management groups:**
    * Understand how management groups provide a level of scope above subscriptions to organize subscriptions and apply governance controls (like Azure Policy and RBAC) hierarchically.
    * Create and manage management group hierarchies.
    * Move subscriptions between management groups.
    * Assign policies and roles at the management group scope.

### Implement and manage storage (15-20%)

This domain covers configuring and managing Azure Storage accounts, including services like Blob storage, Azure Files, and managing access and data protection features.

#### Configure access to storage

* **Configure Azure Storage firewalls and virtual networks:**
    * Restrict access to storage accounts by configuring firewall rules to allow traffic only from specific public IP addresses or address ranges.
    * Allow access from specific Azure virtual networks and subnets using service endpoints or private endpoints.
    * Understand the difference between service endpoints (traffic stays on Azure backbone but uses public IP) and private endpoints (private IP within your VNet).
* **Create and use shared access signature (SAS) tokens:**
    * Understand that SAS tokens provide delegated, granular access to storage resources without exposing account keys.
    * Types of SAS: User delegation SAS, Service SAS, Account SAS. Focus on Service and Account SAS for AZ-104.
    * Configure SAS tokens with specific permissions (read, write, delete, list), start/expiry times, and allowed IP addresses.
    * Generate SAS tokens for blobs, containers, file shares, queues, or tables.
    * Understand how to use a SAS token URI to access storage.
* **Configure stored access policies:**
    * Define stored access policies on a container, file share, queue, or table.
    * Provide an additional level of control over service SAS tokens.
    * Allow modification or revocation of SAS tokens without needing to reissue them by managing the policy.
* **Manage access keys:**
    * Understand that each storage account has two access keys (primary and secondary) that provide full administrative access to the storage account.
    * View and copy access keys.
    * Regenerate (rotate) access keys periodically for security. Understand the impact of regenerating keys on applications using them.
    * Securely store and manage access keys (e.g., using Azure Key Vault).
* **Configure identity-based access for Azure Files:**
    * Understand how to enable identity-based authentication for Azure file shares.
    * **Microsoft Entra Domain Services Authentication:** Join the storage account to a Microsoft Entra Domain Services managed domain to allow SMB access using Microsoft Entra credentials.
    * **On-premises Active Directory Domain Services (AD DS) Authentication:** Synchronize on-premises AD DS identities to Microsoft Entra ID and join the storage account to your on-premises AD DS for SMB access with AD DS credentials.
    * Assign share-level permissions (RBAC roles like Storage File Data SMB Share Reader/Contributor/Elevated Contributor) and NTFS-level permissions.

#### Configure and manage storage accounts

* **Create and configure storage accounts:**
    * Understand the different types of storage accounts (General-purpose v2, General-purpose v1, BlobStorage, FileStorage, BlockBlobStorage). GPv2 is standard.
    * Choose the appropriate account kind, performance tier (Standard, Premium), and access tier (Hot, Cool, Archive for blobs).
    * Configure account settings like location, resource group, and networking.
    * Understand storage account limits.
* **Configure Azure Storage redundancy:**
    * Understand the different data redundancy options and their use cases:
        * **Locally-redundant storage (LRS):** Three copies within a single datacenter.
        * **Zone-redundant storage (ZRS):** Three copies across different availability zones in the primary region.
        * **Geo-redundant storage (GRS):** LRS in primary + LRS in secondary (asynchronous).
        * **Read-access geo-redundant storage (RA-GRS):** GRS + read access to secondary.
        * **Geo-zone-redundant storage (GZRS):** ZRS in primary + LRS in secondary (asynchronous).
        * **Read-access geo-zone-redundant storage (RA-GZRS):** GZRS + read access to secondary.
    * Choose the appropriate redundancy option based on durability and availability requirements.
    * Understand how to change redundancy options (with some limitations).
* **Configure object replication:**
    * Asynchronously copy block blobs between a source and destination storage account.
    * Configure replication policies, including source/destination containers and blob prefixes.
    * Understand use cases like cross-region replication for disaster recovery or minimizing latency.
* **Configure storage account encryption:**
    * Understand that Azure Storage Service Encryption (SSE) encrypts data at rest by default using Microsoft-managed keys.
    * Configure encryption with customer-managed keys (CMK) using Azure Key Vault for greater control.
    * Understand encryption scopes for more granular control over encryption keys within a storage account.
    * Understand support for infrastructure encryption (double encryption).
* **Manage data by using Azure Storage Explorer and AzCopy:**
    * **Azure Storage Explorer:** A graphical tool for managing Azure Storage resources (blobs, files, queues, tables, Azure Data Lake Storage) on Windows, macOS, and Linux. Perform operations like upload, download, delete, manage SAS, etc.
    * **AzCopy:** A command-line utility for copying data to and from Azure Blob, File, and Table storage, and between storage accounts. Optimized for high performance. Know common AzCopy commands for upload, download, sync.

#### Configure Azure files and Azure blob storage

* **Create and configure a file share in Azure Storage:**
    * Create Azure file shares (SMB/NFS).
    * Configure share quotas.
    * Understand share tiers (Transaction optimized, Hot, Cool, Premium).
    * Mount Azure file shares on Windows, Linux, and macOS.
    * Understand use cases like lift-and-shift of on-premises file servers.
* **Create and configure a container in Blob Storage:**
    * Create blob containers within a storage account.
    * Set container public access levels (Private, Blob, Container).
    * Understand the difference between block blobs, append blobs, and page blobs. Focus on block blobs for general use.
* **Configure storage tiers (for blobs):**
    * Understand the different access tiers for block blobs:
        * **Hot tier:** Optimized for frequently accessed data.
        * **Cool tier:** Optimized for infrequently accessed data (stored for at least 30 days). Lower storage costs, higher access costs.
        * **Archive tier:** Optimized for rarely accessed data (stored for at least 180 days) that can tolerate several hours of retrieval latency. Lowest storage cost, highest retrieval cost.
    * Manually change blob tiers or use Lifecycle Management policies.
    * Understand rehydration process from Archive tier (Standard or High priority).
* **Configure soft delete for blobs and containers:**
    * Enable soft delete to protect blobs and containers from accidental deletion by retaining them for a specified period.
    * Configure retention policies.
    * Understand how to view and restore soft-deleted blobs and containers.
* **Configure snapshots and soft delete for Azure Files:**
    * **Share Snapshots:** Create point-in-time, read-only copies of your file shares. Useful for backups and recovering previous versions of files.
    * **Soft Delete for File Shares:** Protects file shares from accidental deletion. Deleted shares are retained for a configurable period.
* **Configure blob lifecycle management:**
    * Create rules to automatically transition blobs to cooler tiers (e.g., Hot to Cool, Cool to Archive) or delete blobs based on age or last modified date.
    * Apply lifecycle policies at the storage account level, targeting specific containers or blob subsets using prefixes.
* **Configure blob versioning:**
    * Enable blob versioning to automatically maintain previous versions of a blob when it's overwritten or deleted.
    * Understand how to list, access, and restore previous blob versions.
    * Works in conjunction with soft delete for comprehensive data protection.

### Deploy and manage Azure compute resources (20-25%)

This domain covers the deployment, configuration, and management of Azure Virtual Machines, containers, and Azure App Service.

#### Automate deployment of resources by using Azure Resource Manager (ARM) templates or Bicep files

* **Interpret an Azure Resource Manager template or a Bicep file:**
    * **ARM Templates (JSON):** Understand the basic structure: `$schema`, `contentVersion`, `parameters`, `variables`, `resources`, `outputs`. Be able to read a template and understand what resources it will deploy and how they are configured.
    * **Bicep Files (.bicep):** Understand Bicep as a domain-specific language (DSL) that uses declarative syntax to deploy Azure resources. It transpiles to ARM templates. Bicep is generally easier to read and write than JSON. Recognize basic Bicep syntax for parameters, variables, resources, and modules.
* **Modify an existing Azure Resource Manager template:**
    * Add or remove resources.
    * Change resource properties.
    * Modify parameters or variables.
    * Understand how to use functions and expressions in ARM templates.
* **Modify an existing Bicep file:**
    * Add or remove resource declarations.
    * Change resource properties.
    * Modify parameters or variables.
    * Understand how to use Bicep functions and expressions, and how to reference other resources symbolically.
* **Deploy resources by using an Azure Resource Manager template or a Bicep file:**
    * Deploy using Azure portal, Azure CLI (`az deployment group create`), Azure PowerShell (`New-AzResourceGroupDeployment`), or CI/CD pipelines.
    * Understand deployment modes (Incremental and Complete).
    * Provide parameter values during deployment (inline, parameter file, or Bicep params file).
* **Export a deployment as an Azure Resource Manager template or convert an Azure Resource manager template to a Bicep file:**
    * **Export Template:** Use the Azure portal (Resource Group -> Deployments -> Select a deployment -> Template) or from a resource itself to export an ARM template for existing resources. Understand that exported templates often need cleanup and parameterization.
    * **Convert ARM to Bicep:** Use the Bicep CLI command `bicep decompile <arm-template-file>` to convert an ARM template to a Bicep file.

#### Create and configure virtual machines

* **Create a virtual machine (VM):**
    * Select an image (Windows Server, Linux distributions from Azure Marketplace, or custom images).
    * Choose a VM size (series like Dv5, Ev5, Fsv2, etc., based on CPU, RAM, IOPS needs).
    * Configure networking: VNet, subnet, public IP, Network Security Group (NSG).
    * Configure storage: OS disk type (Standard HDD, Standard SSD, Premium SSD, Ultra Disk), data disks.
    * Set up administrator credentials (username/password or SSH key for Linux).
    * Understand options like Spot VMs, Azure Hybrid Benefit.
* **Configure Azure Disk Encryption (ADE):**
    * Understand ADE for encrypting OS and data disks of Azure VMs using BitLocker (Windows) or DM-Crypt (Linux).
    * Configure ADE using Azure Key Vault to store encryption keys.
    * Understand the process for enabling encryption on new and existing VMs.
* **Move a virtual machine to another resource group, subscription, or region:**
    * **Move between Resource Groups/Subscriptions (within the same region):** Use the Azure portal or CLI/PowerShell. Understand limitations (some resources might not be movable or require specific steps).
    * **Move between Regions:** This is a more complex process, typically involving Azure Site Recovery or re-deploying the VM in the target region and migrating data. Direct "move" is not supported for VMs across regions.
* **Manage virtual machine sizes:**
    * Resize a VM to a different size within the same VM series or to a different series (may require deallocation).
    * Understand the impact of resizing on cost and performance.
    * Check for size availability in the region.
* **Manage virtual machine disks:**
    * Add, detach, and manage data disks.
    * Expand disk sizes (OS and data disks, with OS considerations).
    * Configure disk caching (Read-only, Read-write, None).
    * Understand managed vs. unmanaged disks (focus on managed disks).
    * Create snapshots of disks for backup or creating new VMs.
* **Deploy virtual machines to availability zones and availability sets:**
    * **Availability Sets:** Protect against hardware failures within a datacenter. VMs are spread across Update Domains (UDs) and Fault Domains (FDs). Provides 99.95% SLA.
    * **Availability Zones:** Protect against datacenter failures. Physically separate locations within an Azure region, each with independent power, cooling, and networking. Deploy VMs across zones for higher availability (99.99% SLA for VMs in multiple zones).
    * Understand when to use each and how to configure them during VM deployment.
* **Deploy and configure an Azure Virtual Machine Scale Sets (VMSS):**
    * Understand VMSS for creating and managing a group of load-balanced VMs.
    * Configure scaling rules (manual or autoscale based on metrics like CPU utilization).
    * Deploy VMSS from an image or custom image.
    * Understand update policies (manual, automatic, rolling).
    * Integrate with Azure Load Balancer or Application Gateway.

#### Provision and manage containers in the Azure portal

* **Create and manage an Azure Container Registry (ACR):**
    * Understand ACR as a private Docker registry service for storing and managing container images.
    * Create an ACR instance (Basic, Standard, Premium SKUs).
    * Push and pull images to/from ACR using Docker CLI.
    * Configure authentication (admin user, service principal, managed identity).
    * Understand features like geo-replication (Premium SKU) and ACR Tasks for building images.
* **Provision a container by using Azure Container Instances (ACI):**
    * Understand ACI for running single Docker containers or simple applications without managing underlying VMs.
    * Deploy containers from Docker Hub, ACR, or other registries.
    * Configure CPU, memory, environment variables, and port mappings.
    * Understand use cases like simple web apps, task automation, build jobs.
* **Provision a container by using Azure Container Apps (ACA):**
    * Understand ACA as a serverless application-centric hosting service built on Kubernetes.
    * Deploy containerized applications and microservices.
    * Configure revisions, scaling rules (KEDA-based), ingress, Dapr integration.
    * Simpler than managing a full AKS cluster for many scenarios.
* **Manage sizing and scaling for containers, including Azure Container Instances and Azure Container Apps:**
    * **ACI:** Sizing is defined at deployment (CPU cores, memory). Scaling is typically by deploying more instances if needed (manual).
    * **ACA:** Configure minimum and maximum replicas. Define scaling rules based on HTTP traffic, KEDA-supported scalers (e.g., queue length, CPU/memory).

#### Create and configure Azure App Service

* **Provision an App Service plan:**
    * Understand that an App Service plan defines the region, features, size (SKU: Free, Shared, Basic, Standard, Premium, Isolated), and scale of the underlying compute resources for your web apps, API apps, mobile apps, and function apps.
    * Choose an appropriate pricing tier based on requirements (custom domains, SSL, slots, autoscale, VNet integration).
* **Configure scaling for an App Service plan:**
    * **Scale Up (Vertical Scaling):** Change the pricing tier of the App Service plan to get more CPU, memory, and features.
    * **Scale Out (Horizontal Scaling):** Increase or decrease the number of VM instances running your app within the App Service plan.
    * **Autoscale:** Configure rules to automatically scale out/in based on metrics (e.g., CPU percentage, memory percentage, queue length) or a schedule.
* **Create an App Service (Web App):**
    * Create a web app within an App Service plan.
    * Select a runtime stack (e.g., .NET, Node.js, Python, Java, PHP, Docker Container).
    * Deploy code using various methods (FTP, Git, Azure DevOps, GitHub Actions, ZIP deploy).
* **Configure certificates and Transport Layer Security (TLS) for an App Service:**
    * Upload your own SSL/TLS certificates (Standard tier or higher).
    * Use App Service Managed Certificates (free, auto-renewed for apex and subdomains).
    * Bind certificates to custom domains.
    * Enforce HTTPS. Configure minimum TLS version.
* **Map an existing custom DNS name to an App Service:**
    * Configure CNAME (for subdomains like www.contoso.com) or A records (for apex/root domains like contoso.com) with your DNS provider.
    * Validate domain ownership and add the custom domain to the App Service.
* **Configure backup for an App Service:**
    * Set up scheduled backups for app content and configuration.
    * Store backups in an Azure Storage account.
    * Restore an app from a backup.
    * Understand limitations (e.g., database backup might need separate configuration).
* **Configure networking settings for an App Service:**
    * **VNet Integration:** Allow your app to access resources in an Azure Virtual Network.
    * **Hybrid Connections:** Access on-premises resources without a VPN.
    * **Access Restrictions:** Control inbound traffic to your app (allow/deny based on IP addresses or service tags).
    * **Private Endpoints:** Expose your App Service privately within your VNet.
* **Configure deployment slots for an App Service:**
    * Understand deployment slots (e.g., staging, dev) as live apps with their own hostnames (Standard tier or higher).
    * Deploy new versions of your app to a non-production slot.
    * Test the new version in the slot.
    * Swap slots to move the new version to production with minimal downtime.
    * Swap with preview and roll back if needed.

### Implement and manage virtual networking (15-20%)

This domain covers the creation, configuration, and management of Azure virtual networks, including IP addressing, routing, DNS, load balancing, and network security.

#### Configure and manage virtual networks in Azure

* **Create and configure virtual networks (VNets) and subnets:**
    * Define an address space for the VNet (e.g., 10.0.0.0/16).
    * Create one or more subnets within the VNet's address space (e.g., 10.0.1.0/24, 10.0.2.0/24).
    * Understand subnet considerations (e.g., reserving IP addresses, NSG association, route table association, service endpoints, delegation).
* **Create and configure virtual network peering:**
    * Connect two VNets (in the same region or different regions - Global VNet Peering) to enable resources in them to communicate with each other using private IP addresses.
    * Understand that peering is non-transitive (if VNetA is peered with VNetB, and VNetB is peered with VNetC, VNetA is not automatically peered with VNetC).
    * Configure settings like "Allow virtual network access," "Allow forwarded traffic," and "Allow gateway transit/Use remote gateways."
* **Configure public IP addresses:**
    * Understand public IP addresses for enabling internet connectivity to Azure resources (VMs, Load Balancers, Application Gateways, etc.).
    * Differentiate between Basic and Standard SKU public IPs (Standard offers zone-redundancy and is closed by default to inbound traffic unless explicitly allowed by an NSG).
    * Associate public IPs with network interfaces (NICs) or public load balancers.
    * Configure DNS name labels for public IPs.
* **Configure user-defined network routes (UDRs):**
    * Understand how Azure routes traffic by default (system routes).
    * Create route tables with UDRs to override default routing behavior.
    * Direct traffic to a Network Virtual Appliance (NVA) for inspection, or force tunnel traffic to on-premises.
    * Associate route tables with subnets.
    * Define routes with address prefixes and next hop types (e.g., Virtual appliance, Virtual network gateway, Internet).
* **Troubleshoot network connectivity:**
    * Use tools like **IP Flow Verify** (in Network Watcher) to check if traffic is allowed/denied between a VM and an IP address.
    * Use **Next Hop** (in Network Watcher) to determine the next hop for traffic from a VM to a destination.
    * Check NSG rules, UDRs, VNet peering status, and DNS resolution.
    * Basic ping/traceroute from within VMs (if ICMP is allowed).

#### Configure secure access to virtual networks

* **Create and configure network security groups (NSGs) and application security groups (ASGs):**
    * **NSGs:** Act as a stateful firewall to filter network traffic to and from Azure resources in an Azure VNet.
    * Create inbound and outbound security rules based on priority, source/destination IP, port, and protocol (TCP, UDP, ICMP, Any).
    * Associate NSGs with NICs or subnets (subnet association is generally recommended for easier management).
    * Understand default NSG rules.
    * **ASGs:** Group VMs with similar functions (e.g., web servers, app servers). Use ASGs as source or destination in NSG rules, simplifying rule management for groups of servers.
* **Evaluate effective security rules in NSGs:**
    * Understand how NSG rules are processed (by priority).
    * Use the "Effective security rules" view for a NIC in the Azure portal to see the aggregated set of rules applied from both NIC-level and subnet-level NSGs.
    * Helps in troubleshooting connectivity issues caused by NSG rules.
* **Implement Azure Bastion:**
    * Understand Azure Bastion as a PaaS service that provides secure and seamless RDP/SSH connectivity to your VMs directly from the Azure portal over TLS, without needing a public IP on the VM.
    * Deploy an Azure Bastion host in your VNet (requires a dedicated subnet named `AzureBastionSubnet`).
    * Connect to VMs using Bastion.
* **Configure service endpoints for Azure platform as a service (PaaS):**
    * Extend your VNet's private address space and identity to supported Azure PaaS services (e.g., Azure Storage, Azure SQL Database).
    * Traffic to the PaaS service from the VNet uses the Azure backbone network, and you can restrict PaaS service access to specific subnets.
    * The PaaS service still has a public endpoint, but access can be locked down to your VNet.
* **Configure private endpoints for Azure PaaS:**
    * Provide private IP addresses from your VNet for Azure PaaS services (e.g., Azure Storage, Azure SQL Database, App Service).
    * Traffic to the PaaS service stays entirely within your VNet and the Microsoft backbone, never traversing the public internet.
    * Creates a network interface in your VNet for the PaaS service. Offers more granular network isolation than service endpoints.

#### Configure name resolution and load balancing

* **Configure Azure DNS:**
    * **Azure Private DNS zones:** Provide name resolution within a VNet and between peered VNets without needing custom DNS servers. Link private DNS zones to VNets for registration and resolution.
    * **Azure Public DNS zones:** Host your public DNS domains (e.g., contoso.com) in Azure. Manage DNS records (A, AAAA, CNAME, MX, TXT, SRV, etc.).
    * Understand how Azure provides internal DNS resolution by default (for resources in the same VNet).
    * Configure custom DNS servers for a VNet if needed.
* **Configure an internal or public load balancer:**
    * **Azure Load Balancer (Layer 4):** Distributes inbound traffic to backend pool members (VMs, VMSS instances).
    * **Public Load Balancer:** Uses a public IP to distribute internet traffic.
    * **Internal Load Balancer:** Uses a private IP to distribute traffic within a VNet.
    * Configure frontend IP configurations, backend pools, health probes, and load balancing rules.
    * Understand SKU differences (Basic vs. Standard - Standard is recommended, offers HA ports, outbound rules, more metrics).
* **Troubleshoot load balancing:**
    * Check health probe status (ensure backend instances are healthy).
    * Verify load balancing rules and NAT rules.
    * Ensure backend instances are responding correctly.
    * Check NSGs to ensure traffic is allowed to the load balancer and from the load balancer to backend instances.
    * Use Azure Monitor metrics for the load balancer.

### Monitor and maintain Azure resources (10-15%)

This domain focuses on using Azure Monitor to collect and analyze monitoring data, configure alerts, and implement backup and disaster recovery solutions.

#### Monitor resources in Azure

* **Interpret metrics in Azure Monitor:**
    * Understand that Azure Monitor collects metrics (performance counters, health data) from Azure resources.
    * Use Metrics Explorer in Azure Monitor to chart metrics, apply filters, and split data by dimensions.
    * Identify common metrics for VMs (CPU, memory, disk, network), storage accounts (capacity, transactions, latency), App Services (requests, response time, CPU), etc.
* **Configure log settings in Azure Monitor (Diagnostic Settings):**
    * Understand that Azure Monitor Logs (based on Log Analytics workspaces) stores log and performance data.
    * Create Diagnostic Settings for Azure resources to send platform logs (activity logs, resource logs) and metrics to:
        * Log Analytics workspace (for querying and analysis)
        * Azure Storage account (for archiving)
        * Azure Event Hubs (for streaming to external systems)
* **Query and analyze logs in Azure Monitor:**
    * Use Log Analytics workspaces to store and query log data.
    * Write queries using Kusto Query Language (KQL).
    * Understand basic KQL syntax (e.g., `search`, `where`, `summarize`, `project`, `render`).
    * Analyze activity logs (control plane events) and resource logs (data plane events).
* **Set up alert rules, action groups, and alert processing rules in Azure Monitor:**
    * **Alert Rules:** Define conditions (based on metrics, log queries, activity logs) that trigger alerts.
    * **Action Groups:** Define actions to take when an alert is triggered (e.g., send email, SMS, voice call, trigger an Azure Function, Logic App, webhook, ITSM tool).
    * **Alert Processing Rules (Preview):** Manage alerts at scale by applying actions or suppressing notifications based on defined criteria.
    * Configure alert severity, frequency, and logic.
* **Configure and interpret monitoring of virtual machines, storage accounts, and networks by using Azure Monitor Insights:**
    * **VM Insights:** Provides deeper monitoring of VM performance and health, including guest OS performance, processes, and dependencies (using Log Analytics agent and Dependency agent).
    * **Storage Insights:** Provides a unified view of storage account usage, capacity, performance, and availability.
    * **Network Insights (via Network Watcher):** Provides visibility into network topology, health, and metrics.
    * Understand how to enable and use these insights.
* **Use Azure Network Watcher and Connection Monitor:**
    * **Network Watcher:** A suite of tools for monitoring, diagnosing, and viewing metrics for Azure network resources.
        * Tools include: IP Flow Verify, Next Hop, NSG Diagnostic, VPN Troubleshoot, Packet Capture, Connection Troubleshoot.
    * **Connection Monitor:** Provides end-to-end connection monitoring between a source (e.g., VM) and a destination (e.g., another VM, FQDN, URI, IP address). Monitors reachability, latency, and topology changes.

#### Implement backup and recovery

* **Create a Recovery Services vault:**
    * Understand that Recovery Services vaults are used to manage backups and site recovery for Azure VMs, on-premises servers, SQL Server in Azure VM, Azure Files, etc.
    * Create a vault, specifying subscription, resource group, region, and storage redundancy (LRS/GRS).
* **Create an Azure Backup vault:**
    * Understand that Backup vaults are a newer type of vault designed for specific workloads like Azure Disks, Azure Blobs, and Azure Database for PostgreSQL. (AZ-104 primarily focuses on Recovery Services vaults for VMs and Files).
    * Know the distinction if it comes up, but Recovery Services vault is key.
* **Create and configure a backup policy:**
    * Define backup frequency (daily, weekly, etc.) and time.
    * Configure retention range for daily, weekly, monthly, and yearly recovery points.
    * Apply the backup policy to resources (e.g., Azure VMs, Azure File shares).
* **Perform backup and restore operations by using Azure Backup:**
    * **Backup:** Enable backup for VMs or Azure File shares. Monitor backup jobs.
    * **Restore:**
        * **VMs:** Restore a full VM, restore individual disks, or perform file/folder recovery from a VM backup without restoring the entire VM.
        * **Azure Files:** Restore an entire file share or individual files/folders.
    * Understand different restore options (e.g., create new VM, replace existing, restore to alternate location).
* **Configure Azure Site Recovery (ASR) for Azure resources (Azure-to-Azure DR):**
    * Understand ASR for replicating Azure VMs from a primary region to a secondary region for disaster recovery.
    * Set up ASR by configuring a Recovery Services vault, enabling replication for VMs, and defining replication policies.
    * Understand concepts like Recovery Point Objective (RPO) and Recovery Time Objective (RTO).
* **Perform a failover to a secondary region by using Site Recovery:**
    * Understand the difference between a test failover (non-disruptive) and a planned/unplanned failover.
    * Execute a failover to bring up replicated VMs in the secondary region.
    * Understand concepts like commit and re-protect (failback) after a disaster.
* **Configure and interpret reports and alerts for backups:**
    * Use Backup center or Recovery Services vault dashboards to monitor backup health, successful/failed jobs, and storage usage.
    * Configure built-in alerts for backup failures or warnings.
    * Use Azure Monitor and Log Analytics for more advanced reporting and alerting on backup data.
