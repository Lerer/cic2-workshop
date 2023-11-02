
# Intro to flexible security

### Actions
Actions are one of the cornerstones to Okta CIC’s overall extensibility. With Actions, you can add essential custom logic to your login and identity flows specific to your needs. Actions also allow you to connect external integrations that enhance your overall extensibility experience.   

In this challenge you will also see how easy it is to strengthen the overall security of your application by adding multi-factor authentication.


### Actions for Organization Security
Now that we’ve set up our organizations and authentication, we will increase our organization authentication security.   

In this challenge you will add MFA as part of the authentication flow. However, since we are emulating a SaaS provider, we can assume, not all of our Business customers will want to have MFA as always-on. Hence, we will condition the MFA as an option for each Organization   

For the purpose of the Challenge we will need to follow these steps   

1. Enable MFA option for our tenant - but not as “always-on”
2. Set up an Action which will act as the condition to redirect to MFA challeng
3. Enable an organization for MFA

Let’s get started!


# Enable MFA factors

### Let’s enable TOTP for MFA 

1. In Okta CIC, click on **Security** -> **Multi-factor Auth** 


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/mfa-menu.png?raw=true)   


2. Click on the toggle next to “**One-time Password**” to enable it 


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/totp-toggle.png?raw=true)   



#### Let’s make MFA as <u>NOT</u> mandatory 


3. Set **“Never”** as MFA policy 


In order to make sure we selectively trigger MFA when we want to, in the second section (`Define policies`), set the policy to **“Never”**.


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/never-as-mfa-policy.png?raw=true)   



> **Note**:exclamation: - at the bottom it may mentioned “Go to Rules” to modify MFA behavior. Rules are now deprecated and we will use Actions to perform the conditioned MFA. See here for more details


4. Click on **Save**
5. Done! 


You have updated the MFA Policy. 


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/mfa-policy-updated.png?raw=true)   



Learn more about the following topics mentioned in this task:
- [Multi-factor-authentication](https://auth0.com/docs/secure/multi-factor-authentication)
- [Configure SMS and Voice Notifications for MFA](https://auth0.com/docs/secure/multi-factor-authentication/multi-factor-authentication-factors/configure-sms-voice-notifications-mfa)

      
Congratulations, you’ve completed task 6.1 by enabling Multi-factor Authentication in our Okta CIC tenant with a policy to not show a multi-factor authentication by default.

# Trigger MFA for specific Organizations

Actions are one of the key flexibility which drives many options within Okta CIC’s overall extensibility. With Actions, you can add essential custom logic to your login and other identity flows specific to your needs. 


> **Note** :thought_balloon: - Actions also allow you to connect external integrations that enhance your overall extensibility experience.

In this challenge, you will configure an Action within your Okta CIC tenant that will query the Organization metadata and will trigger MFA if needed.   


Let’s get started!   


### Create Custom MFA Policy as Action


#### 1. In Okta CIC left navigation menu Actions section, click on Library


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/nav-to-actions-lib.png?raw=true)   


#### 2. Click on Build Custom


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/custom-action-build.png?raw=true)   



#### 3. Name it as "**`Trigger Org-based MFA`**" and click on the **`Create`** button.


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/new-action.png?raw=true)   


> **Note**:exclamation: - make sure it is showing the “**Login / Post Login**” Trigger

#### 4. Paste the code into your action

```javascript
/**
  * Handler that will be called during the execution of a PostLogin flow.
  *
  * @param {Event} event - Details about the user and the context in which they are logging in.
  * @param {PostLoginAPI} api - Interface whose methods can be used to change the behavior of the login.
  */

exports.onExecutePostLogin = async (event, api) => {
    // Avoid MFA if already done before
    if (event.authentication && event.authentication.methods){
        const method = event.authentication.methods.find((method) => method.name === 'mfa');
        if (!!method) {
            return;
        }
    }

    // get the Org metadata information
    if (event.organization?.metadata) {
        const MFAOption = event.organization.metadata.MFA_Enabled;
        if (MFAOption!=null && String(MFAOption).toLowerCase() === 'true') {
            api.multifactor.enable("any");
        }
   }
};
```

#### 5. Click on Deploy


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/deploy-button.png?raw=true)   



### Update our Login Flow

#### 6. Click on Flows


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/flows-menu-item.png?raw=true)   



#### 7. Click on the Login Flow   

We are now going to include the action in the login flow.


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/login-flow-button.png?raw=true)   



#### 8. Click on "**Custom**" at the right side of the flow digram


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/custom-actions-tab-link.png?raw=true)   


#### 9. From ther left side, drag and drop your action into the flow to create the following:


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/updated-flow.png?raw=true)   


#### 10. Click on Apply

Your flow is going to be updated


![](https://github.com/lerer/cic2-workshop/blob/main/images/006/flow-updated-message.png?raw=true)   



#### 11.  Done!


The above Action you just included in the login flow will run on authentication. If the user logs in as part of an organization which has a metadata name “**MFA_Enabled**” setup with a value of "**True**" (case insensitive), it will trigger MFA.

let’s test out our new MFA policy in the next section.


# Test your MFA Policy


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
