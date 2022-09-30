# Exercise 4 - Security Recommendations regarding audit.log

In this exercise you will learn about security recommendations that help protect your accounts from risks related to the audit log.
The SAP Audit Log service is a platform service which stores all the audit logs written on your behalf by other platform services that you use. It allows you to retrieve the audit logs for your subaccount via the audit log retrieval API or view them using the SAP Audit Log Viewer service. The rention time is 90 days - there is currently no possibility to extend the retension time.
Therefore we reccommend to download regular audit logs and save them ideally in an existing and central audit log system of your choice. This can be done via the audit log retrieval API or in the SAP Audit Log Viewer service. 

# Relevant Security Recommendations
- BTP-AUD-0001


## Exercise 4.1 Configure the SAP Audit Log Viewer service

 In this excercise you will configure the SAP Audit Log Viewer service to see audit relevant log entries.

1. Open the SAP BTP Cockpit. You will find the URL on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "Security" --> "Role Collections" and click on the "+" button to create a new role collection
3. 
<br><img src="/exercises/ex4/images/CreateRoleCollection0.png" width="50%">

3. In the pop-up window enter the rolecollection name "Audit Log Viewer". In the description enter "View the audit relevant logs in the audit log viewer".
Click on the "Create"- button.

<br><img src="/exercises/ex4/images/CreateRoleCollection1.png" width="50%">

4. Now you can see the Audit Log Viewer role collection together with the other role collections. Click on ">" on the right side of the newly created role collection to open the details. 

<br><img src="/exercises/ex4/images/CreateRoleCollection2.png" width="50%">

5. In the extended window you can assign roles and users to the role collection. Start assigning the two roles of the audit log viewer service called " Auditlog_Auditor" to the role collection.
To do so click on the "Edit"-button.

<br><img src="/exercises/ex4/images/AssignRolestoRoleCollection1.png" width="50%">

6. In the edit mode search under role name for the two roles called "Auditlog_Auditor".

<br><img src="/exercises/ex4/images/AssignRolestoRoleCollection2.png" width="50%">

7. Mark the two roles called "Auditlog_Auditor" and click the "Add"-button. 

<br><img src="/exercises/ex4/images/AssignRolestoRoleCollection3.png" width="50%">

8. Go to the users column and enter the email adress of your user you are currently logged in to the cockpit. This can be either the user of the Default Identity Provider "BTP<XY>@example.com" or the user of your custom identity provider (bestrun0X-platform), which is "TechEdIAS@bestrun.com". 
Enter it in the "ID" field and the "Email" field.
 
<br><img src="/exercises/ex4/images/AssignUsertoRoleCollection1.png" width="50%"> 
 
 9. Click the "save" button to save your changes.
 
 <br><img src="/exercises/ex4/images/AssignUsertoRoleCollection2.png" width="50%"> 
 
 10. The result will be that the users assigned have the authorizations to use the the Audit Log Viewer service. You need to be logged in the cockpit with the user assinged the authorizations to be able to see the Viewer in the next step.
 
 <br><img src="/exercises/ex4/images/AssignUsertoRoleCollection3.png" width="50%">
 


## Exercise 4.2  Check the audit logs and download audit log entries via the SAP Audit Log Viewer service.

You can download the audit logs via the audit log retrieval API to import them into your SIEM system or you can download them via the Viewer User Interface to store them as backup in your files system.
Now you learn how to download them via the User Interface.

 1. Open the SAP BTP Cockpit. You will find the URL on the [Getting Started](/exercises/ex0) page.

 2. Navigate to "Servcies " > "Instances and Subscriptions". Under Subscriptions you will see the Audit Log Viewer service. Nex to the text field there is a link to the user interface. Click on it.
 
<br><img src="/exercises/ex4/images/GotoAuditlogviewer1.png" width="50%">
 
 3. In the newly opened Audit Log Viewer UI you can einter take the default timeframe or select a specific one to see the latest audit log entries. On the right side there is button to retrieve the logs after the selction of the timeframe.
 
 <br><img src="/exercises/ex4/images/Viewer1.png" width="50%">
 
4. Now you can see the log entries of the specific audit relevant changes which have been done lately. 

  <br><img src="/exercises/ex4/images/Viewer2.png" width="50%">
 
5. The retention period of the logs in the cloud foundry envrionment is 90 days. Therefore it is reccommended to backup the audit log files or import them via the audit log retrieval API into a SIEM system.  You can download the files from the user interface. To do so click on the download button in the middle of the headline.
 
 <br><img src="/exercises/ex4/images/Viewer2.png" width="50%">

6. In the pop-up window select place on your VM to save the "viewLogs.json" file. Clcik on "Save".
 
 <br><img src="/exercises/ex4/images/DownloadViewer3.png" width="50%">

You now know how to download the audit relevant log files for backup.

## Summary

In this exercise you have configured the SAP Audit Log Viewer service to see the audit relevant log entries. In addition, you have seen how to download the audit.log files before the retention period ends.

Continue to - [Exercise 5 - SAP Cloud Connector](exercises/ex5/)
 
FooterSAP
Open Source Wiki
SAP
SAP
Open Source Wiki
© 2022 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
