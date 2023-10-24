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
