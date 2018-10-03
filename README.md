# Azure AD B2C extension

The Azure AD B2C extension for VS Code lets you quickly navigate through Azure AD B2C [custom policy](https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-overview-custom). Create new elements, such as: technical profiles and claim definition. For more information, see [Get started with custom policies](https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-get-started-custom).

## Having an issue?
Please contact us at b2ctools@outlook.com

## Get started
To start working with your custom policy. Open you Visual Studio Code, and open your folder that containing the custom policy XML files. Or open the policy XML files directly from any folder.

![Custom policy navigator](media/openfolder.png)

## Azure AD B2C Custom policy Features
### Custom policy explorer
From **Custom policy explorer** click on the XML element type and select the element you want to open. Note: custom policy explorer shows elements from  selected file only.

![Custom policy navigator](media/explorer.png)

### Go to definition and find all references
To go any XML element definition. Clt-Click, click F12 or right-click and select **Go to definition** or **Peak definition**. Note: Go to definition navigates you to the source element in the selected file only.

To search for references in your **Open folder** XML files or any XML file you open with VS code, select **Find all references** or click Shift+F12.

![Go to definition and find all references](media/goto.png)

### Adding XML elements
You can add following elements to your policy. Note: make sure your cursor is located in the right place.
* B2C Add Identity provider technical profile (shift+ctrl+1)
* B2C Add REST API technical profile (shift+ctrl+2)
* B2C Add Claim Type (shift+ctrl+3)
* B2C Add Application Insights (debug mode) (shift+ctrl+4)

![Adding XML elements](media/commands.png)

### Help and more information
After you run the commends, B2C extension shows you information message with a link to relevant article.

![InformationMessage](media/moreinfo.png)

### XML Schema quick help

Move your mouse over any XML tag name, to see the description

![XML Schema quick help](media/hover.gif)

### Application Insights
Collect logs from Azure AD B2C and diagnose problems with your Azure AD B2C vscode extension. Read more [here](https://github.com/yoelhor/aad-b2c-vs-code-extension/blob/master/src/help/app-insights.md). The logs are organized by the **policy name**, **correlation Id** (the application insights presents the first digit of the correlation Id), and the **log timestamp**. This allows you to find the relevant log based on the local timestamp and see the user journey as executed by Azure AD B2C.

![Application Insights](media/ai.png)

### App Settings
Allows you to manage the values of your Azure AD B2C environments. When you execute the **B2C Policy build** command, the extension finds and replace the values of your settings with the ones configure in the policy file, and creates a directory that contains all of your policy files (after the replacement). In the following example, the extension replaces the keys with the value configure in the `appsettings.json` file: 
- {Settings:Tenant}
- {Settings:IdentityExperienceFrameworkAppId}
- {Settings:ProxyIdentityExperienceFrameworkAppId}
- {Settings:FacebookAppId}

![App Settings](media/app-settings.png)

The configuration `appsettings.json` file contains the values for each environment. You can add more settings, to accommodate your needs, such as the URL of a REST API end point, Google+ app Id, URL of content definitions, and so on. In the policy file, use the format of **Settings:** and the key name `{Settings:Key}`.

```JSON
{
  "Environments": [
  {
    "Name": "Test",
    "Production": false,
    "Tenant": "your-tenant.onmicrosoft.com",
    "IdentityExperienceFrameworkAppId": "Your AD app Id",
    "ProxyIdentityExperienceFrameworkAppId": "Your AD Proxy app Id",
    "FacebookAppId": "0"
  },
  {
    "Name": "QA",
    "Production": false,
    "Tenant": "your-tenant.onmicrosoft.com",
    "IdentityExperienceFrameworkAppId": "Your AD app Id",
    "ProxyIdentityExperienceFrameworkAppId": "Your AD Proxy app Id",
    "FacebookAppId": "0"
  },
  {
    "Name": "Production",
    "Production": true,
    "Tenant": "your-tenant.onmicrosoft.com",
    "IdentityExperienceFrameworkAppId": "Your AD app Id",
    "ProxyIdentityExperienceFrameworkAppId": "Your AD Proxy app Id",
    "FacebookAppId": "0"
  }]
}
```

After the command is completed, you will find the exported policies under the **Environment** folder.


## Disclaimer
The extension is developed and managed by the open-source community in [GitHub](https://github.com/yoelhor/aad-b2c-tools.git). The extension is not part of Azure AD B2C product and it's not supported under any Microsoft standard support program or service. The extension is provided AS IS without warranty of any kind. For any issue, visit the [GitHub](https://github.com/yoelhor/aad-b2c-tools.git) repository.
