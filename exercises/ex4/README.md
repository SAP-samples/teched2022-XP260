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
<br><img src="/exercises/ex4/images/CreateRoleCollection0.png" width="50%">

3. In the pop-up window enter the rolecollection name "Audit Log Viewer". In the description enter "View the audit relevant logs in the audit log viewer".
Click on the "Create"- button.
<br><img src="/exercises/ex4/images/CreateRoleCollection1.png" width="50%">

4. Now you can see the Audit Log Viewer role collection togehter with the other role collections. Click on ">" on the right side of the newly created role collection to open the details. 
<br><img src="/exercises/ex4/images/CreateRoleCollection2.png" width="50%">

5. In the extended window you can assign roles and users to the role collection. Start assigning the two roles of the audit log viewer service to the role collection.
To do so click on the "Edit"-button.
<br><img src="/exercises/ex4/images/AssignRolestoRoleCollection1.png" width="50%">

## Exercise 4.2  Download audit log entries via the User Interface 

You can download the audit logs via the audit log retrieval API to import them into your SIEM system or you can download them via the Viewer User Interface to store them as backup in your files system.
Now you learn how to download them via the User Interface.

1. ..... You will also find it on the [Getting Started](/exercises/ex0) page.

2. ......

3. ....

4.  ....

5. 

6. 
7. 

You now know how to download the audit relevant log files for backup.. 

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
