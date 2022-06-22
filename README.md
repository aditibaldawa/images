**Xoriant Confidential**

![logo](https://adfs.xoriant.com/adfs/portal/logo/logo.png?id=9C59550B72BCCBCB24FF9D6D50CEDB5A517026716867E69D896C77E02979DDDE)


# AZX- AZURE ACCELERATOR


**The Utility Runbook**



**Restricted Rights Legend**
The information contained in this document is confidential and subject to change without notice. No 
part of this document may be reproduced or disclosed to others without the prior permission of Xoriant Corporation.    

**Copyright**
© Copyright 2022 Xoriant Corporation  
This is an uncontrolled copy when in printed form.

 


|    Owner   |    Abhi Sapre |
| ----------- | ----------- |
| **Draft Owner**      | Vinish Nair       |
| **Responsible Group**      | Shankar Sitaraman, Vinish Nair, Ajit Dharap, Yuvraj Rathod |
| **Revision Date**      |  |
| **Last Re-validation Date**      |  |
| **Abstract**      | An instruction guide to walk the utility ,features and functionalities. |
| **Applicability**      | An instruction guide to walk the utility ,features and functionalities. |
| **Status**      | Draft, |








 **Revision date**  -
 **Brief Description of change**  Initial Publication  
 **Revision Authority POC**  - Shankar Sitaraman
- For information about this document, contact: Team

 </br>


#### 1. Overview
#### 1.1.	Role Based Access Control (RBAC)
#### 1.2.	The Utility Admin login
#### 1.3.	Create Resource Group
#### 2. SaaS (Software as a Service)
#### 2.1.	Monitor
#### 2.2.	Policy
#### 3.	PaaS (Platform as a service)
#### 3.1.	SQL Database
#### 3.2.	Create SQL Server 
#### 3.3.	Key Vaults
#### 3.4.	App Services
#### 3.5.	Container Services
#### 3.5.1.	AKS Cluster Deployment
#### 3.5.2.	Container Registries
#### 3.5.3.	AKS App Deployment
#### 4.	IaaS (Infrastructure as a Service)
#### 4.1.	Virtual Network
#### 4.1.1.	Virtual Network
#### 4.1.2.	Network Security group
#### 4.2.	Storage Account
#### 4.3.	Virtual Machine
#### 4.3.1.	Create SSH KEY 

 </br> </br>



## 1.	Overview 
- Users can utilise a utility to access Azure services, which are divided into three categories: **SaaS**, **PaaS**, and **IaaS**. With greater efficiency, standardisation, and consistency, this simplified procedure would make governance and compliance to industry and organisational requirements for all Azure services much easier.
- This utility provides customized features or applications with minimum resources that are needed to set up the environment.

 ##### Services offered by AZX are listed below:


 1. ##### SaaS (Software as a Service)
     Monitor, Policy.

2. #####	PaaS (Platform as a service)
   SQL Database, Key Vaults, App Services, Container Services (AKS Cluster Deployment, Container Registries, AKS App Deployment)

3.  ##### IaaS (Infrastructure as a Service)
    Virtual Network (Virtual Network, Network Security Group), Storage Account, Virtual Machine.

 </br> </br>

##  2.  Role Based Access Control (RBAC)

- RBAC facilitates to configure role assignments that maps specific user to a specific scope item to perform authorized actions. By enabling RBAC, particular access will be granted to the end users to execute authorized actions. 
- Roles that have been configured are listed below:



| Sr. no      | Role | Resource Creation Scope|
| ----------- | ----------- | -----------|
| 1.      | Admin       | 	User Management
|         |             | 	Change Subscription
|         |             |   Add/Modify Service Principle
|         |             |  List of Compute Resources creation as lsited below:
|         |             |  o	Alert rule for monitor
|         |             | o	SQL Server.
|         |             | o	Database.
|         |             | o	Key Vaults.
|         |             | o	Manage App Service.
|         |             | o	Deploy new Service.
|         |             | o	AKS Cluster.
|         |             | o	 Populate Container Registries with images.
|         |             | o	Deploy App in AKS.
|         |             | o	 Virtual Network.
|         |             | o	 Network Security Group.
|         |             | o	 Storage Account.
|         |             |o	 Manage Virtual Machine.|
|   2.      |       Operaor      | Except User Management, Change Configuration (Subscription, Service Principle). All Resource Creation as Admin.|
|   3.      |       Auditor      | Read only access to all resources, configurations & users.|

 </br> </br>

### **1.2	The Utility Admin Login**
 1.	To access the admin interface, enter the admin credentials and click the Login button. An admin's login is depicted in the figure below.
  
    ![image](https://user-images.githubusercontent.com/87083633/174570590-894bd93f-0eb9-4e79-b24f-e6e2f2ff91bb.png)

 </br>

2.	After login, landing page displays 3 tiles: SaaS, PaaS, IaaS and drop-down lists on the top right-corner.

![image](https://user-images.githubusercontent.com/87083633/174587753-73b56805-5b05-43ce-ba3b-0abb1ef248a1.png)

 </br>


 -  In **User’s**     ![image](https://user-images.githubusercontent.com/87083633/174592814-6552b6cf-b75b-40ad-873f-2b0187825916.png)  icon drop down menu, you can Change password and can logout from the utility.
 
 - In **Setting’s**    ![image](https://user-images.githubusercontent.com/87083633/174592982-5e36fe11-5880-4f6c-81e0-f6686a73198c.png)          drop down menu, you can Switch Subscription and manage users. 

 </br>

3.	To add **Subscription**, you need to click on **_Switch Subscription_** option.

    ![image](https://user-images.githubusercontent.com/87083633/174593361-9bfa5f21-e1e2-4495-be74-89e903b9b70c.png)

4.	You can Change the password by clicking on **_Change Password_**.

#### _Note_ : 
-	Password must be at least 8 characters long (It should have at least 1 uppercase and 1 special characters).

 </br>

5.	User Management

    Click on the Settings icon   ![image](https://user-images.githubusercontent.com/87083633/174593760-a388b00b-614e-44cd-b232-60f6c8470677.png)  on the top right pane of the page. Click User Administration. 
    This will open the User Management page that lists the detailed information pertinent to RBAC. You can add a user with the help of Add User button, at the top right corner of the page.
    
     ![image](https://user-images.githubusercontent.com/87083633/174594057-15d7a3ae-dd52-48db-b5c9-1f92fafacd7a.png)


    




### Resources creation is elaborated from here on for which one must be part of either Admin or Operator role.
 </br> </br>

### **1.3  Resource Group**
   - A Resource Group is a container that holds related resources for an Azure solution. The Resource Group can include all the resources for the solution, or only those resources that user wants to manage as a group.

     </br>

**Create Resource Group**

 </br>

 1.	Select any AZX service that you want to use and click on **Create New**.

     ![image](https://user-images.githubusercontent.com/87083633/174595477-09c01d38-1f47-42da-84e4-a66c0d6121e0.png)


2.	Provide the following information:

     - **Name**: Enter Resource Group name.
    Ex: AzxdevtestIndia.
    -  **Region**: Select an Azure location. 
Ex: eastus or centralus or westcentralus or northcentralus or southcentralus  etc.

    ![image](https://user-images.githubusercontent.com/87083633/174595234-133906bd-f9d7-4e50-b628-3707b6e2a5e5.png)

 </br>

3.	Select **_Create_**.

 </br> </br>

## **2.SaaS (Software as a Service)**
-	SaaS allows you to connect to and use cloud-based apps over the Internet. When you are implementing a SaaS solution, you are responsible for configuring the SaaS solution. 

-	Services which are provided by AZX under SaaS are: **Monitor** and **Policy**.


 </br> 

### **2.1	Monitor**
- Azure Monitor helps you maximize the availability and performance of AKS application and services. It delivers a comprehensive solution for collecting, analyzing, and acting on telemetry from your cloud and on-premises environments.

- Alert Rules for Monitor is as shown below:

 </br>

![image](https://user-images.githubusercontent.com/87083633/174595658-6bd8ac5a-6ba5-42f9-a3a2-f89dcde7f2ca.png)

 </br>

- After selecting the Resource Group & AKS Cluster from the respective drop-down list then the values displayed are the Alert Name, Description, Condition, Target Resource, Actiongroup Name.

 </br>

**Create New Alert Rule**

 </br>

1.	Select **SaaS tile** > **Monitor**.

</br>

  ![image](https://user-images.githubusercontent.com/87083633/174595862-c085a89a-077b-4af0-b33f-57bcf990d786.png)

</br>

2.	Under Monitor Section
    - Select **Resource Group** or **_Create New_** > **AKS Cluster** > **_+New Alert Rule_**.
    
</br>

![image](https://user-images.githubusercontent.com/87083633/174598285-c0477b25-8aca-44fc-843c-fd959fee4259.png)

</br>

3.	Provide the information.
    - **Action Group** > select value from pull down menu or **_+Action Group_**.
    
       </br>

    ![image](https://user-images.githubusercontent.com/87083633/174598374-f28df673-d088-4272-8a94-00b501ae4701.png)

</br>

4.	Provide the information.

</br>

![image](https://user-images.githubusercontent.com/87083633/174598461-1f8425e9-6a53-448d-a1be-e1544182534b.png)

5.	Select **_Create_** button.

</br></br>

### **2.2  Policy**
- The three policy initiative types used in AZX are listed below:



| Policy Name     | Policy Version  | Policy Description |
| :---:        |    :----:   |          :---: |
| ISO      | ISO 27001:2013       | It enables organizations of any kind to manage the security of assets such as financial   information, intellectual property, employee details or information entrusted by third parties.       |
| NIST   | NIST SP 800-171 Rev. 2| The purpose of this publication is to provide federal agencies with recommended security requirements for protecting the confidentiality of CUI. |   
|    | NIST SP 800-53 Rev. 5 | This publication establishes controls for systems and organizations. The controls can be implemented within any organization or system that processes, stores, or transmits information. The use of these controls is mandatory for federal information systems.|    
|    | NIST SP 800-53 Rev. 4 | This publication provides a catalog of security and privacy controls for federal information systems and organizations and a process for selecting controls to protect organizational operations organizational assets, individuals, other organizations, and the Nation from a diverse set of threats.|   
| PCI      | PCI v3.2.1:2018       | The PCI DSS applies to all entities that store, process, and/or transmit cardholder data. It covers technical and operational system components included in or connected to cardholder data. If you accept or process payment cards, PCI DSS applies to you.|

- In AZX you can only assign policy initiative and only policy initiative are displayed.

- Assignment Summary of Policy is as shown below:

</br>

  ![image](https://user-images.githubusercontent.com/87083633/174598622-c1652e6b-84e5-4af0-b0c8-82a2a87d1fac.png)

</br>

- You need to select either of three initiatives, Policy Version and Resource Group from the respective drop downs to associate with the policy, the table will display Policy name, Description of Policy, Scope, Type.
- If users want to assign policy then user need to click on button named Assign Policy Initiatives. If policy is already assigned it will display “The Policy is already Assigned” as well as user can search by policy by typing policy name in search bar

#### _Note_ :
- Since User need to provide managed identity while assigning policy initiative we have set the default value for location as "centralindia" and identity type as "SystemAssigned".
- Also By default, enforcement mode is assigned to no enforcement\.

</br></br>

## **3.	PaaS (Platform as a Service)**

</br>

### **3.1	SQL Database**

</br>

•	Azure SQL Database is a fully managed platform as a service (PaaS) database engine\.

•	Dashboard of SQL Database

</br>

![image](https://user-images.githubusercontent.com/87083633/174598999-6b690597-aebf-462f-99a9-4877cad603cc.png)

**Create SQL Database**

1.	Select **PaaS tile** > **SQL Database**.

    ![image](https://user-images.githubusercontent.com/87083633/174599110-96edd58c-5251-4c07-bb30-56e857fe3bb9.png)

</br>

2.	Select the **Resource Group** or **_Create New_** > **SQL Server** or **_Create New_** > **_+SQL DATABASE_**.



    ![image](https://user-images.githubusercontent.com/87083633/174599210-e16311fd-cbe9-44b3-8918-1743173a54fc.png)

</br>

3.	Provide the information.

    ![image](https://user-images.githubusercontent.com/87083633/174599284-afcea659-92b4-4c2c-8cd7-bf2855d9edc2.png)


4.	Select **_Create_**.

</br>

#### **3.1.1	SQL Server**

</br>

**Create SQL Server**

1.	Select **Resource Group** or **_Create New_** > **SQL Server** or **_Create New_** > **_+SQL DATABASE_**. 


    ![image](https://user-images.githubusercontent.com/87083633/174600972-27f331b6-e496-4fb4-880a-6dcef1930a77.png)

</br>

2.	Provide the information.



    ![image](https://user-images.githubusercontent.com/87083633/174601076-5c109604-e829-47de-87b1-205837a45910.png)

</br>

3.	Select **_Create_**.
•	To delete SQL Database.

    Select Action >  ![image](https://user-images.githubusercontent.com/87083633/174601280-c8ca0a8b-ee7c-408b-ad74-71f0b66cf41d.png)

</br></br>

### **3.2	Key Vaults**

</br>

- Azure Key Vault is a cloud service for securely storing and accessing secrets. A secret is anything that you    want to tightly control access to, such as API keys, passwords, certificates, or cryptographic keys.

- **Secrets Management** - Azure Key Vault can be used to securely store and tightly control access to tokens, passwords, certificates, API keys, and other secrets.

- **Key Management** - Azure Key Vault can be used as a Key Management solution. Azure Key Vault makes it easy to create and control the encryption keys used to encrypt your data.

- **Certificate Management** - Azure Key Vault lets you easily provision, manage, and deploy public and private Transport Layer Security/Secure Sockets Layer (TLS/SSL) certificates for use with Azure and your internal connected resources.


**Create Key Vault** 

1.	Select **IaaS tile** > **Key Vault**.

    ![image](https://user-images.githubusercontent.com/87083633/174601471-e98492bd-779c-4d2f-b774-fa04ca0d7b7f.png)

</br>

2.	Select **Resource Group** or **_Create New_** > **_+Key Vault_**.

    ![image](https://user-images.githubusercontent.com/87083633/174601559-5ae38d73-4e24-4470-b11c-25be861f39f9.png)

</br>

3.	Provide the information.

    ![image](https://user-images.githubusercontent.com/87083633/174601657-1bf0cb5f-55f1-4969-aca9-524b93728854.png)

</br>

4.	Select **_Create_**.

</br>

 **Adding key**:


1.	Select **Resource Group** > Action >                         ![image](https://user-images.githubusercontent.com/87083633/174601735-faf09b2d-e64d-458a-baa1-d2b326f2d67e.png)



    ![image](https://user-images.githubusercontent.com/87083633/174601921-1753cf48-62f3-40f9-86b1-48a08ee0e0aa.png)

</br>

2.	Select **_+New_** > Provide the information > **_Add_**.  



    ![image](https://user-images.githubusercontent.com/87083633/174602129-75d98be1-da2f-4f0b-bf48-4126b5a92dd5.png)

</br>

**Adding secrets**:

1.	Select **Resource Group** > Action > ![image](https://user-images.githubusercontent.com/87083633/174602599-50fdde59-c396-46a8-bb21-e37c057cbb76.png)


    ![image](https://user-images.githubusercontent.com/87083633/174602710-2282c1a5-6454-45ed-af4e-91b42a1fef68.png)

2.	Select **_+New_** > Provide the information > **_Add_**.

    ![image](https://user-images.githubusercontent.com/87083633/174603157-cd9f7a53-738f-47f0-ad09-17cc36dcab74.png)

    </br>

**Adding Certificate**:


1.	Select Resource Group > Action > ![image](https://user-images.githubusercontent.com/87083633/174603316-9b219a89-ab87-4df7-93c9-aca768ff4ad3.png)


    ![image](https://user-images.githubusercontent.com/87083633/174603477-d9a6ca1a-032e-49ce-b3df-703643db45cb.png)

2.	Select **_+New_** > Provide the information > **_Add_**.

    ![image](https://user-images.githubusercontent.com/87083633/174603875-46dfc83c-3589-463b-a52b-c3e27b9efcd1.png)

	- When you click on Delete key vault, key vault gets deleted and along with-it keys, secrets and certificates also get deleted automatically.


</br></br>

### **3.3	App Services**
Azure App Service is a fully managed platform as a service (PaaS) offering for developers.

</br>

#### 3.3.1	App service
- Azure App Service enables you to build and host web apps, mobile back ends, and RESTful APIs in the programming language of your choice without managing infrastructure. It offers auto scaling and high availability, supports both Windows and Linux.
- Dashboard of App service is as shown below:



    ![image](https://user-images.githubusercontent.com/87083633/174604053-266bb61b-af31-4bae-986c-f607bee9744d.png)

</br>

- You need to either select the Resource Group or create new Resource group and the values displayed are Name, Status, Location, App Service Plan and Operating System.
- You can Start, Stop, Restart, Browse, Delete and Refresh the service.
- In AZX portal you can only manage the Application Service.
- 	When you click on delete the application gets deleted. 

</br></br>

#### 3.3.2	Deploy service
- Azure Deploy service can deploy any file with extension:  .JSON.

</br>

**Deploy service**
1.	Select **PaaS tile** > **App Service** > **Deploy Service**.


    ![image](https://user-images.githubusercontent.com/87083633/174604241-f89a9519-a808-4d1a-bec6-51bff8e0d788.png)

</br>

2.	Select **Resource Group** or **_Create New_** > Upload file (extension can be . JSON (ARM Template)).



    ![image](https://user-images.githubusercontent.com/87083633/174604808-4fb6f57e-39b4-4884-ae3f-43ca6bedb4fa.png)


</br></br>


### 3.4	Container Services
Containers are becoming the preferred way to package, deploy, and manage cloud applications. Azure Container Instances offers the fastest and simplest way to run a container in Azure, without having to manage any virtual machines and without having to adopt a higher-level service.

</br>

#### 3.4.1	AKS Cluster Deployment
•	Azure Kubernetes Service (AKS) simplifies deploying a managed Kubernetes cluster in Azure by offloading the operational overhead to Azure. As a hosted Kubernetes service, Azure handles critical tasks, like health monitoring and maintenance.

</br>

**Create AKS Cluster**

1.	Select **PaaS tile**  > **Container Service**  > **AKS Cluster Deployment**.



    ![image](https://user-images.githubusercontent.com/87083633/174605210-0e826b18-aeee-434e-9e07-43e5b2bb8ac5.png)


</br>

2.	Select **Resource Group** or **_Create New_** > **_+AKS Cluster_**. 



    ![image](https://user-images.githubusercontent.com/87083633/174605348-cb346e74-b684-4352-81f7-62d134ab1edb.png)

</br>

3.	Provide the information> select **_Deploy_**.
#### _Note_ :
- If you select Agent Pool Mode as System, then OS type available is Linux and if you selects Agent 
    - Pool Type as User then OS type available are Linux and Windows.
    - Disk Size should vary from 30 to 2048.
    - Max Pod Count should be from 30 to 250.



    ![image](https://user-images.githubusercontent.com/87083633/174605441-a7cc806e-2848-4457-8366-ca5597382bc0.png)

</br>

**Node Details**:
1.	Select **Resource Group** >   ![image](https://user-images.githubusercontent.com/87083633/174609447-8e29a437-45a7-4ab4-b9f8-e84e62edb501.png)     .



    ![image](https://user-images.githubusercontent.com/87083633/174609523-5a860742-d78b-4df0-a01e-152ae6c4ab50.png)

</br>

2.	Select **_+Node pool_**.

    ![image](https://user-images.githubusercontent.com/87083633/174609601-82d41bf6-dc47-48b8-94ac-908a692dcfae.png)

</br>

3.	Provide the information > **_Add_**.
#### _Note_ : 
- Pool Name should have only lowercase letters.
    - If you select OS Type is Linux, the Pool Name can have maximum 12 characters and if OS Type is Windows, the Pool Name can have maximum 6 characters
    - Disk Size should vary from 30 to 2048.
    - Max Pod Count should be from 30 to 250.

    ![image](https://user-images.githubusercontent.com/87083633/174609827-2210adb9-6281-4b0a-bcdf-c91e3e5e75bc.png)

</br>

4.	For Scale Node
Action >    ![image](https://user-images.githubusercontent.com/87083633/174610195-8d08f1f5-2ceb-4333-b30e-194eb2d6953c.png)


    ![image](https://user-images.githubusercontent.com/87083633/174610361-bc78ee95-0eb3-4351-bc6e-10d6a552292b.png)

    </br>

5.	Provide the information > Confirm.

    ![image](https://user-images.githubusercontent.com/87083633/174610777-351d257a-17b3-4998-abe0-c6434d8c867c.png)

- User can Enable and Disable Secret store CSI driver.

</br>

**Update Kubernetes version**:

1.	Select **Resource Group** > Action >  ![image](https://user-images.githubusercontent.com/87083633/174611086-83e60b1d-f398-4243-8d9c-21c5fba2dd2c.png)

    ![image](https://user-images.githubusercontent.com/87083633/174611228-177d214c-0d95-4135-9c08-1dde32f487ff.png)

   </br>

2.	Provide the information > **_Upgrade_**.

    ![image](https://user-images.githubusercontent.com/87083633/174611639-42cdfa69-e4d0-4385-a328-7ff80fbabc17.png)

</br>

**Kubernetes Dashboard**:

1.	Select **Resource Group** >      ![image](https://user-images.githubusercontent.com/87083633/174722882-d6b4fb5e-d591-4937-b513-60a268eedd36.png).

</br>

2.	Select Copy Token > **_Go to Dashboard_**.

    ![image](https://user-images.githubusercontent.com/87083633/174722975-682d7ac7-8c1a-4b9f-8e21-a87b1db43d29.png)

</br>

3.	Paste the token > **_Sign in_**.

    ![image](https://user-images.githubusercontent.com/87083633/174723035-566a28d0-5427-4aaa-ab3f-037d49f1c1ec.png)

</br>

4.	You will be redirected to Kubernetes Dashboard.

    ![image](https://user-images.githubusercontent.com/87083633/174723092-57cc4c4f-2ac6-472c-b5db-79b2c8870e9c.png)


</br></br>

#### 3.4.2.  Container Registries
- Azure Container Registry is a managed by private Docker registry service.
- 	It creates and maintains Azure container registries to store and manage user private Docker container images and related artifacts.

</br>

**Create Container Registries** 

1.	Select **PaaS tile**  > **Container service**  > **Container Registries Deployment** .

    ![image](https://user-images.githubusercontent.com/87083633/174723226-a407faf2-21da-4f72-9143-c77ba56a5b60.png)

    </br>

2.	Select **Resource Group** > **_Create New_** > **_+Registry_**.

    ![image](https://user-images.githubusercontent.com/87083633/174723352-fe8d907d-6a40-4c55-82d3-98946957647c.png)

    </br>

3.	Provide the information > **_Create_**.

    #### _Note_ :
    - Size are categorized into 3 types: Basic, Premium, Standard.
    
        ![image](https://user-images.githubusercontent.com/87083633/174723526-45bb3b6c-f60c-4c56-9df8-3c982275d84c.png)

</br>

**Import Images**:

1. 	Select  **_Import Images_**.

    ![image](https://user-images.githubusercontent.com/87083633/174723621-c6ad3c35-4fcf-4900-a3f1-14e38237f03b.png)

    </br>

2. 	User can import image in two ways ACR to ACR and Docker hub.

    ![image](https://user-images.githubusercontent.com/87083633/174723838-e1d06efd-b4bd-45c2-bcca-e1dc94343348.png)

</br>

**a.	ACR TO ACR**

</br>

1. 	Provide the information >  **_Import_**.

    ![image](https://user-images.githubusercontent.com/87083633/174724146-d8a86afd-baf6-4969-9d30-85455ee6f6a6.png)

</br>

**b.	Docker hub**

</br>

1. 	Provide the information > **_Import_**.

    ![image](https://user-images.githubusercontent.com/87083633/174724004-ad2ff141-fcc0-471d-a8cc-ba7faac9c3d8.png)

- When you click on delete ACR gets deleted.



  </br> </br> 

**3.4.3	  AKS App Deployment**
Azure Kubernetes Service (AKS) is a managed Kubernetes service that lets you quickly deploy.

Deploying details

</br>


1.	Select **PaaS tile** > **Container service** > **AKS App Deployment**.

    ![image](https://user-images.githubusercontent.com/87083633/174724197-2cc3f20a-c0e4-43fa-aa67-0b90ba900497.png)

    </br>

2.	Select > **Resource Group** or **_Create New_** > **AKS Cluster** > **import file**(.YAML,.YML) > **_Deploy Service_**.

    ![image](https://user-images.githubusercontent.com/87083633/174724234-0c20091a-26c3-4cda-9933-9a6baf7cf919.png)	


</br></br>


## 4.	IaaS (Infrastructure as a Service)
### 4.1	Virtual Network
- Azure Virtual Network (VNet) is the fundamental building block for user private network in Azure. VNet enables many types of Azure resources, such as Azure Virtual Machines (VM), to securely communicate with each other, the internet and on-premises networks.
- Azure virtual network enables Azure resources to securely communicate with each other, the internet, and on-premises networks. Key scenarios that user can accomplish with a virtual network include - communication of Azure resources with the internet, communication between Azure resources, communication with on-premises resources, filtering network traffic, routing network traffic, and integration with Azure services.
-  After clicking in IaaS tile of landing zone, Virtual Network tile is visible.
- Virtual network tile is divided into two parts Virtual Network and Network Security Group.

</br></br>

#### 3.1.1.	Virtual Network
- VNet is like a traditional network that user would operate in user own data center but brings with additional benefits of Azure's infrastructure such as scale, availability, and isolation.

</br>

**Create Virtual Network**

</br>

1.	Select **IaaS tile** >**Virtual Network** > **Virtual Network**.

    ![image](https://user-images.githubusercontent.com/87083633/174724296-47ed282b-c31d-401e-a38c-6f2e01fb3760.png)

    </br>

2.	Select **Resource Group** or **_Create New_** > **_+Vnet_**.

    ![image](https://user-images.githubusercontent.com/87083633/174724336-ff3e8e5e-559e-4bf4-8467-74c00ad48c3a.png)

    </br>

3.	Provide the information > **_+Add Subnet_**.

    ![image](https://user-images.githubusercontent.com/87083633/174724380-907a1aa3-e6b8-4eea-abee-c5f371b3c49c.png)

    </br>

4.	Provide the information > **_Add_**.

![image](https://user-images.githubusercontent.com/87083633/174724426-89c4aedc-e87d-4744-ba31-06f8011ce016.png)

</br>

- To delete subnet  select       ![image](https://user-images.githubusercontent.com/87083633/174601280-c8ca0a8b-ee7c-408b-ad74-71f0b66cf41d.png)


</br>

5.	Select **_Create_** . 

</br></br>

#### Virtual Network Peering

</br>

1.	Select **IaaS tile** > **Virtual Network** > **Network Security Group**.


    ![image](https://user-images.githubusercontent.com/87083633/174725857-cee18c8d-126e-4f24-9598-540186a7fabc.png)

    </br>

2.	Select **Resource Group** > **Virtual Network** > **Virtual Network Name link**.



    ![image](https://user-images.githubusercontent.com/87083633/174726525-d5c3cc6b-d59d-42e3-9e93-eb7822ea80f3.png)

    </br>

3.	You can create new peer by clicking on **_New button_** and as well can **_Reload_**.

    ![image](https://user-images.githubusercontent.com/87083633/174726628-29d171f5-f1c0-479b-80f5-a00f656a09a2.png)

    </br>

4.	Select **_New_** > Provide the information > **_Add_**

#### _Note_ : 
- By default the value of location is us_east.

    ![image](https://user-images.githubusercontent.com/87083633/174726842-c39b2d75-c1d1-4c5d-9189-83e90d8b5744.png)

    </br>


- When you delete Vnet related Subnet gets deleted.
- When you click on delete Vnet Perring gets deleted as well as there is separate option to delete Vnet peering.

</br></br>

#### 3.1.2.	Network Security Group
- User can use an Azure network security group to filter network traffic to and from Azure resources in an Azure virtual network. A network security group contains security rules that allow or deny inbound network traffic to, or outbound network traffic from, several types of Azure resources. For each rule, user can specify source and destination, port and protocol.

</br>

  **Security rules**:
  -  A network security group contains zero, or as many rules as desire. Each rule specifies the following properties:
**Name**: A unique name within the network security group.
**Priority**: A number between 100 and 4096. Rules are processed in priority order, with lower numbers processed before higher numbers.
**Source or Destination Address**: Any, or an individual IP address, classless inter-domain routing (CIDR) block (10.0.0.0/24, for example), service tag, or application security group. If user specify an address for an Azure resource, specify the private IP address assigned to the resource.
**Protocol**: ICMP, TCP, UDP, Any
**Source or destination port**: User can specify an individual or range of ports. For example, user could specify 80 or 10000-10005. Specifying ranges enables user to create fewer security rules.
**Action**: Allow or Deny

</br>

- Dashboard of Network Security Group (NSG) is as shown below:

    ![image](https://user-images.githubusercontent.com/87083633/174727001-fb6532e1-9bef-4f7a-90b3-7a73383a06e9.png)



    - Dashboard displays the NSG name, type (public or private), and action (Association and Disassociation).

</br>

**Create Network Security Group**

</br>

1.	Select **IaaS tile** > **Virtual Network** > **Network Security Group**.

    ![image](https://user-images.githubusercontent.com/87083633/174727078-84f309d5-87b8-4560-93ca-4400ceb01353.png)

    </br>

2.	Select **Resource Group** > **_+NSG_**.

    ![image](https://user-images.githubusercontent.com/87083633/174727153-ab632c42-5f76-428e-8591-3559c8a8dc32.png)

    </br>

3.	Provide **NSG Name** > **_Add Rule_**.

    ![image](https://user-images.githubusercontent.com/87083633/174727212-17e524e2-b29b-4948-97a2-a33c3c6f6fb0.png)

    </br>

4.	Provide the information > **_Create_**.

 </br>  

#### _Note_ : 
- Name (ex: rule0, rule1) and priority are defined in backend as user creates new rule priority values increases by 1.
- If user select type as Inbound then source address is 0.0.0.0/0 or *and it is public and if address if different then it is private.
- if user select type as outbound then it is private.

 ![image](https://user-images.githubusercontent.com/87083633/174727301-32ca6fc2-ffed-439b-bdba-dd362a18a0c2.png)

 </br>

5.	To **Associate Group** or **Disassociate Group** 
Select **_Vnet_** > **Subnet** > **_Associate or Disassociate_**.

    ![image](https://user-images.githubusercontent.com/87083633/174727672-b5d474f5-d20a-4edc-9169-bd9d275d4127.png)

</br></br>


### 3.2.	Storage Account
- A storage account is an Azure Resource Manager. Every Resource Manager resource, including an Azure storage account, must belong to an Azure Resource Group. A Resource Group is a logical container for grouping user Azure services. 
- When user create a storage account, user have the option to either create a new Resource Group or use an existing Resource Group.
- Dashboard for Storage account is as shown below:

![image](https://user-images.githubusercontent.com/87083633/174727835-a30c8206-57ca-42ec-b698-f33aec2d7cbd.png)

</br>

  - You need to either select the Resource Group or create new Resource group, after that the table displays the Storage account name,
Location, storage type(Blob storage, storage,storageV2) and can delete the storage account.

</br>

**Create Storage Account**

1.	Select **IaaS tile** > **Storage Account** .

    ![image](https://user-images.githubusercontent.com/87083633/174728562-440d7507-5a55-437a-9664-a9e0711d7802.png)

    </br>

2.	Select **Resource Group** or **_Create New_** > **_+ Storage Account_**.

    ![image](https://user-images.githubusercontent.com/87083633/174728620-3e4e0a6d-d2d5-417e-8d9b-676cf4a46e4a.png)


</br>

3.	Provide the information > **_Create_**.

![image](https://user-images.githubusercontent.com/87083633/174728679-5d36f7b3-30b4-457e-94b5-04556dfb358a.png)

- When you click on delete, Storage account gets deleted.


</br></br>

### 3.3.	Virtual Machine
- Azure virtual machines (VMs) can be created through the AZX. This method provides a browser-based user interface to create VMs and their associated resources.
- AZX allows deployment of Virtual Machine (VM) on Azure that runs on Windows and Linux operating system.


</br>

**Create Virtual Machine**

1.	Select **IaaS tile** > **Virtual Machine**.

    ![image](https://user-images.githubusercontent.com/87083633/174728733-d33dbab8-034d-4c96-b407-079b0a6c4ad1.png)

    </br>

2.	Under Virtual Machine Section
- In **Resource Group** pull down menu, choose **Resource Group** or select **_Create new_** resource group.
- In **Region** pull down menu, choose **Region**.
- In **Virtual Network** pull down menu, choose **Virtual Network**.

    ![image](https://user-images.githubusercontent.com/87083633/174728783-19764eea-0f7c-449d-a495-f884700d05ca.png)

    </br>

3.	Provide the information > **_+ Virtual Machine_**.

</br>

4.	Provide the information.

    #### _Note_ :  
    - If you select Image as Linux(You need to select SSH key or you can create new SSH Key).

        ![image](https://user-images.githubusercontent.com/87083633/174728976-6c0dc05a-73d9-4819-81d3-704724adf85f.png)

</br>

5.	If You want to create multiple Virtual Machines of same configuration then select **_Copy current VM config**.

    ![image](https://user-images.githubusercontent.com/87083633/174729060-395fe762-214a-445a-aa82-c515bac3e3a3.png)


</br>

6.	 If you want to create multiple Virtual Machines of different configuration the select **_Add new VM Config_** and to Delete VM select **_Delete VM_**.

       ![image](https://user-images.githubusercontent.com/87083633/174729117-4078747c-f914-4c34-b978-a3bf98b65e21.png)

       </br>

7.	Select **_Create_**.

</br></br>

#### 3.3.1.	SSH Key
- With a secure shell (SSH) key pair, user can create virtual machines (VMs) in Azure that use SSH keys for authentication.
 
 </br>

**Create SSH Key**
1.	 Select **SSH key** or select **_Create New_**.

        ![image](https://user-images.githubusercontent.com/87083633/174729156-7b26dae9-ebbf-4071-8012-26656d845ff3.png)

        </br>

2.	Provide the following information:
- **Key Name**: A unique name is required.
- 	Leave the other options to their defaults.

    ![image](https://user-images.githubusercontent.com/87083633/174729273-8b15be54-3b62-4db8-9a4a-fa964de2bc6b.png)

</br>

3.	Select **_Create_**. 

- Dashboard of Virtual Machine 

</br>

1.	Click on  **“+”** icon.

    ![image](https://user-images.githubusercontent.com/87083633/174729351-7990badb-fe35-49d9-82cc-8e51a812d860.png)
    - You can Start, Restart, Stop, Resize and Delete the Virtual Machine.
    
    ![image](https://user-images.githubusercontent.com/87083633/174729416-fcaa0331-b1b4-4fdc-ae84-f0cd41a9ebfb.png)


</br>

- 	**Add Disk**:

1.	Select **_Add disk_**.

</br>

2.	Provide the information.
#### _Note_ 
- storage type is categorized into 4 types:
	Premium_LRS (Disk size range : 32 to 32767), StandardSSD_LRS(Disk size range : 4 to 32767), Standard_LRS(Disk size range : 32 to 32767), UltraSSD_LRS(Disk size range : 32 to 32767).

    ![image](https://user-images.githubusercontent.com/87083633/174729499-1c5e9bc3-234c-4e5f-ad23-705671d09bd2.png)

    </br>

- **Resize**:

1.	Select **_Resize_** > **Size** > select **_Resize_**.

    ![image](https://user-images.githubusercontent.com/87083633/174729656-30cd2a2b-d192-4cf7-9255-25390a8cbe6f.png)

- When you select Delete only Virtual Machine, Public IP and Network Interface(netcards) gets deleted.
</br>





  





























































































































 























