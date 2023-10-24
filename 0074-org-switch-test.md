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
 
