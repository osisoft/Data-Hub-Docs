---
uid: sign-in-cnnxt
---

# Sign in to AVEVA™ Connect 

This topic explains how to navigate to AVEVA™ Data Hub via [AVEVA™ Connect](https://connect.aveva.com/) for the following types of accounts:

* [Single user sign-in](#single-user-sign-in)
* [Corporate sign-in: Federation for single sign-on](#corporate-sign-in:-federation-for-single-sign-on)
* [Users with access to multiple accounts](#users-with-access-to-multiple-accounts)
* [Third-party user access](third-party-user-access)

## Single user sign-in

To sign in as a single user, follow these steps:

1. Open the [AVEVA™ Connect page](https://connect.aveva.com/). 

1. Sign in with your credentials. 
    
    **Result:** The AVEVA™ Connect home page is displayed.

    **Note:** If you attempt a sign-in ten times consecutively with a wrong password from the same location (IP address), then your login will be blocked. If this happens, contact AVEVA™ Global Customer Support to unlock your account.

1. From the AVEVA™ Connect home page, click on the folder that represents your organization's services.

   **Result:** A tile or set of tiles that represents the service(s) you have access to is displayed below the folder.    

1.  Click anywhere on the appropriate tile to launch the AVEVA Data Hub service you wish to use.

   **Result:** The AVEVA Data Hub portal opens. 
     
<!--VTT, 11/4/21 - Question for SME: Are these other sign in procedures necessary?-->
   
## Corporate sign-in: Federation for single sign-on

Some AVEVA™ Connect accounts are configured to use Active Directory Federation, which enables authentication and authorization to AVEVA™ Connect applications using the corporate user identity. This enables you to use single sign-on with the user account from the corporate domain.

1. Open the [AVEVA™ Connect page](https://connect.aveva.com/). 

If single sign-on is enabled, you only need to provide your email address when signing in to AVEVA™ Connect. 

**Note:** You may be prompted to sign into your corporate Sign-In page.

1. From the AVEVA™ Connect home page, click on the folder that represents your organization's services.
   
   **Result:** The applications available from this namespace account are displayed below the folder. 
     
1. Click on the tile that represents AVEVA™ Data Hub.

   **Result:** The AVEVA™ Data Hub window opens. 

## Users with access to multiple accounts

In some cases, you may have access to several accounts in AVEVA™ Connect, for example, to access a training environment. In such cases, you are presented with an additional screen to select an account to sign in to.

## Third-party user access

A connection code enables third-party users to access specific accounts associated with an Identity Provider. Any accounts that are not intended for the third-party user are hidden.

**Note:** You must have a federated connection.

Follow these steps to sign in as a third-party user using a connection code.

1.	On the AVEVA™ Connect login page, enter your email address.

1.	Click **Have a connection code?**.

    ![Connection code screen](images/cnnxtn-code-3rd-party.png)

1.	Enter your connection code. This is provided by AVEVA™.
 
    **Note:** A direct sign-in link can be provided to enable quick access to restricted accounts. The third-party user will receive an email invitation that contains the direct link.

1.	Click **Next**.

1.	Click on the desired account.

    **Result:** The AVEVA™ Connect home page is displayed for the selected account.