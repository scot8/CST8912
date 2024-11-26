**CST8912 – Cloud Solution Architecture**

**Graded Lab Activity \#9**

**Method1:**

1\. Configure Azure SQL database for Canada central region under your resource group cst8912-demo, choose single database under sql databases in sql deployment option

2\. Enter the following values in create database page and keep other properties with their default settings

Subscription: Select your Azure subscription

Resource group: CST8912demo

Database name: db8912

Server: Select Create new and create a new server with a unique name in any Canada central location. Use SQL authentication and specify your name as the server admin login and a suitably complex password (remember the password - you'll need it later!)

Server : db8912demo

Username:db8912yourname

Password: dfguyt@234!

Want to use SQL elastic pool?: No

Workload environment: Development

Compute + storage: Leave unchanged

Backup storage redundancy: Locally-redundant backup storage

![A screenshot of a computer Description automatically generated](media/dbd86015c086623656afb078a20ffaa3.png)

![A screenshot of a computer Description automatically generated](media/31af5f734356c0ae8c91f1cdcbd8a964.png)

3\. On the Create SQL Database page, select Next :Networking \>, and on the Networking page, in the Network connectivity section, select Public endpoint. Then select Yes for both options in the Firewall rules section to allow access to your database server from Azure services and your current client IP address.

![A screenshot of a computer Description automatically generated](media/f7e3419096cf1330df1173c43e198e32.png)

4\. Select Next: Security \> and set the Enable Microsoft Defender for SQL option to Not now.

![A screenshot of a computer Description automatically generated](media/fa6e370c56b93e459c8050a04460c78d.png)

5\. Select Next: Additional Settings \> and on the Additional settings tab, set the Use existing data option to Sample (this will create a sample database that you can explore later).

![A screenshot of a computer Description automatically generated](media/9889b424748ab343609d9c0d2ff87482.png)

6\. Select Review + Create, and then select Create to create your Azure SQL database.

![A screenshot of a computer Description automatically generated](media/e82a2bc42c57c2a0838d6c62d0e84853.png)

Task 3: Configure Data Classification  
  
In this task, you will explore and classify data in SQL database for GPDR and data protection compliance.

1.  On the SQL server blade, in the Settings section, click SQL Databases.
2.  On the SQL database blade, in the Security section, click Data Discovery & Classification.
3.  On the Data Discovery & Classification blade, click the Classification tab.
4.  Click the text message We have found 15 columns with classification recommendations displayed on blue bar at the top of the blade.

![A screenshot of a computer Description automatically generated](media/8311fd949e804d1e8301902b18b00503.png)

1.  Review the listed columns and the recommended sensitivity label.
2.  Enable the Select all checkbox and then click Accept Selected Recommendations.
3.  Once you have completed your review click Save.

![A screenshot of a computer Description automatically generated](media/7c806b4bc2c98f85ff15959fb8467036.png)

1.  Back on the Data Discovery & Classification blade Overview tab, note that it has been updated to account for the latest classification information.

![A screenshot of a computer Description automatically generated](media/9c76aefa89172c831a40293981e469ce.png)

Task 4: Configure Auditing

In this task, you will first configure server level auditing and then configure database level auditing.

1.  In the Azure portal, navigate back to the SQL Server blade.
2.  On the SQL Server blade, in the Security section, click Auditing.
3.  Set the Enable Azure SQL Auditing switch to ON to enable auditing
4.  Select the Storage checkbox and entry boxes for Subscription and Storage Account will display (create new storage account if not selected)
5.  Choose your Subscription from the dropdown list.
6.  Click Storage account and choose Create new.

![A screenshot of a computer Description automatically generated](media/59a1810ddbae182bd3406cedc81b967c.png)

![A screenshot of a computer Description automatically generated](media/f7c936bb9330d9f5896e22fe403b0d7d.png)

1.  Back on the Auditing blade, under Advanced properties set Retention (days) to 5.
2.  On the Auditing blade, click Save to save the auditing settings

![A screenshot of a computer Description automatically generated](media/71129e9578c5dcded852277bcd213da0.png)

1.  On the server blade, in the Settings section, click SQL Databases.
2.  On the SQL database blade, in the Security section, click Auditing.  
    Note: This is database level auditing. Server-level auditing is already enabled.

![A screenshot of a computer Description automatically generated](media/17de5b0fd32c303d659131c4cfcf57de.png)

1.  On your SQL database Overview page in the Azure portal, select Query editor (preview) from the left menu. Try to sign in, you might fail on password, firewall rule for your IP address, everything gets audited. Try successful login as well, run query and you might find more details in audit logs

![A screenshot of a computer Description automatically generated](media/0801db96bcee5d16472e543eee30d438.png)

1.  switch back to DB, Auditing and Click View Audit Logs.
2.  On the Audit records blade, note that you can switch between Server audit and Database audit.

![A screenshot of a computer Description automatically generated](media/7ae1c986979e52554fcb6b02fac1fa15.png)

![A screenshot of a computer Description automatically generated](media/63c6152ce18f900617dbfac7a0e84578.png)

Task 5: Clean up resources created during this lab

**Deliverable**: Delete all the resources created during this lab and document all the steps with screenshots in lab report.

![A screenshot of a computer Description automatically generated](media/9983d7ec419d887a2c02ef0a4b3944ba.png)
