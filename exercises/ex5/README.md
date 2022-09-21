# Exercise 5 - Cloud Connector Security

In this exercise you will learn about the security settings of the SAP Cloud Connector and our recommendations on how to handle them.

# Relevant Security Recommendations
- BTP-CLC-0008


## Exercise 5.1 Access the SAP Cloud Connector console

In this exercise...

1. Open the SAP Cloud Connector adminstration console at https://localhost:8443
<br><img src="/exercises/ex5/images/SCC_Logon.png" width="50%">

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
