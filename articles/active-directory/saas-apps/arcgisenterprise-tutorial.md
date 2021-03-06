---
title: 'Tutorial: Azure Active Directory integration with ArcGIS Enterprise | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and ArcGIS Enterprise.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 12/28/2018
ms.author: jeedes
---
# Tutorial: Azure Active Directory integration with ArcGIS Enterprise

In this tutorial, you learn how to integrate ArcGIS Enterprise with Azure Active Directory (Azure AD).
Integrating ArcGIS Enterprise with Azure AD provides you with the following benefits:

* You can control in Azure AD who has access to ArcGIS Enterprise.
* You can enable your users to be automatically signed-in to ArcGIS Enterprise (Single Sign-On) with their Azure AD accounts.
* You can manage your accounts in one central location - the Azure portal.

If you want to know more details about SaaS app integration with Azure AD, see [What is application access and single sign-on with Azure Active Directory](../manage-apps/what-is-single-sign-on.md).
If you don't have an Azure subscription, [create a free account](https://azure.microsoft.com/free/) before you begin.

## Prerequisites

To configure Azure AD integration with ArcGIS Enterprise, you need the following items:

* An Azure AD subscription. If you don't have an Azure AD environment, you can get one-month trial [here](https://azure.microsoft.com/pricing/free-trial/)
* ArcGIS Enterprise single sign-on enabled subscription

> [!NOTE]
> This integration is also available to use from Azure AD US Government Cloud environment. You can find this application in the Azure AD US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this tutorial, you configure and test Azure AD single sign-on in a test environment.

* ArcGIS Enterprise supports **SP and IDP** initiated SSO
* ArcGIS Enterprise supports **Just In Time** user provisioning


## Adding ArcGIS Enterprise from the gallery

To configure the integration of ArcGIS Enterprise into Azure AD, you need to add ArcGIS Enterprise from the gallery to your list of managed SaaS apps.

**To add ArcGIS Enterprise from the gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, on the left navigation panel, click **Azure Active Directory** icon.

	![The Azure Active Directory button](common/select-azuread.png)

2. Navigate to **Enterprise Applications** and then select the **All Applications** option.

	![The Enterprise applications blade](common/enterprise-applications.png)

3. To add new application, click **New application** button on the top of dialog.

	![The New application button](common/add-new-app.png)

4. In the search box, type **ArcGIS Enterprise**, select **ArcGIS Enterprise** from result panel then click **Add** button to add the application.

	 ![ArcGIS Enterprise in the results list](common/search-new-app.png)

## Configure and test Azure AD single sign-on

In this section, you configure and test Azure AD single sign-on with [Application name] based on a test user called **Britta Simon**.
For single sign-on to work, a link relationship between an Azure AD user and the related user in [Application name] needs to be established.

To configure and test Azure AD single sign-on with [Application name], you need to complete the following building blocks:

