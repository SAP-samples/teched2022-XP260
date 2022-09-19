# Exercise 2 - Identity Authentication Service with multi-factor-authentication for a business app

In the previous exercise, you saw how to use a custom identity provider instead of SAP ID Service to authenticate users that access the SAP BTP Cockpit. One benefit of this integration is that you can now implement your company's multi-factor authentication (MFA) approach for users accessing the cockpit. 

## Exercise 2.1 Configuring the users that shall use MFA

As MFA reduces the usbility of the authentication process, you wouldn't want to make it mandatory for everbody. In the first step, we will therefore create a group for those user that need to authenticare with MFA. For example these could be the users with administrative rights while pure viewers might not require MFA.

1. Open the administration console of your Identity Authentication service tenant ( bestrunXY.accounts.ondemand.com/admin/ ). You will also find it on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "User & Authorizations" --> "User Groups".

3. Click the "Create" button to create a group with the name "BTP_Admins" and display name "BTP Admins". CLick "Create" to save the new group.

4. To assign users to the group, click the "Add" button above the list of users.

5. Mark your customer identity provider user in the list and click save. The user is now a member of the group "BTP_Admins"

## Exercise 2.2 Configuring MFA for accessing the SAP BTP Cockpit

In this step we will configute the Identity Authentication service to enforce MFA for users that try to access the SAP BTP Cockpit and are in the group of BTP Admins.

1. Choose the menu item "Applications & Resources" --> "Applications"

2. Click on the top level entry "SAP Business Technology Platform". The details for the identity provider configuration for accessing the cockpit are displayed

3. Choose the tab "Authentication and Access" and click on "Risk-Based Authentication"

4. The list of authentication rules is still empty. Click on "Create Rule"

5. In the "New Risk-Based Authentication Rule" dialog, set the action to "Two Factor Authentication" and the entry field "Two-Factor Methods" to "TOTP". 



After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
