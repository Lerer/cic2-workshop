# Enteprise Connections

## 5.0 Intro to Setting up Federated Logins (Enteprise Connections) for your business customers


- Auth0 provides Enterprise connections to authenticate users in an external, federated identity provider (IdP) such as Okta, Azure AD, Google Workspace, PingFederate, and more.



- Auth0 supports a variety of open standards on top of this including OIDC, SAML as well AD/LDAP connectors



-  These can be created directly in the Auth0 Admin Dashboard or via Management API for programmatic or self-service approaches for your customers.



![](https://github.com/lerer/cic2-workshop/blob/main/images/005/ent-conn-logo.png?raw=true)


## 5.1 Create an Okta tenant for Federation

To simulate the setup of a federated connection, we've created an Okta Tennt tool so we can setup federation for your organisation, this will simulate an Enteprise Connection with a customer using Okta as their IDP but your customers could easily have a Azure AD, Google Workspace etc as their IDP.


**Step 1:** Click the link to the workshop creator tool
- https://okta-cic-workshop-org-creator.herokuapp.com/
- This tool will help us generate an Okta tenant to connect for federation

**Step 2:** Enter in the Auth0 Tenant Name Box 
- Click **Applications** > **Applications** in your Auth0 Tenant
- Select the SPA application you created earlier
- Copy your domain

![](https://github.com/lerer/cic2-workshop/blob/main/images/005/tenant-name.png?raw=true)



**Step 3:** The Organisation Name needs to be lowercase and unique across all workshop attendees. **This is not the Auth0 Organization name you created**. In this context the **`organization name`** means a name for an Okta Workforce Identity Cloud Org to be created.    


⁠⁠So if the tool says, the organization already exists, just come up with a more unique one.


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/conn-create-setup.png?raw=true)



**Step 4:** Save the information that’s provided to you somewhere safe as we’ll need it in the next step


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/your-new-conn.png?raw=true)



###Good job!
Let's go to the next section.

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


## 5.3 Enabling the connection for your Organization

Let’s add the connection you created to a new organisation


**Step 1:** Click Organisations from the left side menu, then select the Organization you created in section "5.1 Create an Okta tenant for Federation"


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/select-org.png?raw=true)   


**Step 2:** Once Created, Click the Connections section
- Click Enable Connections
- Select the Okta Connection and click Enable Connection


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/select-conn.png?raw=true)   


**Step 3:** Here you’ll have a choice to enable auto-membership, meaning you don’t need to invite users who are already apart of the connection, enable it and hit save


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/save-enabled-conn.png?raw=true)   


## 5.4 Test login via the Okta SSO

Let's test out the login!


**⁠Step 1:** If you are already logged in, logout first.   

**Step 2:** On the sidebar click on the "Organizations" dropdown and click on the Organization that you set up in the first section.   


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/web-select-org.png?raw=true)   


**Step 3:** Click "Continue with Okta" button     


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/switch-login-to-ent-conn.png?raw=true)   


**Step 4:** Enter the credentials you were given from the Organization Creator earlier and hit sign-in     


![](https://github.com/lerer/cic2-workshop/blob/main/images/005/login-with-ent-conn.png?raw=true)   


You should now be signed in to the organisation and redirected to your app.  


### Good job!
Now you have enabled SSO for an organization using their identity provider.

