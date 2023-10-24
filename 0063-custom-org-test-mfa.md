## 6.3 Test your MFA Policy


For this section we simply need to pick the organization we want to enable MFA as a policy.   


In a commercial SaaS application we would probably want to add a setting option presented and serviced from the Application admin console. However, since it is not a UI challenge, we are going to add the setting manually.   



#### 1. Select Organizations from the left navigation menu


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/org-menu-item.png?raw=true)   


#### 2. Find the Organization metadata 
After selecting the specific organization for MFA, scroll down to section where is says: Metadata


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/org-metadata.png?raw=true)   


Once there, click on it to expand to add your metadata


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/add-new-org-metadata.png?raw=true)   



#### 3. Update organization metadata
Now we will add the following setting to the organization metadata    


Key | Value 
--- | --- 
“MFA_Enabled” | “true” 

![](https://github.com/lerer/cic2-workshop/blob/main/images/006/new-metadata-item.png?raw=true)   


Once you fill in the key and value, click on the


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/add-button.png?raw=true)   


the metadata setting will update automatically.


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/new-added-metadata.png?raw=true)   



#### 4. Test login


At this stage go back to the application and try to login using account credentials associated with the Organization you just update its metadata


If all went well, you will be presented with MFA challange when you try to login


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/mfa-qr-code.png?raw=true)   


#### 5. Disable MFA
In order to make it easy for the next Challange, you may want to remove the Organization metadata to disable the MFA
