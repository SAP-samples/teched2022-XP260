# Exercise 1 - Using a custom identity provider to authenticate platform users

In this exercise, we will create...

## Exercise 1.1 - Configure the global account cockpit to trust identity provider

First, we will change the trust configuration in the SAP BTP Cockpit to establish trust to your custom identity provider

1. Open the SAP BTP Cockpit for your global account. You will find the URL on the [Getting Started](/exercises/ex0) page

2. Note that the URL switches to "accounts.sap.com" and the login screen of the SAP ID Service is displayed
<br>![](/exercises/ex1/images/SAP_ID_Service.png)

3. Enter your credentials for SAP ID Service, which is the default identity provider for any new BTP global account

4. In the SAP BTP Cockpit Accdount Explorer, choose the menu item Security --> Trust Configuration
<br>![](/exercises/ex1/images/SAP_BTP_Cockpit_Account_Explorer.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

