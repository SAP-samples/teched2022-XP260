# Exercise 3 - Security Recommendations regarding user access and authentication

In this exercise you will learn about further security recommendations that help protect your accounts from risks related to access and authentication. 

# Relevant Security Recommendations
- BTP-UAA-0009
- BTP-IAS-0002


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

By default, Identity Authentication service comes with 2 password policies, Standard and Enterprise. In this exercise you will learn how to define your password policy, based on your company's requirements.

1. Open the administration console of your Identity Authentication service tenant ( bestrunXY.accounts.ondemand.com/admin/ ). You will also find it on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "Applications & Resources" --> "Password Policies"
<br><img src="/exercises/ex3/images/Menu_Item_Password_Policies.png" width="50%">

3. Click on the button "Add Custom Policy". The dialog "Custom Password Policy" is displayed
<br><img src="/exercises/ex3/images/Custom_Password_Policy.png" width="50%">

You have now...

## Exercise 3.3 TBD

When you ...

1. TBD

## Summary

TBD

Continue to - [Exercise 3 - Exercise 3 ](../ex3/README.md)
