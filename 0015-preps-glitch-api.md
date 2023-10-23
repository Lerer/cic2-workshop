## 1.5 Update Glitch APP with API details

#### 1. Update the API configuration 
In Glitch, go to the source code page of your Glitch API application and in the left menu panel under **Files**, open `src` folder and click `auth_config.json`.


#### 2. Modify auth_config.json 
- Set the `audience` value to `api://dashboardapi/`

The end result should look like this:

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/auth-config-api.png?raw=true)



#### 3. Done! 
There is nothing else to see at this point, but these steps were necessary to start with the third challenge.

In this challenge, you set up a custom API within your Okta CIC tenant to enable the creation of OAuth access tokens used for accessing secured API endpoints
