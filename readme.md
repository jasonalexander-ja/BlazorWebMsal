# Example of MSAL in .NET 8 Blazor Web

This is an example app of using MSAL in a .NET 8 Blazor Web. 

As of time of writing, MSAL doesn't appear to be supported/documented for Blazor Web, however in this app we were able to demonstrate basic authentication of an app, the next steps would be to look at calling MS Graph. 

## To run 

We just need to register a web app in Azure AD using the allowed redirect user path of `https://localhost:7064`. 

- Go to [portal.azure.com](portal.azure.com). 
- Navigate to Azure Entra ID (formerly Azure AD). 
- In the `App registrations` tab, click `New registration`
- Give it a name, and select `Accounts in this organizational directory only (Default Directory only - Single tenant)`
- In redirect URI, set platform to `Web`, and the redirect URI to `https://localhost:7064`. 
- Click `Register`
- Copy the `Tenant Id` and `Client Id` into the relevant fields in `appsettings.json`

### Set the client secret 

- In the app registration page, go to `Certificates and secrets`
- In the `Client secrets` tab, click `New client secret`
- Name the secret, and copy down the value
- In the project CLI, run `dotnet user-secrets set "AzureAd:ClientSecret" "[your client secret]"`

Run with either `F5` in Visual Studio/Rider or `dotnet run` in the CLI. 
