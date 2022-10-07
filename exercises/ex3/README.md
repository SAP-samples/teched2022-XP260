# Exercise 3 - Security Recommendations regarding user access and authentication

In this exercise you will learn about further security recommendations that help protect your accounts from risks related to access and authentication. 

# Relevant Security Recommendations
- BTP-UAA-0009
- BTP-IAS-0002


## Exercise 3.1 Identify obsolete users

In the previous exercises you associated users to a global account or subaccount, to give them access. It makes sense to review on a regular basis whether the users actually need this access. After all, an abandoned account with high privileges could become an attack target.

1. Open the SAP BTP Cockpit. You will find the URL on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "Security" --> "Users" and click on the "Sort" button
<br><img src="/exercises/ex3/images/Cockpit_Users.png" width="70%">

3. Sort the list of users by Last Logon, ascending
<br><img src="/exercises/ex3/images/User_List_Sort.png" width="70%">

4. In the sorted list you will see at the top those users that have last signed in a long time ago. Maybe they don't need this access anymore?

5. Sort the list of users by Last Logon, descending. If there are any users that never used this account at all, then they will show up at the top of the page. These might be good candidates for a clean-up. If there are no users that never used the account, then the top of the list shows the users that accessed the system most recently

## Exercise 3.2 Defining a custom password policy

By default, Identity Authentication service comes with 2 password policies, Standard and Enterprise. In this exercise you will learn how to define your password policy, based on your company's requirements.

1. Open the administration console of your Identity Authentication service tenant ( bestrunXY.accounts.ondemand.com/admin/ ). You will also find it on the [Getting Started](/exercises/ex0) page.

2. Choose the menu item "Applications & Resources" --> "Password Policies"
<br><img src="/exercises/ex3/images/Menu_Item_Password_Policies.png" width="70%">

3. Click on the button "Add Custom Policy". The dialog "Custom Password Policy" is displayed
<br><img src="/exercises/ex3/images/Custom_Password_Policy.png" width="70%">

4. Set the policy strength to 3. This implies that this policy has a higher priority than the existing policies "Standard" and "Enterprise". This becomes relevant when a user accesses applications with different password policy requirements. A password policy with strength 3 will also be accepted by applications that require strength 1 or 2.
💡 Identity Authentication service does not measure the strength of the policy that you define. It is up to you do decide, which properties are required for a password to be considered strong

5. Decide on the "Password Behavior". Should the user be able to reset an expired password with the old one, or should the user have to perform the password reset process?

6. Set the "Required character groups count" to 3. Identity Authentication Service supports 4 types of character groups, uppercase letters, lowercase letters, numbers, and symbols. With this setting you specific how many different groups need to be part of the password. 

7. Fill out the remaining fields of the "Custom Password Policy" dialog and click on "Add". Your new password policy is added to the top of the list as it has the highest strength

You now know how to create a custom password policy that you can use for additional protection of your applications. 

## Summary

In this exercise you have how to identity potentially abandoned user accounts. In addition, you have seen how you can define custom password policies in Identity Authentication service

Continue to - [Exercise 4 - Audit Logs](../ex4/README.md)
