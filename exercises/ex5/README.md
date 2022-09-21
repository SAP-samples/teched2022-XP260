# Exercise 5 - Cloud Connector Security

In this exercise you will learn about the security settings of the SAP Cloud Connector and our recommendations on how to handle them.

# Relevant Security Recommendations
- BTP-CLC-0008


## Exercise 5.1 Access the SAP Cloud Connector console and connect your SAP BTP subaccount

In this exercise you will learn how to access the administration console of the SAP Cloud Connector and establish a connection to your subaccount in the cloud

1. Open the SAP Cloud Connector adminstration console at https://localhost:8443
<br><img src="/exercises/ex5/images/SCC_Logon.png" width="50%">

2. The overview page of the connector is displayed. Click on the button "Add Subaccount"
<br><img src="/exercises/ex5/images/SCC_Admin_Connector_Overview.png" width="50%">

3. You will find the information that you need at this point on the overview page of your SAP BTP subaccount 
<br><img src="/exercises/ex5/images/Subaccount_Details.png" width="50%">

4. In the "Add Subaccount Dialog", select "US East (VA) - AWS" as the region. Copy the Subaccount ID from the subaccount overview page. Enter "TechEd Workshop" as the "Display Name". Then enter the logon e-mail and the password for your **SAP ID Service** user and click on "Save"
<br><img src="/exercises/ex5/images/Add_Subaccount_Dialog.png" width="50%">

5. You have now connected your SAP BTP subaccount with your SAP Cloud Connector 
<br><img src="/exercises/ex5/images/SCC_Subaccount_Connected.png" width="50%">

6. Open your SAP BTP Cockpit, navigate to the subaccount and choose the menu item "Connectivity" --> "Cloud Connectors". The connection to your on-premise SAP Cloud Connector is established
<br><img src="/exercises/ex5/images/SCC_BTP_Cockpit.png" width="50%">

## Exercise 5.2 Add a mapping to an on-premise system that shall be called from the cloud

The SAP Cloud Connector allows you to expose on-premise systems to the cloud in a controlled, secure way. In this exercise you will learn how to define the mapping based on the security recommendations.

1. TBD

You now know ... 

## Exercise 3.3 TBD

When you ...

1. TBD

## Summary

TBD

Continue to - [Exercise 3 - Exercise 3 ](../ex3/README.md)
