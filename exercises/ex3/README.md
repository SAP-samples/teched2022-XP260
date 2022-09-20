# Exercise 3 - Security Recommendations regarding user access and authentication

In this exercise you will learn about further security recommendations that help protect your accounts from risks related to access and authentication. 

# Relevant Security Recommendations
- BTP-IAS-0001


## Exercise 3.1 Identify obsolete users

In the previous exercises you associated users to a global account or subaccount, to give them access. It makes sense to review on a regular basis whether the users actually need this access. After all, an abandoned account with high privileges could become an attack target.

1. Open the SAP BTP Cockpit. You will find the URL on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "Security" --> "Users" and click on the "Sort" button
<br><img src="/exercises/ex3/images/Cockpit_Users.png" width="50%">

3. Sort the list of users by Last Logon, ascending
<br><img src="/exercises/ex3/images/User_List_Sort.png" width="50%">

4. In the sorted list you will see at the top those users that have last signed in a long time ago. Maybe they don't need this access anymore?

5. Sort the list of users by Last Logon, descending. If there are any users that never used this account at all, then they will show up at the top of the page. These might be good candidates for a clean-up. 

## Exercise 3.2 Defining a custom password policy

In this step we will configure the Identity Authentication service to enforce MFA for users that try to access the SAP BTP Cockpit and are in the group of BTP Admins.

1. Choose the menu item "Applications & Resources" --> "Applications"
<br><img src="/exercises/ex2/images/BTP_Cockpit_Application.png" width="50%">

2. Click on the top level entry "SAP Business Technology Platform". The details for the identity provider configuration for accessing the cockpit are displayed
<br><img src="/exercises/ex2/images/Applications_Menu_Item.png" width="50%">

3. Choose the tab "Authentication and Access" and click on "Risk-Based Authentication"
<br><img src="/exercises/ex2/images/Overview_Authentication_And_Access.png" width="50%">

4. The list of authentication rules is still empty. Click on "Create Rule"
<br><img src="/exercises/ex2/images/Create_Rule_Button.png" width="50%">

5. In the "New Risk-Based Authentication Rule" dialog, set the action to "Two Factor Authentication" and the entry field "Two-Factor Methods" to "TOTP". Select the group "BTP_Admin" from the value help dialog of the field "Group" and click on "Create"
<br><img src="/exercises/ex2/images/Create_Rule_Dialog.png" width="50%">

6. When the dialog is closed, click on "Save" to save the newly created authentication rule
<br><img src="/exercises/ex2/images/Save_Rule.png" width="50%">

Multi-factor authentication is now enabled for your user in the custom identity provider

## Exercise 2.3 Access the SAP BTP Cockpit with MFA

When you now authenticate with your custom identity provider to access the cockpit, MFA will be triggered.

1. Close the browser

2. Open the SAP BTP Cockpit URL. If you are authenticated with SAP ID Service, choose the menu item "Security" --> "Trust Configuration" and click in "Open" for your custom identity provider.

3. The logon page of your identity provider is displayed and you need to enter username and password
<br><img src="/exercises/ex2/images/IAS_Username_Password.png" width="50%">

4. The page "Two-Factor Authentication" is displayed, where you can register a device that shall generate the time-based one-time passwords (TOTP). While you can use the mentioned SAP Authenticator app, the process also works with Google Authenticator, Microsoft Authenticator and most other authenticator apps

5. Open the authenticator app on your smart phone and create a new entry in it, by scanning the QR code

6. Enter the code that the authenticator app generates into the "Passcode" field and click on "Continue"
<br><img src="/exercises/ex2/images/IAS_Register_OTP.png" width="50%">

7. You have successfully authenticated an can access the SAP BTP Cockpit


## Summary

In this exercise you have learned how to protect access the SAP BTP Cockpit by enforcing MFA for a specific group of users. Please note that this only affects users in the "BTP Admins" group, when they try to access the SAP BTP Cockpit. You can still access the Identity Authentication console of your custom identity provider without MFA. 

Continue to - [Exercise 3 - Exercise 3 ](../ex3/README.md)
