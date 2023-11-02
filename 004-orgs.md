
# Introduction to Organizations 

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/orgs-logo.jpeg?raw=true)


- The Auth0 Organizations feature best supports business-to-business (B2B) implementations that have applications that end-users access.      

- You can create organizations using either the Auth0 Dashboard or the Management API.    

- Organisations allow you easily activate and customize SSO and branding per-organization    

  - Define how your customer or partners can quickly access applications for a smooth login experience.    

  - Rapidly onboard enterprise customers     

  - Deliver SSO to your customers in a fraction of the time     

  - Federate your customers’ end-users seamlessly with any directory     

  - Brand login and registration flows so your customers feel at home      




- Define roles for what users can do in your applications and assign them to users within your customer organizations.    

  - Add users directly into your organization via email invite or using the Auth0 API      

  - Reduce overheads associated with building access control       



# Setting up Organizations

#### Configure an Application to Use Organisations
- Click **Applications** --> **Application** from the left side menu
- Select the SPA app that you created earlier
- Click into the `Organizations` tab

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/orgs-tab.png?raw=true)



- For **Types of Users** select **Select Business Users**
- For **Login Flow** select **Prompt for Credentials**
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/004/org-b2b-setup.png?raw=true)


- Click **`Save Changes`**

>This will create a login flow that looks something like this


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/orgs-login-flow.png?raw=true)




# Create an Organization and add an Admin user in the Dashboard

**Step 1:** Navigate to [Organizations](https://manage.auth0.com/#/organizations)      
      
**Step 2:** Click create an Organization

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/create-org-start.png?raw=true)


**Step 3:** Enter a name for your Organization and hit Add Organization


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/add-org-button.png?raw=true)


**Step 4:** In the Branding section below, **add a logo** for your organization, **set the colours** and at the bottom **Click Save Changes**


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/org-basic-brandings.png?raw=true)


> **Congratulations you’ve created your first Organization! Now let’s add some users into your Organisation....** 



**Step 5:** Click into the Members Tab
- Select **Add Members**

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/org-add-members-button.png?raw=true)


- Search for an existing user you created in the previous sections and click on them
- Click Add Member

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/add-member.png?raw=true)



**Step 6:** Now that the user is added, let’s assign them the admin role
- Go back to the member screen, click the **`…`** on the far right of the user

- From the dropdown menu select **`Assign Roles`**


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/assign-roles.png?raw=true)


- Select the **`Admin`** role we created earlier, and press Assign Role


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/assign-admin-role.png?raw=true)


**Step 7:** Add a Connection to your Organization
- Click `Connections` Tab under your Organisation
- Click **Enable Connections**


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/enable-conn-button.png?raw=true)


- Select the **`Username-Password-Authentication`** database
- Click Enable Connection


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/confirm-conn-button.png?raw=true)


- Leave Auto-Membership disabled (default)

### Good job!
⁠Now you have an Organization with an Admin user. Let's got to next section.


# Manage users via the app as an Admin

In this section you will manage the users who are "members" of your organization

   
**Step 1:** Go to your Glitch application and login as an admin user into an Organization.      

⁠Here you’ll be able to do a number of things as an admin.

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/web-login.png?raw=true)



As you are an admin, you will be able to see a link on the sidebar **`Users & Roles`** which will take you to a user management page.


![](https://github.com/lerer/cic2-workshop/blob/main/images/004/user-mgmt-link.png?raw=true)


**Step 2:** Click on **`Users & Roles`** on the sidebar. You will see the members page showing you all the members in your organisation
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/004/web-org-memebers-list.png?raw=true)



**Step 3:** Let's invite a new user to the organization

  
- Click on **`Invite members`** button to invite a new user to the organization.
Type an email address and select a role using the dropdown. Notice that you will see the same roles you created in the Auth0 management dashboard earlier.
⁠

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/invite-member.png?raw=true)



**Step 4:** Accept the invitation

- Check the email inbox of the user you invited
⁠

![](https://github.com/lerer/cic2-workshop/blob/main/images/004/invite-email.png?raw=true)



- Accept the invitation by clicking on the email (Open in an incognito or Private window)
- You will be asked to setup a password for the user.
- Now notice that depending on the role you selected (Admin or Member), you will see options in teh dashboard relevant to the role.

### Good job!
Your app now offers ability for your users to manage their team members.



