Acquaa uses Auth0 as the federated identity management system for authentication as well authorisation to an extent.

## Authentication Flow
![Authentication Flow](https://github.com/acquaa-org/acquaa/blob/gh-pages/images/authentication.png)

## Steps for creating an app in Azure AD
1. Create an app in Azure AD. We will require one for each environment - ie UAT, Prod
2. Configure the redirect URI (Get it from Acquaa engineering team)
3. For "Supported account types", use 'Single Tenant'
4. Create teh app and generate a client secret for use by Auth0 (Refer to https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-credentials).
5. Add the following permissions for the app: Users > User.Read (This is for Auth0 to get user profile details such as name, email)

Note down the following information as they are needed for configuring Auth0
1. Client ID (App ID)
2. Client secret
3. Microsoft Azure AD Domain

The above information is needed in Auth0 for configuring authentication via Azure AD.

## References
1. https://auth0.com/docs/authenticate/identity-providers/enterprise-identity-providers/azure-active-directory/v2#register-your-app-with-azure-ad
2. https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app
3. https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis
4. https://auth0.com/blog/what-is-and-how-does-single-sign-on-work/