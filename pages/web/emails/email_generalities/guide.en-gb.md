---
title: 'Getting started with the MX Plan solution'
slug: web_hosting_an_overview_of_ovh_email
excerpt: 'Find out how to get started with an MX Plan solution'
section: 'Getting started'
order: 01
---

**Last updated 19th July 2021**

## Objective

If you have just purchased an MX Plan solution, this means you have email addresses that you can use to send and receive messages from a device of your choice.

**Find out how to get started with an MX Plan solution.**

## Requirements

- an MX plan solution, This is available via: a [web hosting plan](https://www.ovhcloud.com/en-gb/web-hosting/), a  [free Start 10M hosting plan](https://www.ovhcloud.com/en-gb/domains/free-web-hosting/), or an MX Plan solution only
- access to the [OVHcloud Control Panel](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.co.uk/&ovhSubsidiary=GB), and `Web Cloud`{.action} section

## Instructions <a name="instructions"></a>

Once the MX Plan solution has been created and is available, you can manage it from the [OVHcloud Control Panel](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.co.uk/&ovhSubsidiary=GB). Depending on its activation date or if [it has been migrated recently](https://www.ovh.co.uk/mxplan-migration/), you may have the old or new version of the solution. You will need to check this before you proceed any further.

To do this, log in to the [OVHcloud Control Panel](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.co.uk/&ovhSubsidiary=GB), and open the Web Cloud section. Click `Emails`{.action} in the services bar on the left-hand side, then choose the name of the plan concerned. Continue with the next steps, depending on which version you own.

|MX Plan legacy version|MX Plan new version|
|---|---|
|![email](images/mxplan-starter-legacy-step1.png){.thumbnail}<br> Find the solution in the "Subscription" box|![email](images/mxplan-starter-new-step1.png){.thumbnail}<br>Locate the "Server model" in the "Summary" box|
|Continue to [Legacy version of the MX Plan solution](#oldmxplan)|Continue to [New version of the MX Plan solution](#newmxplan)|

### New version of the MX Plan solution <a name="newmxplan"></a>

#### Accessing your solution management

If you are using the new version of the MX Plan solution, this is the display you should get. If not, please ensure you follow the right path [by referring to the information above](#instructions).

![email](images/mxplan-starter-new-step1.png){.thumbnail}

#### Adding an email account

To configure your email addresses, go to the `Email accounts`{.action} tab. The window that opens will list the accounts that are already available, as well as those that you can still create. To add a new email account, click `Add account`{.action}.

![email](images/mxplan-starter-new-step2.png){.thumbnail}

In the pop-up window, enter the following information:

|Information|Description|
|---|---|
|Email account|A temporary name is already pre-filled in the text box: delete it and enter your new email address (e.g. firstname.surname). The domain name for the email address is already pre-selected in the list.|
|First name|Enter a first name.|
|Last name|Enter a last name.|
|Display name|Enter the name that will be displayed when sending emails from this address.|
|Password|[Enter and confirm a password](https://docs.ovh.com/gb/en/customer/manage-password/). For security reasons, we recommend not using the same password twice, choosing one that does not contain any personal information (e.g. your surname, first name and date of birth) and we also recommend renewing it regularly.|

Once you have completed the text fields, click `Next`{.action} and then check the information that appears in the summary. If it is all correct, click `Confirm`{.action} . Repeat this step as necessary according to the number of accounts you have.

![email](images/mxplan-starter-new-step3.png){.thumbnail}

#### Using your email addresses

Once you have created your email addresses, you can start using them straight away. You can do this using Outlook Web Access (OWA) webmail, or you can use any software you want.

##### **1. Using Outlook Web Access (OWA) webmail**

Go to the [Webmail login](https://www.ovh.co.uk/mail/) page, then enter the email address and password. Then click the `Login`{.action} button.

When you first log in to the webmail interface, you are prompted to set the interface language and your time zone. Your inbox will then appear. To find out how to use your email address via the OWA webmail interface, please refer to our [Outlook Web App user guide](https://docs.ovh.com/gb/en/emails/using-owa/).

![email](images/mxplan-starter-new-step4.png){.thumbnail}

##### **2. Using the software of your choice**

To use your email address with a third-party software, you will need to configure this email address on the device you want to use (PC, Mac, smartphone or tablet). To do this, you can use our configuration guides:

|Windows|Outlook|Apple|Android|
|---|---|---|---|
|[Windows 10](https://docs.ovh.com/gb/en/emails/mail-configuration-windows-10/)|[Outlook Windows](https://docs.ovh.com/gb/en/emails/configuration-outlook-2016/)|[MacOS Mail (latest version)](https://docs.ovh.com/gb/en/emails/guide-configuring-mail-on-macos/)|[Android (latest version)](https://docs.ovh.com/gb/en/emails/configuration-android/)|
|[Thunderbird](https://docs.ovh.com/fr/emails/configuration-email-configuration-pour-thunderbird/)|[Outlook Mac OS](https://docs.ovh.com/gb/en/emails/configuration-outlook-2016-mac/)|[Mail for iPhone or iPad](https://docs.ovh.com/gb/en/emails/email_hosting_iphone_ios_91_configuration/)|
|||[Thunderbird Mac OS](https://docs.ovh.com/fr/emails/guide-de-configuration-email-pour-thunderbird-mac/)|

If you just need the information required to configure your email address, the settings to use are listed below:

- **For IMAP configuration (recommended)**

|Server type|Server name|Port (with SSL)|Port (without SSL)|
|---|---|---|---|
|Incoming|ssl0.ovh.net|993|143|
|Outgoing|ssl0.ovh.net|465|587|

- **For POP configuration**

|Server type|Server name|Port (with SSL)|Port (without SSL)|
|---|---|---|---|
|Incoming|ssl0.ovh.net|995|110|
|Outgoing|ssl0.ovh.net|465|587|

> [!warning]
>
> If you have any problems configuring your email address on your device, we recommend using [our configuration guides](../) or getting in touch with the publishers of the application you are using, because you may need to make a change that is specific to the application.
>

#### Advanced features

##### **Security policy**

You may want to increase the security of access to your email addresses.

You can do this by setting the security policy for your MX Plan solution.

Please follow our guide on [Managing the security policy of an email service](https://docs.ovh.com/gb/en/microsoft-collaborative-solutions/manage-security-policy-password/).

##### **Redirections**

You may want to redirect your emails to another recipient, create an alias or systematically copy another email address.

To do this, you will need to create a redirection.

You can do this in two ways:

- creating a redirection via webmail, via the inbox rules. To do this, please follow our guide on [Inbox rules in OWA](https://docs.ovh.com/gb/en/microsoft-collaborative-solutions/creating-inbox-rules-in-owa/#example-1-redirecting-emails-to-another-address).

- creating a redirection from your [OVHcloud Control Panel](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.co.uk/&ovhSubsidiary=GB). For example, you can use this method to create an alias, i.e. redirect an email address that does not exist to an existing email address. To do this, please follow our guide on [Using email](https://docs.ovh.com/gb/en/emails/email-redirection-guide/#mx-plan-new-version_1) redirections.

##### **Voicemail**

You may go on holidays, or you may not have access to your email address for a certain period of time.

You can then create an automatic reply. Please follow our guide on [Setting up automatic replies in OWA](https://docs.ovh.com/gb/en/microsoft-collaborative-solutions/exchange_2016_how_to_set_up_automatic_replies_in_owa/).

##### **Delegations**

You may want to send an email from your personal email address, **instead of** or **from another** email address associated with your domain name.

To do this, you will need to configure the delegation for the email address concerned. Please follow our guide on [Delegating account rights](https://docs.ovh.com/gb/en/microsoft-collaborative-solutions/exchange_2013_how_to_grant_full_access_permissions_for_an_account/).

##### **Mailing lists**

You may want to send a regular newsletter to your contacts.

To do this, you can create a mailing list. Please follow our guide on [Managing and using mailing lists](https://docs.ovh.com/gb/en/emails/guide-dutilisation-mailing-list/).

##### **Bottom of page**

You may want to apply a global signature to all the email addresses for your domain name.

You can do this in the footer, which can be configured from your Control Panel. Please follow our guide on [Adding a footer to your emails](https://docs.ovh.com/gb/en/microsoft-collaborative-solutions/exchange_20132016_how_to_create_an_automatic_signature/).

### MX Plan legacy version <a name="oldmxplan"></a>

#### Accessing your solution management

If you are using the legacy version of the MX Plan solution, this is the display you should see. If not, please ensure you follow the right path [by referring to the information above](#instructions).

![email](images/mxplan-starter-legacy-step1.png){.thumbnail}

#### Adding an email account

To create an email address, go to the `Email accounts`{.action} tab. The table that appears will contain all of the email addresses you have created as part of your MX Plan solution. Then click the `Create Email Address`{.action} button.

![email](images/mxplan-starter-legacy-step2.png){.thumbnail}

In the pop-up window, enter the following information:

|Information|Description|  
|---|---|  
|User name|Enter the name for your email address (firstname.lastname, for example). The domain name concerned is already entered by default.|  
|Account description|Enter a short description that will distinguish this account from any other accounts added in the OVHcloud Control Panel.|  
|Account size|Select the size of account you want. This size refers to the space available to your account for storing messages.|  
|Password|Type in a password, and confirm it. For security reasons, we recommend not using the the same password twice, and choosing one that does not contain any personal information (e.g. first name, surname and date of birth). We also recommend changing your password regularly.|

Once you have completed the text fields, click `Next`{.action} and then check the information that appears in the summary. If it is all correct, click `Confirm`{.action} . Repeat this step as necessary according to the number of accounts you have.

![email](images/mxplan-starter-legacy-step3.png){.thumbnail}

#### Using your email addresses

Once you have created your email addresses, you can start using them straight away. There are two ways you can do this: using the RoundCube webmail interface, or using the software of your choice.

##### **1. Using RoundCube webmail**

Go to the [Webmail login](https://www.ovh.co.uk/mail/) page, then enter the email address and password. Then click the `Login`{.action} button.

Your inbox will appear. To find out how to use your email address via the RoundCube webmail interface, use our guide “[Use your email address via the RoundCube webmail interface ](https://docs.ovh.com/fr/emails/utilisation-roundcube/)”.

![email](images/mxplan-starter-legacy-step4.png){.thumbnail}

##### **2. Using the software of your choice**

To use your email address with a third-party software, you will need to configure this email address on the device you want to use (PC, Mac, smartphone or tablet). To do this, you can use our configuration guides:

|Windows|Outlook|Apple|Android|
|---|---|---|---|
|[Windows 10](https://docs.ovh.com/gb/en/emails/mail-configuration-windows-10/)|[Outlook Windows](https://docs.ovh.com/gb/en/emails/configuration-outlook-2016/)|[MacOS Mail (latest version)](https://docs.ovh.com/gb/en/emails/guide-configuring-mail-on-macos/)|[Android (latest version)](https://docs.ovh.com/gb/en/emails/configuration-android/)|
|[Thunderbird](https://docs.ovh.com/fr/emails/configuration-email-configuration-pour-thunderbird/)|[Outlook Mac OS](https://docs.ovh.com/gb/en/emails/configuration-outlook-2016-mac/)|[Mail for iPhone or iPad](https://docs.ovh.com/gb/en/emails/email_hosting_iphone_ios_91_configuration/)|
|||[Thunderbird Mac OS](https://docs.ovh.com/fr/emails/guide-de-configuration-email-pour-thunderbird-mac/)|

If you just need the information required to configure your email address, the settings to use are listed below:

- **For IMAP configuration (recommended)**

|Server type|Server name|Port (with SSL)|Port (without SSL)|
|---|---|---|---|
|Incoming|ssl0.ovh.net|993|143|
|Outgoing|ssl0.ovh.net|465|587|

- **For POP configuration**

|Server type|Server name|Port (with SSL)|Port (without SSL)|
|---|---|---|---|
|Incoming|ssl0.ovh.net|995|110|
|Outgoing|ssl0.ovh.net|465|587|

> [!warning]
>
> If you have any problems configuring your email address on your device, we recommend using [our configuration guides](../) or getting in touch with the publishers of the application you are using, because you may need to make a change that is specific to the application.

#### Advanced features

##### **Redirection**

You may want to redirect your emails to another recipient, create an alias or systematically copy another email address.

To do this, you will need to create a redirection. Please follow our guide on [Using email](https://docs.ovh.com/gb/en/emails/email-redirection-guide/#mx-plan-legacy-version) redirections.

##### **Voicemail**

You may go on holidays, or you will not have access to your email address for a certain period of time.

You can then use the automatic reply on your email address. Please follow our guide on [Creating an auto-reply for an email](https://docs.ovh.com/gb/en/emails/set-up-email-responder/) address.

##### **Delegations**

You may want to **delegate all the email service for a domain name to another OVHcloud account** , or **delegate one or more email accounts to another OVHcloud account**. For example, you can allow the holder of this other OVHcloud account to change the password for an email address.

Please follow our guide on [Delegating email management to another person](https://docs.ovh.com/fr/emails/deleguer-gestion-emails-autre-identifiant/).

##### **Mailing lists**

You may want to send a regular newsletter to your contacts.

To do this, you can create a mailing list. Please follow our guide on [Managing and using mailing lists](https://docs.ovh.com/gb/en/emails/guide-dutilisation-mailing-list/).

## Go further

The legacy MX Plan solutions are being migrated to the new MX Plan solutions. If you would like to migrate your solution as a priority, you can follow the instructions on [this page](https://www.ovh.co.uk/mxplan-migration/#accordion_6001-4).

If your needs change and you want additional features, you can also [migrate an MX Plan email address to an Email Pro or Exchange account](https://docs.ovh.com/gb/en/microsoft-collaborative-solutions/migration-email-address-to-exchange/).

Join our community of users on <https://community.ovh.com/en/>.
