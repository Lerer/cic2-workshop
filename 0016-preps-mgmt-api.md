## 1.6 Create Management API client

In this section, you will setup your app to speak to the Auth0 Management API.

> _The Auth0 Management API is a collection of endpoints to complete administrative tasks programmatically and should be used by back-end servers or trusted parties._

**Why do we need this?**
In the app you are building, we will offer the ability for users to manage their team members. We will control this ability with Role Based Access Control. We'll come to that in a challenge.


**How does it work?**
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/001/diagram.png?raw=true)



### Step 1: Create a Management API client
1. Go to `Applications` on the Dashboard and click `Create Application`
2. Use a relevant name. For example: `Management API client`
3. Select `Machine to Machine Applciations` as the application type and click `Create`
4. Select `Auth0 Management API` from the dropdown
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/001/mgmt-api-select.png?raw=true)


5. Select `All` permissions and click `Authorize`.    
   **Important:exclamation:**: In a real project, you should only enable necessary permissions to the client. For today, we will keep it simple.

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/auth-all.png?raw=true)


6. Go to `Settings` tab and find the `Client ID` and `Client Secret`.      
   :point_right: We will now copy these over to the Glitch App.⁠

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/mgmt-api-client-details.png?raw=true)


### Step 2: Update Glitch App's environment variables
1. Go to your Glitch app, under files, select `.env` file
2. Copy the `Client ID` value from the previous step to the `AUTH0_API_ID` field
3. Copy the `Client Secret` value from the previous step to the `AUTH0_API_CLIENT_SECRET` field.

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/glitch-env.png?raw=true)


### Good Job!
That's it! Now your Glitch App can interact with the Auth0 Management API.
⁠This uses the **Node Auth0 SDK** which makes it easy to interact with the Managment API.

⁠You can check it out here: https://github.com/auth0/node-auth0
