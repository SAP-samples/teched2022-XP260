# Exercise 5 - Cloud Connector Security

In this exercise you will learn about the security settings of the SAP Cloud Connector and our recommendations on how to handle them.

# Relevant Security Recommendations
- BTP-CLC-0008
- BTP-CLC-0009
- BTP-CLC-0014
- BTP-CLC-0015
- BTP-CLC-0016
- BTP-CLC-0017
- BTP-CLC-0019

## Exercise 5.1 Access the SAP Cloud Connector console and connect your SAP BTP subaccount

In this exercise you will learn how to access the administration console of the SAP Cloud Connector and establish a connection to your subaccount in the cloud

1. Open the Windows file explorer and double click the batch file go.bat in the directory C:\TechEd\SCC_Portable
<br><img src="/exercises/ex5/images/SCC_Batch.png" width="70%">

⚠️ TODO: Handle Windows firewall warning if still required

2. Open the SAP Cloud Connector administration console at https://localhost:8443
<br><img src="/exercises/ex5/images/SCC_Logon.png" width="70%">

⚠️ TODO: Handle Chrome browser warning if still required

3. Enter then username "Administrator" and Password "manage" to login ( ⚠️ FOR SAP TESTERS: The password on the test image was already changed to "vegas22")

4. In the "Initial Setup" dialog, enter the current password "manage" and the new password "vegas22". Choose the installation type "Master", then click on "Save"
<br><img src="/exercises/ex5/images/SCC_Initial_Setup_Save.png" width="70%">

5. The "Define Subaccount" page of the connector is displayed, where you need to provide the connectivity information for your SAP BTP subaccount
<br><img src="/exercises/ex5/images/SCC_Define_Subaccount.png" width="70%">

6. Look up the required information on the overview page of your SAP BTP subaccount 
<br><img src="/exercises/ex5/images/Subaccount_Details.png" width="70%">

7. On the "Define Subaccount" page, select "US East (VA) - AWS" as the region. Copy the Subaccount ID from the subaccount overview page. Enter "TechEd Workshop" as the "Display Name". Then enter the logon e-mail and the password for your **SAP ID Service** user and click on "Save"
<br><img src="/exercises/ex5/images/SCC_Define_Subaccount_Save.png" width="70%">

8. You have now connected your SAP BTP subaccount with your SAP Cloud Connector 
<br><img src="/exercises/ex5/images/SCC_BTP_Connected.png" width="70%">

6. Open your SAP BTP Cockpit, navigate to the subaccount and choose the menu item "Connectivity" --> "Cloud Connectors". The connection to your on-premise SAP Cloud Connector is established
<br><img src="/exercises/ex5/images/SCC_BTP_Cockpit.png" width="70%">

## Exercise 5.2 Add a mapping to an on-premise system that shall be called from the cloud

The SAP Cloud Connector allows you to expose on-premise systems to the cloud in a controlled, secure way. In this exercise you will learn how to define the mapping based on the security recommendations.

1. Choose the menu item "TechEd Workshop" --> "Cloud To On-Premise" and click on the "Add" button
<br><img src="/exercises/ex5/images/SCC_Cloud_To_On-Premise.png" width="70%">

2. In the "Add System Mapping Dialog", select the back-end type "ABAP System" and click on "Next"
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping.png" width="70%"> 

3. Review the list of available protocols. We recommend to use the encrypted versions of the protocols whenever possible: HTTPS, LDAPS, RFC SNC and TCP SSL. For this exercise, select HTTPS and click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Protocol.png" width="70%"> 

4. Enter the details for the on-premise back-end system that shall be made available to the cloud. Then internal host is "ecc60.mycompany.corp", the port is 1443. Click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Internal.png" width="70%">

:bulb: For this TechEd workshop, we are working with dummy connections to explain the security recommendations. The internal host configured here does not really exist in the landscape

5. Enter the details for the virtual host. The entry fields are already prefilled with the values from the previous dialog page. However, as you can see in the dialog, we highly recommend to use a different host name here so as not to unnecessarily leak information about your on-premise hosts to the cloud. The virtual host name is "sales-system.cloud", the port is 443. Click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Virtual.png" width="70%">

6. Select "X.509 Certificate (Strict Usage) as the principal type and click on "Next"
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Principal.png" width="70%">

7. Select "Use Virtual Host" as host in the request header and click on "Next".
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Header.png" width="70%">

8. Leave the description empty and click on "Next", then click on "Finish"
<br><img src="/exercises/ex5/images/SCC_Add_System_Mapping_Finish.png" width="70%">

9. You have now successfully added a mapping to an internal system to the SAP Cloud Connector configuration
<br><img src="/exercises/ex5/images/SCC_Cloud_To_On-Premise_With_Entry.png" width="70%">

## Exercise 5.3 Restrict access to the on-premise system and only expose relevant capabilities

In this exercise you will specify, which resources of the on-premise system shall be exposed to the cloud. This is a critical step because it significantly reduces the potential attack surface of your on-premise application

1. In the "Cloud To On-Premise" dialog, click on the "Add" button in the section "Resources Of sales-system.cloud:443"
<br><img src="/exercises/ex5/images/SCC_Add_Resources_Button.png" width="70%">

2. In the "Add Resource" dialog you can now specify, which URL can be called from the cloud. Enter "/production/accounting" as the URL path and set the "AccessPolicy" to "Path Only", to prevent calls to sub-paths. 
<br><img src="/exercises/ex5/images/SCC_Save_Resources.png" width="70%">

:bulb: For an RFC-based ABAP connection you would add the names of allowed functions as resources

3. With this configuration, the connection to the on-premise system is now defined and the exposed resources are explicitly specified
<br><img src="/exercises/ex5/images/SCC_Cloud_To_On-Premise_With_Resources.png" width="70%">

## Exercise 5.4 Managing the allowed TLS cipher suites

By default, SAP Cloud Connector allows TLS connections based on all the cipher suites that are supported by the Java virtual machine. Some of these cipher suite are weaker than others. We recommend to disable all weak cipher suites that are not required for compatibility reasons.

1. In the SAP Cloud Connector administration console, choose the "Configuration" menu item
<br><img src="/exercises/ex5/images/SCC_Configuration.png" width="70%">

2. On the "User Interface" tab, scroll down to the "Cipher Suites" section and click on the "Edit" button
<br><img src="/exercises/ex5/images/SCC_Config_Cipher_Suites.png" width="70%">

3. Select the cipher suite "TLS_ECDH_RSA_WITH_AES_128_CBC_SHA" in the list of enabled cipher suites and click on the right arrow icon to move the entry to the list of disabled cipher suites
<br><img src="/exercises/ex5/images/SCC_Disable_Cipher_Suite.png" width="70%">

4. Click on the "Save" button to persist the change
<br><img src="/exercises/ex5/images/SCC_Save_Cipher_Suites.png" width="70%">

In this exercise you have learned how to manage the list of TLS cipher suites that SAP Cloud Connector supports. A TLS cipher suite consists of 3 parts: The key exchange, the encryption algorithm and the message digest algorithm. At this point in time, the following choices seem reasonable:
- For the key exchange, DHE or ECDHE in combination with ECDSA or RSA
- For the encryption algorithm, AES with GCM (Galois/Counter Mode)
- For the digest algorithm, SHA-256 or SHA-384

Of course, these recommendations are constantly evolving, and compatibility with an existing infrastructure needs to be considered.  

## Summary

You have now learned how to set up a connection from the cloud to an on-premise system in SAP Cloud Connector, based on our security recommendations.

