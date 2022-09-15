# Accessing the BTP services

The following exercises require access to a BTP global account and a tenant of SAP Cloud Identity Services - Identity Authentication.

**Seat number**: XY

**SAP BTP Global Account**: XP260-0XY

**SAP BTP Sub Account**: XP260-0XY > xp260-0XY

😁 We need a list of URLs here that people can copy/paste. Can we put this here ? 😁

**Identity Authentication Service**: https://bestrunXY.accounts.ondemand.com/admin

| Seat Number | Global Account Cockpit | Identity Authentication Service console |
| ----------- | ---------------------- | --------------------------------------- |
| 01 | https://cockpit.eu10.hana.ondemand.com/cockpit/#/globalaccount/?????????????/accountModel&//?section=SubaccountsSection&view=TilesView | https://bestrun01.accounts.ondemand.com/ |

## Level 2 Heading

After completing these steps you will have....

1.	Click here.
<br>![](/exercises/ex0/images/00_00_0010.png)

2.	Insert this code.
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
