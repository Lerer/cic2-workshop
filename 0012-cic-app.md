## 1.2 CIC App


In this task, we will utilize the Okta CIC Management Dashboard to set up the Glitch UI application within Okta CIC.

#### 1. Open your CIC management dashboard 

Your tenant’s management url should be similar with: `https://manage.auth0.com/dashboard/<REGION>/<TENANT NAME>`, but you can access even more convenient via <a href="https://manage.auth0.com" target="_blank">https://manage.auth0.com</a>.


#### 2. Expand the Applications Menu 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/expand-app-menu.png?raw=true")


#### ⁠3. Create an App 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/create-app.png?raw=true")



#### 4. Name it and classify it 
Name your app as `Dashboard` and select as application type: `Single Page Web Application`. 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/app-class-selection.png?raw=true)



#### ⁠5. Click on Create 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/create-button.png?raw=true)





#### 6. Click the settings tab 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/settings-tab.png?raw=true)




#### ⁠7. Update the allowed URLs 

❗❗ :bangbang: IMPORTANT These values must be populated:

**1. Application Login URI**
**2. Allowed Callback URLs**
**3. Allowed Logout URLs**
**4. Allowed Web Origins**

Use the URL of your Glitch application.

For Application Login URI, add `https://<your Glitch app domain>/api/login`. See the example in the screenshot below.

For callback, logout and web origins, you can also use `https://*.glitch.me` for this lab, though we would not recommend that for your production application!


:warning: Whilst it is possible to use wildcards as in the image bellow, please note that it is not a good practice as the CIC application could be triggered by any app under the Glitch domain.

```
⚠️ :warning: Whilst it is possible to use wildcards as in the image bellow, please note that it is not a good practice as the CIC application could be triggered by any app under the Glitch domain.
```

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/app-url-settings.png?raw=true)


⁠#### 8. Find and copy the app details 

We will need to update the Glitch app with the domain and the client ID generated by CIC.


![](https://github.com/lerer/cic2-workshop/blob/main/images/001/app-details.png?raw=true)


**⁠Note that the dashboard has a handy copy icon.**

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/copy-button.png?raw=true)



#### 9. Save Changes 

Scroll all the way to the bottom and click on “Save Changes”. 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/save-changes.png?raw=true)



#### 10.  CIC now knows your app! 

This task generated a CIC application, you now have a:
- Client ID
- CIC Domain to use in your Glitch App. We will use those in the next step to bring an actual login into our application.


