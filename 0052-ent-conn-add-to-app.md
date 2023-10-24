## 5.2 Setting up the Enterprise Connection for your Application

Let's setup the Okta SSO/federation for your app for the organization now.      
⁠
⁠In a real project, you can offer the ability for your users to setup the federation/SSO via your own app - in this case the Dashboard app. You can build the UI that collects the deatils required for the SSO setup and call the Auth0 Management API with the details to create the "Enterprise connection" and enable it for that particular organization.
⁠
⁠To keep it simple, today we will be setting up the connection directly on the Auth0 management dashboard.


1. Navigate to the management dashboard


2. Click Authentication on the left side menu, then click "Enterprise.
⁠From here you’ll be able to select the type of Connection like Okta or Azure AD, or just a generic SAML/OpenID Connect connection


3. Select "OpenID Connect" and click "Create Connection"


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/cic-new-ent-conn.png?raw=true)



4. Enter a connection name (this can be anything) and copy the Issuer URL and ClientID from the organisation you just created. Click on "Create" to complete the setup.

![](https://github.com/lerer/cic2-workshop/blob/main/images/005/cic-new-conn-details.png?raw=true)




5. To make sure users are actually redirected to your new organization, 
   1. Click on "Login Experience" in your newly created connection.

   2. Add the domain of your newly created user into the "Identity Provider Domains" (e.g. example.com if your user was called test@example.com) and click on "Save" on the bottom of the page.

![](https://github.com/lerer/cic2-workshop/blob/main/images/005/login-exp.png?raw=true)


6. Enable "Identifier first" under Authentication profile. On the sidebar, select "Authentication" and select "Authentication profile". Then on that page, select "Identifier First" and click "Save"


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/auth-profile-save.png?raw=true)



### Good job!
We will enable the connection for our organization in the next section.
