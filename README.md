# CST8912 - Cloud Solution Architecture

## Cloud Development and Operations

### CST8912_013 Cloud Solution Architecture 

##### Graded Lab Activity 3, Week 4


---

**Prepared By:**
Thoufeek Baber (041166788)

**Submitted to:**
Prof. Ragini Madaan

---

## Goal of this project:

Compose the appropriate networking, compute, storage, and database services to meet the operational requirements of various application scenarios. 

- **Design cloud architecture layers** and their function to maximize reliability and resiliency of application services.
  
- **Outline core architectural components** to meet the operational requirements of various application scenarios.
  
- **Describe cloud service models** (IaaS, PaaS, SaaS) and implement highly available and elastically scalable solutions.
  
- **Identify the core features of cloud computing** and their interactions with each service layer.


### Steps:

**1. Creating a storage account** - Create a storage account named `labtest8912` under student subscription and resource group `CST8912-demo` for region Canada central and select geo redundant storage **(geo redundant storage GRS)**, keep networking and data protection options default.


 ![Step 1 - Resource Group Creation](./Images/1.png "Resource Creation")
  *Figure 1: Image shows the overview of Resource Group ‘CST8912-demo’*

 ![Step 1 - Storage account Creation](./Images/2.png "Storage account Creation")
 *Figure 2: Image shows the overview of the storage labtest08913.*

**2. Change Redundancy** - Go to your storage account resource blade, in data management section, go to redundancy tab and change redundancy to `local redundant storage` from dropdown, and under settings choose configuration and set blob access tier to `cool` and save the change.

![Step 2 - Choosing Loaclly Redundant storage](./Images/3.png "Redundant storage")
*Figure 3: Image shows Redundancy set to local redundant storage.*

![Step 2 - Set blob access tier](./Images/4.png "Blob Access to cool")
*Figure 4: Change configuration Blob access tier to Cool*

**3. Creation of containers** - Under data storage left, click containers and add new container named `labtestcontainer8912` and select upload a blob and change the advance settings and change the access tier to `hot` and upload to folder named `sampletest8912`, browse the files from the sample files links shared in this lab (check with your instructor if you cannot find the sample file link)

![Step 3 - Preview storage account](./Images/7.png "storage account")
*Figure 5: Shows the overview of the Storage account created for this project.*


![Step 3 - Creating a storage container](.Images/5.png "preview storage container")
*Figure 6: Shows the overview of labtestcontainer8912 created for the project.*

![Step 3 - Folder and lab file](.Images/6.png "uploaded file and folder inside container")
*Figure 7: Shows the uploaded file/folder in the container.*


**4. Accessing file thorugh public domain** - Click the file uploaded in the container to see the configuration options and copy the blob url and open a new *private window* from the browser to paste the copied url 
note : The url should not work since the containers public access is set to private, resource was not found.  

![Step 4 - Accesing file using private window](./Images/8.png "failed access due to lack of authorization")
*Figure 8: Failed to access the file due to lack of access token*

**5. Creation of SAS Token** - On the file blade, click generate SAS and copy the SAS token generated and paste the blob SAS URL on the private window of the browser, you must be able to see the file.


![Step 5 - Creation of SAS Token](./Images/9.png "SAS Token")
*Figure 9: Shows the creation of SAS token for public domain access*

![Step 5 - Successfull download of file](./Images/10.png "file download")
*Figure 10: Image shows the successful download of the file using the SAS URL link.*


**6. Rule Creation** - On the container blade under data management tab go to `Lifecycle Management` and create a new rule name `myrule8912`, rule scope should be `limit blobs with filters` and blob type and blob subtype should be default, add condition if base blobs were last modified more than “15 days” ago then `move to cool storage`.


![Step 6 - Rule creation](./Images/11.png "created rule")
*Figure 11: Creation of rule name “myrule8912”.*

![Step 6 - Details of rule](./Images/12.png "Rule details")
*Figure 12: Shows details tab of the created Rule.*

![Step 6 - Cool storage info](./Images/14.png "Cool storage")
*Figure 13: image shows the settings move to cool storage after 15 days.*

**7. Deleting Resources** - After demo delete all the resources created during lab and create a lab report documenting all the steps with screenshots.

![Step 7 - Resource deletion](./Images/15.png "Deleting Resources")
*Figure 14: Shows the complete deletion of all the resources created for the project.*