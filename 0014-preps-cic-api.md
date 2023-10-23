## 1.4 Set up the CIC API

#### 1. Open the Okta CIC Management Dashboard 
Go to: manage.auth0.com.


#### 2. Click on APIs 
In the left menu panel, expand the Applications option and click APIs. 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/api-menu.png?raw=true)


#### 3. Click on Create API 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/create-api-button.png?raw=true)


#### 4. Create an API 
- Set the Name value to: `Dashboard API`
- Set the Identifier value to: `api://dashboardapi/`
- **Click on Create.** 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/create-api.png?raw=true)


#### 5. Let's create some permissions
Go to `Permissions` tab and create these permissions:

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/permissions-tab.png?raw=true)


⁠Use the permission names given below and add any relevant description.

- invite:users
- setup:sso
- view:members
- view:stats
- read:connections


![](https://github.com/lerer/cic2-workshop/blob/main/images/001/add-permissions.png?raw=true)


### 6. Congratulations, you’ve completed task 1.4 :) 
   
A custom API has now been setup in your Okta CIC tenant.