1. **[Configure Azure AD Single Sign-On](#configure-azure-ad-single-sign-on)** - to enable your users to use this feature.
2. **[Configure ArcGIS Enterprise Single Sign-On](#configure-arcgis-enterprise-single-sign-on)** - to configure the Single Sign-On settings on application side.
3. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with Britta Simon.
4. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable Britta Simon to use Azure AD single sign-on.
5. **[Create ArcGIS Enterprise test user](#create-arcgis-enterprise-test-user)** - to have a counterpart of Britta Simon in ArcGIS Enterprise that is linked to the Azure AD representation of user.
6. **[Test single sign-on](#test-single-sign-on)** - to verify whether the configuration works.

### Configure Azure AD single sign-on

In this section, you enable Azure AD single sign-on in the Azure portal.

To configure Azure AD single sign-on with [Application name], perform the following steps:

1. In the [Azure portal](https://portal.azure.com/), on the **ArcGIS Enterprise** application integration page, select **Single sign-on**.

    ![Configure single sign-on link](common/select-sso.png)

2. On the **Select a Single sign-on method** dialog, select **SAML/WS-Fed** mode to enable single sign-on.

    ![Single sign-on select mode](common/select-saml-option.png)

3. On the **Set up Single Sign-On with SAML** page, click **Edit** icon to open **Basic SAML Configuration** dialog.

	![Edit Basic SAML Configuration](common/edit-urls.png)

4. On the **Basic SAML Configuration** section, perform the following steps, if you wish to configure the application in **IDP** Initiated mode:

    ![Screenshot shows the Basic SAML Configuration, where you can enter Identifier, Reply U R L, and select Save.](common/idp-intiated.png)

    a. In the **Identifier** text box, type a URL using the following pattern:
    `<EXTERNAL_DNS_NAME>.portal`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<EXTERNAL_DNS_NAME>/portal/sharing/rest/oauth2/saml/signin2`

    c. Click **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    ![Screenshot shows Set additional U R Ls where you can enter a Sign on U R L.](common/metadata-upload-additional-signon.png)

	In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<EXTERNAL_DNS_NAME>/portal/sharing/rest/oauth2/saml/signin`

    > [!NOTE]
	> These values are not real. Update these values with the actual Identifier, Reply URL and Sign-on URL. Contact [ArcGIS Enterprise Client support team](mailto:support@esri.com) to get these values. You will get the Identifier value from **Set Identity Provider section**, which is explained later in this tutorial.

5. On the **Set up Single Sign-On with SAML** page, In the **SAML Signing Certificate** section, click copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

### Configure ArcGIS Enterprise Single Sign-On

1. To automate the configuration within ArcGIS Enterprise, you need to install **My Apps Secure Sign-in browser extension** by clicking **Install the extension**.

	![My apps extension](common/install-myappssecure-extension.png)

1. After adding extension to the browser, click on **Set up ArcGIS Enterprise** will direct you to the ArcGIS Enterprise application. From there, provide the admin credentials to sign into ArcGIS Enterprise. The browser extension will automatically configure the application for you and automate steps 3-7.

	![Setup configuration](common/setup-sso.png)

1. If you want to setup ArcGIS Enterprise manually, log in to your ArcGIS Enterprise company site as an administrator.


1. Select **Organization >EDIT SETTINGS**.

	![Screenshot shows the ArcGIS Enterprise Organization tab with Edit settings called out.](./media/arcgisenterprise-tutorial/configure1.png)

1. Select **Security** tab.

	![Screenshot shows the Security tab selected.](./media/arcgisenterprise-tutorial/configure2.png)

1. Scroll down to the **Enterprise Logins via SAML** section and select **SET ENTERPRISE LOGIN**.

	![Screenshot shows Enterprise Logins via SAML where you can select Set Enterprise Login.](./media/arcgisenterprise-tutorial/configure3.png)

1. On the **Set Identity Provider** section, perform the following steps:

	![Screenshot shows Set Identity Provider where you perform the steps described here.](./media/arcgisenterprise-tutorial/configure4.png)

	a. Please provide a name like **Azure Active Directory Test** in the **Name** textbox.

	b. In the **URL** textbox, paste the **App Federation Metadata Url** value which you have copied from the Azure portal.

	c. Click **Show advanced settings** and copy the **Entity ID** value and paste it into the **Identifier** textbox in the **ArcGIS Enterprise Domain and URLs** section in Azure portal.
	
	![Screenshot shows where to get the Entity I D and update identify provider.](./media/arcgisenterprise-tutorial/configure5.png)

	d. Click **UPDATE IDENTITY PROVIDER**.

### Create an Azure AD test user 

The objective of this section is to create a test user in the Azure portal called Britta Simon.

1. In the Azure portal, in the left pane, select **Azure Active Directory**, select **Users**, and then select **All users**.

    ![The "Users and groups" and "All users" links](common/users.png)

2. Select **New user** at the top of the screen.

    ![New user Button](common/new-user.png)

3. In the User properties, perform the following steps.

    ![The User dialog box](common/user-properties.png)

    a. In the **Name** field enter **BrittaSimon**.
  
    b. In the **User name** field type **brittasimon\@yourcompanydomain.extension**  
    For example, BrittaSimon@contoso.com

    c. Select **Show password** check box, and then write down the value that's displayed in the Password box.

    d. Click **Create**.

### Assign the Azure AD test user

In this section, you enable Britta Simon to use Azure single sign-on by granting access to ArcGIS Enterprise.

1. In the Azure portal, select **Enterprise Applications**, select **All applications**, then select **ArcGIS Enterprise**.

	![Enterprise applications blade](common/enterprise-applications.png)

2. In the applications list, type and select **ArcGIS Enterprise**.

	![The ArcGIS Enterprise link in the Applications list](common/all-applications.png)

3. In the menu on the left, select **Users and groups**.

    ![The "Users and groups" link](common/users-groups-blade.png)

4. Click the **Add user** button, then select **Users and groups** in the **Add Assignment** dialog.

    ![The Add Assignment pane](common/add-assign-user.png)

5. In the **Users and groups** dialog select **Britta Simon** in the Users list, then click the **Select** button at the bottom of the screen.

6. If you are expecting any role value in the SAML assertion then in the **Select Role** dialog select the appropriate role for the user from the list, then click the **Select** button at the bottom of the screen.

7. In the **Add Assignment** dialog click the **Assign** button.

### Create ArcGIS Enterprise test user

In this section, a user called Britta Simon is created in ArcGIS Enterprise. ArcGIS Enterprise supports just-in-time user provisioning, which is enabled by default. There is no action item for you in this section. If a user doesn't already exist in ArcGIS Enterprise, a new one is created after authentication.

> [!Note]
> If you need to create a user manually, contact [ArcGIS Enterprise support team](mailto:support@esri.com).

### Test single sign-on 

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the ArcGIS Enterprise tile in the Access Panel, you should be automatically signed in to the ArcGIS Enterprise for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](../user-help/my-apps-portal-end-user-access.md).

## Additional Resources

- [List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory](./tutorial-list.md)

- [What is application access and single sign-on with Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

- [What is Conditional Access in Azure Active Directory?](../conditional-access/overview.md)