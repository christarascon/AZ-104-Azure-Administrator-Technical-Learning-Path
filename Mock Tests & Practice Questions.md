## 5. Mock Tests & Practice Questions

[Taking practice tests](https://www.edusum.com/microsoft/az-104-microsoft-azure-administrator) is crucial to assess your understanding, get familiar with the exam format and question types, and identify weak areas.

### AZ-104 Sample Questions and Answers

Prepare effectively for the Microsoft Azure Administrator AZ-104 exam with this curated set of [sample questions and answers](https://www.edusum.com/microsoft/microsoft-azure-administrator-az-104-certification-sample-questions). These questions closely align with the actual exam objectives, helping you assess your knowledge, identify gaps, and gain confidence before test day.

**Example Question Types:**

1. When the backups are deleted, how long are they preserved under soft delete?
    - b) 10 days
    - c) 7 days
    - d) 1 day

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: a
    </details>

2. You have an Azure Storage account named corpimages and an on-premises shared folder named \\server1\images. You need to migrate all the contents from \\server1\images to corpimages. Which two commands can you use?
Each correct answer presents a complete solution? Select all answers that apply.
    - a) Azcopy sync \\server1\images [https://corpimages.blob.core.windows.net/public](https://corpimages.blob.core.windows.net/public) -recursive
    - b) Azcopy copy \\server1\images [https://corpimages.blob.core.windows.net/public](https://corpimages.blob.core.windows.net/public) -recursive
    - c) Get-ChildItem -Path \\server1\images -Recurse | Set-AzStorageBlobContent -Container " corpimages"
    - d) Set-AzStorageBlobContent -Container "ContosoUpload" -File "\\server1\images" -Blob " corporateimages "

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: b, c
    </details>

3. What benefit does a Content Delivery Network (CDN) provide its users?
    - a) Allows you to reduce the traffic coming into a web server for static, unchanging files such as images, videos, and PDFs
    - b) Allows you to store data that can be retrieved later in an extremely fast and inexpensive manner
    - c) Allows you to keep temporarily session information on the web visitor such as their login ID or their name
    - d) For a small fee, Azure will take over management of your virtual machine, perform OS updates and ensure it's running well

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: a
    </details>

4. Which of the following Network watcher feature would you use for the following requirement?
Find out if a network security rule is preventing a network packet from reaching a virtual machine hosted in an Azure virtual network.
    - a) Packet Capture
    - b) IP Flow Verify
    - c) Traffic Analysis
    - d) Next Hop

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: b
    </details>

5. A company has started using Azure and set up a subscription. They want to see the costs being incurred for each type of resource. Which of the following can help you get these details?
    - a) Go to your Azure AD directory and go to Licences.
    - b) Go to your Subscription and go to Cost Analysis.
    - c) Go to your Azure AD directory and go to Cost Analysis.
    - d) Go to your Subscription and go to Resource Groups.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: b
    </details>

6. Users are reporting that when they attempt to access myapps.microsoft.com, they are prompted multiple times to sign in and are forced to use an account name that ends with onmicrosoft.com.
You discover that there is a UPN mismatch between Azure AD and the on-premises Active Directory. You need to ensure that the users can use single-sign-on (SSO) to access Azure resources.
What should you do first?
    - a) From the on-premises network, request a new certificate that contains the Active Directory domain name.
    - b) From the server that runs Azure AD Connect, modify the filtering options.
    - c) From the on-premises network, deploy Active Directory Federation Services in a clustered environment.
    - d) From Azure AD, add and verify a custom domain name.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: d
    </details>

7. You have an Azure subscription that contains a storage account named storage1 and a Microsoft Entra tenant named contoso.com. You plan to provide identity-based access to storage1. Which storage1 data service can be configured to use identity-based access?
    - a) file shares
    - b) tables
    - c) containers
    - d) queues

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: a
    </details>

8. While setting up Azure Site Recovery, in which region do you have to deploy the cache storage account?
    - a) Secondary region with RA-GRS
    - b) Primary and secondary regions
    - c) Secondary region
    - d) Primary region

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: d
    </details>

9. You have an Azure subscription that contains a virtual network named VNet1. You plan to enable VNet1 connectivity to on-premises resources by using an encrypted connection. What should you configure for VNet1?
    - a) a public IP address
    - b) a private endpoint connection
    - c) internet routing
    - d) a virtual network gateway

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: d
    </details>

10. In which format are NSG flow logs stored?
    - a) Markdown
    - b) YAML
    - c) JSON
    - d) XML

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: c
    </details>

### Free Practice Test Links
* **Microsoft Learn Practice Assessments:** Microsoft often provides free practice assessments on the [official AZ-104 exam page](https://learn.microsoft.com/en-us/credentials/certifications/azure-administrator/?practice-assessment-type=certification#certification-practice-for-the-exam). These are highly recommended. 
* **[EduSum](https://www.edusum.com/exams/sample-az-104-microsoft-azure-administrator-mc    - a):** Offers high-quality, exam-like practice tests designed to simulate the real exam environment, helping you build confidence and assess your readiness effectively. 
* **Various Blogs and Community Sites:** Some Azure community experts occasionally post sample questions or quizzes. Search for "AZ-104 free practice questions."

### Top 10 Most Commonly Asked AZ-104 Questions (Conceptual Areas)

This refers to topic areas frequently emphasized, not specific repeated questions.

1.  **NSG Configuration and Troubleshooting:** Understanding how NSGs work, rule processing, default rules, and how to troubleshoot connectivity blocked by NSGs (including effective security rules).
2.  **Azure Storage Account Configuration:** Choosing the right account type, performance tier, access tier (Hot/Cool/Archive), and redundancy options (LRS, GRS, ZRS, RA-GRS) based on scenarios.
3.  **Azure VM Deployment and Sizing:** Selecting appropriate VM sizes, understanding availability sets vs. availability zones, and deploying VMs.
4.  **Azure RBAC:** Assigning built-in roles at correct scopes (management group, subscription, resource group, resource) and understanding permission inheritance. Principle of least privilege.
5.  **Microsoft Entra ID User and Group Management:** Creating users/groups, dynamic group membership, and group-based licensing.
6.  **Azure Monitor - Alerts and Log Analytics:** Setting up alerts based on metrics or logs, and writing basic KQL queries to analyze data in Log Analytics.
7.  **Azure Backup and Restore for VMs:** Configuring backup policies, performing backups, and understanding restore options (full VM, disk, file-level).
8.  **VNet Peering:** Configuring peering between VNets (regional and global) and understanding its properties (non-transitive, gateway transit).
9.  **Azure App Service Plans and Deployment Slots:** Understanding App Service plan SKUs, scaling (up/out), and using deployment slots for safe deployments.
10. **ARM Templates / Bicep:** Basic understanding of how to read, modify, and deploy resources using ARM templates or Bicep.
