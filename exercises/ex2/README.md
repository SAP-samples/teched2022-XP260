# Exercise 2 - Protect access to the SAP BTP Cockpit with multi-factor-authentication

In the previous exercise, you saw how to use a custom identity provider instead of SAP ID Service to authenticate users that access the SAP BTP Cockpit. One benefit of this integration is that you can now implement your company's multi-factor authentication (MFA) approach for users accessing the cockpit. 

# Relevant Security Recommendations
- BTP-IAS-0001
- BTP-IAS-0026


## Exercise 2.1 Configuring the users that shall use MFA

As MFA reduces the usability of the authentication process, you wouldn't want to make it mandatory for everybody. In the first step, we will therefore create a group for those users that need to authenticate with MFA. For example, these could be the users with administrative rights while pure viewers might not require MFA.

1. Open the administration console of your Identity Authentication service tenant ( bestrunXY.accounts.ondemand.com/admin/ ). You will also find it on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "User & Authorizations" --> "User Groups" and click on the "Create" button
<br><img src="/exercises/ex2/images/CreateUserGroup.png" width="50%">

3. Create a group with the name "BTP_Admin" and display name "BTP Admin". Click "Create" to save the new group.
<br><img src="/exercises/ex2/images/Create_Group_Dialog.png" width="50%">

4. To assign users to the group, click the "Add" button above the list of users.
<br><img src="/exercises/ex2/images/Add_Users_to_Group.png" width="50%">

5. Mark your customer identity provider user in the list and click save. The user is now a member of the group "BTP_Admins"
<br><img src="/exercises/ex2/images/Add_User_And_Save.png" width="50%">

## Exercise 2.2 Configuring MFA for accessing the SAP BTP Cockpit

In this step we will configure the Identity Authentication service to enforce MFA for users that try to access the SAP BTP Cockpit and are in the group of BTP Admins.

1. Choose the menu item "Applications & Resources" --> "Applications"
<br><img src="/exercises/ex2/images/BTP_Cockpit_Application.png" width="50%">

2. Click on the top-level entry "SAP Business Technology Platform". The details for the identity provider configuration for accessing the cockpit are displayed
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

3. The logon page of your identity provider is displayed, and you need to enter username and password
<br><img src="/exercises/ex2/images/IAS_Username_Password.png" width="50%">

4. The page "Two-Factor Authentication" is displayed, where you can register a device that shall generate the time-based one-time passwords (TOTP). While you can use the mentioned SAP Authenticator app, the process also works with Google Authenticator, Microsoft Authenticator, and most other authenticator apps

5. Open the authenticator app on your smart phone and create a new entry in it, by scanning the QR code

6. Enter the code that the authenticator app generates into the "Passcode" field and click on "Continue"
<br><img src="/exercises/ex2/images/IAS_Register_OTP.png" width="50%">

7. You have successfully authenticated and can access the SAP BTP Cockpit


## Summary

In this exercise you have learned how to protect access the SAP BTP Cockpit by enforcing MFA for a specific group of users. Please note that this only affects users in the "BTP Admins" group, when they try to access the SAP BTP Cockpit. You can still access the Identity Authentication console of your custom identity provider without MFA. 

Continue to - [Exercise 3 - Security Recommendations regarding user access and authentication](../ex3/README.md)
