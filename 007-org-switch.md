# Organizations Switcher

## 7.0 Intro to Organization Switcher


### Enabling collaboration across organizations

In this challenge we will address a scenario when a user is working as a collaborator in more than one organization, such as subcontractors. A simple implementation would be to register the same user twice (one to each organization) and have him/her/it logout and login again when switching between organizations. 


However, the above implementation will not provide the best user experience as it will create user fatigue login and logout with the fact they will need to remember 2 passwords (or more). As well as a SaaS provider, you will own and manage a user profile per each organization the same human is a member of.


An alternative implementation would be to manage a single user identity and have it associated to each allowed organization with its own contextual role.


We will now guide you how to implement the collaboration model as mentioned above.


Note - additional supporting documentation to the following Challenge can be found here: https://auth0.com/docs/manage-users/organizations/login-flows-for-organizations


Let's Start!


## 7.1 Invite a user to two different organizations

#### 1. Create additional Organization
For the purpose of this challenge please follow the steps in **Challenge 4** to add a second organization.

**Important**
- Add additional user to act as the second organization admin

- Make sure you **add the same Database connection** as you used for the first organization


#### 2. Invite an existing User
Login to your Glitch Application using the Admin user credentials you created for the second organization.


Locate and navigate to the Invitations section


![](https://github.com/lerer/cic2-workshop/blob/main/images/007/users-n-roles.png?raw=true)   



Invite a user to your organization by clicking on the “Invite Members” button which will open the following window


![](https://github.com/lerer/cic2-workshop/blob/main/images/007/invite-user.png?raw=true)   



Add an email address of a user you used for the first Organization as a member

Once you done, click the **`Submit`** button




## 7.2 Accept the user membership invitation

### You can use one of the following options to accept the user invitation:
1. Login to your email and accept the invitation from your email


2. You can navigate to the CIC admin Dashboard => Organizations => `<YOUR ORGANIZATION>` => Invitations tab.
   

The same invitation link which would be normally send on the invitation email is also accessible by clicking on the 3 dots button  right to the user row in the invitations list.


![](https://github.com/lerer/cic2-workshop/blob/main/images/007/three-dots.png?raw=true)   


From there you can see the invitation link


![](https://github.com/lerer/cic2-workshop/blob/main/images/007/invite-url.png?raw=true)   


Copy the invitation link and paste into a new Incognito Browser session


> **Note** - inspect the URL and you can see the “**organization_name**” parameter embedded 



If all went well, you will now redirected to the login screen 
- Create a password if the user is not already set up

- Otherwise, switch from signup to login and authenticate the user

----

- If the Organization you worked on is Your first Organization:
  - repeat the steps you done for creating the organization
  - **Important**: Make sure you use the **same user**, **application** and **connection** for the invitation as you did for the first organization you created

- Otherwise, if you just created your second Organization - Proceed to the next (and final) section


## 7.3 Test switching between organizations

The last part of the challange, is testing our setup - can we login once and switch Organization as a function within our application?


Logout from your existing session if needed


#### 1. Login to the application	

Login to your application using the user account you invited in the previous sections.


> **Note**:exclamation: - make sure you are using the user account which was invited to both organizations.

Once you enter your credentials, you will be prompt to select the Organization you want to log in

For example:


![](https://github.com/lerer/cic2-workshop/blob/main/images/007/select-org.png?raw=true)   



> **Note** - your organization list may differ from the above based on their names
    
Select one of the organizations to login.


#### 2. Note your current organization
Click on the profile icon (top right) to open a menu, and select the **`ID Token`** option


![](https://github.com/lerer/cic2-workshop/blob/main/images/007/id-token-link.png?raw=true)   


A new tab will open which will decode your ID Token.


Note your organization ID in the decode payload section.
```
"org_id": "org_xxxxxxxxxxxxxxx"
```

#### 3. Switch Organization
Now that you have noted your **org_id**, let's switch organization from the application UI.


At the top left of your Saas Application, expand the Organizations list


![](https://github.com/lerer/cic2-workshop/blob/main/images/007/inline-select-org.png?raw=true)   


Click on the other organization your user is member of (the one you did not select as part of the above step 1)


The application UI refreshed, however, let's verify the organization context we logged on as...


Repeat the above Step 2 and check again your **org_id** in the ID Token.


You'll see that although, we have the same user (email), we now (should) have a different **org_id** in our ID Token.

#### 4. Final
In the background the application called the authentication route with an embeded organization id in order to replace our ID (and access) token with a new set to match our requested organization. Since the user is already a memebr of both organization, the switch was smooth as if it was silently authenticated.


If you would of tried the same with a user which is not invited to the second organization, you would be faced with the login screen to provide user credentials which is a member of that organization. 
 
