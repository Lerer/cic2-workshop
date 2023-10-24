## 6.2 Trigger MFA for specific Organizations

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


