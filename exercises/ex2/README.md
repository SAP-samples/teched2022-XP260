# Exercise 2 - Identity Authentication Service with multi-factor-authentication for a business app

In the previous exercise, you saw how to use a custom identity provider instead of SAP ID Service to authenticate users that access the SAP BTP Cockpit. One benefit of this integration is that you can now implement your company's multi-factor authentication (MFA) approach for users accessing the cockpit. 

## Exercise 2.1 Configuring the users that shall use MFA

As MFA reduces the usability of the authentication process, you wouldn't want to make it mandatory for everybody. In the first step, we will therefore create a group for those user that need to authenticate with MFA. For example these could be the users with administrative rights while pure viewers might not require MFA.

1. Open the administration console of your Identity Authentication service tenant ( bestrunXY.accounts.ondemand.com/admin/ ). You will also find it on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "User & Authorizations" --> "User Groups".

3. Click the "Create" button to create a group with the name "BTP_Admins" and display name "BTP Admins". Click "Create" to save the new group.

4. To assign users to the group, click the "Add" button above the list of users.

5. Mark your customer identity provider user in the list and click save. The user is now a member of the group "BTP_Admins"

## Exercise 2.2 Configuring MFA for accessing the SAP BTP Cockpit

In this step we will configure the Identity Authentication service to enforce MFA for users that try to access the SAP BTP Cockpit and are in the group of BTP Admins.

1. Choose the menu item "Applications & Resources" --> "Applications"

2. Click on the top level entry "SAP Business Technology Platform". The details for the identity provider configuration for accessing the cockpit are displayed

3. Choose the tab "Authentication and Access" and click on "Risk-Based Authentication"

4. The list of authentication rules is still empty. Click on "Create Rule"

5. In the "New Risk-Based Authentication Rule" dialog, set the action to "Two Factor Authentication" and the entry field "Two-Factor Methods" to "TOTP". Select the group "BTP_Admin" from the value help dialog of the field "Group" and click on "Create"

6. When the dialog is closed, click on "Save" to save the newly created authentication rule

Multi-factor authentication is now enabled for your user in the custom identity provider

## Exercise 2.3 Access the SAP BTP Cockpit with MFA

When you now authenticate with your custom identity provider to access the cockpit, MFA will be triggered.

1. Close the browser

2. Open the SAP BTP Cockpit URL. If you are authenticated with SAP ID Service, choose the menu item "Security" --> "Trust Configuration" and click in "Open" for your custom identity provider.

3. The logon page of your identity provider is displayed and you need to enter username and password

4. The page "Two-Factor Authentication" is displayed, where you can register a device that shall generate the time-based one-time passwords (TOTP). While you can use the mentioned SAP Authenticator app, the process also works with Google Authenticator, Microsoft Authenticator and most other authenticator apps

5. Open the authenticator app on your smart phone and create a new entry in it, by scanning the QR code

6. Enter the code that the authenticator app generates into the "Passcode" field and click on "Continue"

7. You have successfully authenticated an can access the SAP BTP Cockpit


## Summary

In this exercise you have learned how to protect access the SAP BTP Cockpit by enforcing MFA for a specific group of users. Please note that this only affects users in the "BTP Admins" group, when they try to access the SAP BTP Cockpit. You can still access the Identity Authentication console of your custom identity provider without MFA. 

Continue to - [Exercise 3 - Exercise 3 ](../ex3/README.md)
