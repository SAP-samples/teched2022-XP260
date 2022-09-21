# Exercise 5 - Cloud Connector Security

In this exercise you will learn about the security settings of the SAP Cloud Connector and our recommendations on how to handle them.

# Relevant Security Recommendations
- BTP-CLC-0008


## Exercise 5.1 Access the SAP Cloud Connector console

In this exercise...

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

6. Open your SAP BTP Cockpit, navigate to the subaccount and choose the menu item "Connectivity" --> "Cloud Connectors". The connection to your on-premise SAP Cloud Connector is shown
<br><img src="/exercises/ex5/images/SCC_BTP_Cockpit.png" width="50%">

## Exercise 3.2 Defining a custom password policy

By default, Identity Authentication service comes with 2 password policies, Standard and Enterprise. In this exercise you will learn how to define your password policy, based on your company's requirements.

1. Open the administration console of your Identity Authentication service tenant ( bestrunXY.accounts.ondemand.com/admin/ ). You will also find it on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "Applications & Resources" --> "Password Policies"
<br><img src="/exercises/ex3/images/Menu_Item_Password_Policies.png" width="50%">

3. Click on the button "Add Custom Policy". The dialog "Custom Password Policy" is displayed
<br><img src="/exercises/ex3/images/Custom_Password_Policy.png" width="50%">

4. Set the policy strength to 3. This implies that this policy has a higher priority than the existing policies "Standard" and "Enterprise". This becomes relevant when a user accesses applications with different password policy requirements. The password policy with strength 3 will also be accepted by applicatioins that require strength 1 or 2.
💡Identity Authentication service does not measure the strength of the policy that you define. It is up to you do decide, which properties are required for a password to be considered string

5. Decide on the "Password Behavior". Should the user be able to reset an expired password with the old one, or should the user have to perform the password reset process?

6. Fill out the remaining fields of the "Custom Password Policy" dialog and click on "Add". Your new password policy is added to the top of the list as it has the highest strength

You now know how to create a custom password policy that you can use for additional protection of your applications. 

## Exercise 3.3 TBD

When you ...

1. TBD

## Summary

TBD

Continue to - [Exercise 3 - Exercise 3 ](../ex3/README.md)
