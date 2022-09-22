# Exercise 5 - Cloud Connector Security

In this exercise you will learn about the security settings of the SAP Cloud Connector and our recommendations on how to handle them.

# Relevant Security Recommendations
- BTP-CLC-0008


## Exercise 5.1 Access the SAP Cloud Connector console and connect your SAP BTP subaccount

In this exercise you will learn how to access the administration console of the SAP Cloud Connector and establish a connection to your subaccount in the cloud

1. Open the SAP Cloud Connector administration console at https://localhost:8443
<br><img src="/exercises/ex5/images/SCC_Logon.png" width="70%">

2. The overview page of the connector is displayed. Click on the button "Add Subaccount"
<br><img src="/exercises/ex5/images/SCC_Admin_Connector_Overview.png" width="70%">

3. You will find the information that you need at this point on the overview page of your SAP BTP subaccount 
<br><img src="/exercises/ex5/images/Subaccount_Details.png" width="70%">

4. In the "Add Subaccount Dialog", select "US East (VA) - AWS" as the region. Copy the Subaccount ID from the subaccount overview page. Enter "TechEd Workshop" as the "Display Name". Then enter the logon e-mail and the password for your **SAP ID Service** user and click on "Save"
<br><img src="/exercises/ex5/images/Add_Subaccount_Dialog.png" width="70%">

5. You have now connected your SAP BTP subaccount with your SAP Cloud Connector 
<br><img src="/exercises/ex5/images/SCC_Subaccount_Connected.png" width="70%">

6. Open your SAP BTP Cockpit, navigate to the subaccount and choose the menu item "Connectivity" --> "Cloud Connectors". The connection to your on-premise SAP Cloud Connector is established
<br><img src="/exercises/ex5/images/SCC_BTP_Cockpit.png" width="70%">

## Exercise 5.2 Add a mapping to an on-premise system that shall be called from the cloud

The SAP Cloud Connector allows you to expose on-premise systems to the cloud in a controlled, secure way. In this exercise you will learn how to define the mapping based on the security recommendations.

1. Choose the menu item "TechEd Workshop" --> "Cloud To On-Premise" and click on the "Add" button
<br><img src="/exercises/ex5/images/SCC_Cloud_To_On-Premise.png" width="70%">

2. In the "Add System Mapping Dialog", select the back-end type "ABAP System" and click on "Next"
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping.png" width="70%"> 

3. Review the list of available protocols. We recommend to use the encrypted versions of the protocols whenever possible: HTTPS, LDAPS, RFC SNC and TCP SSL. For this exercise, select HTTPS and click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Protocol.png" width="70%"> 

4. Enter the details for the on-premise back-end system that shall be made available to the cloud. Then internal host is "ecc60.mycompany.corp", the port is 1443. Click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Internal.png" width="70%">

:bulb: For this TechEd workshop, we are working with dummy connections to explain the security recommendations. The internal host configured here does not really exist in the landscape

5. Enter the details for the virtual host. The hist name is "sales-system.cloud", the port is 443. As you can see in the dialog, we highly recommend to use a different host name here so as to not unnecessarily leak information about your on-premise hosts to the cloud. Click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Virtual.png" width="70%">

6. Select "X.509 Certificate (Strict Usage) as the principal type and click on "Next"
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Principal.png" width="70%">

7. Select "Use Virtual Host" as host in the request header and click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Header.png" width="70%">

8. Leave the description empty and click on "Next", then click on "Finish"
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Finish.png" width="70%">

9. You have now successfully added a mapping to an internal system to the SAP Cloud Connector configuration
<br><img src="/exercises/ex5/images/SCC_Cloud_To_On-Premise_With_Entry.png" width="70%">



You now know ... 

## Exercise 3.3 TBD

When you ...

1. TBD

## Summary

TBD

Continue to - [Exercise 3 - Exercise 3 ](../ex3/README.md)
