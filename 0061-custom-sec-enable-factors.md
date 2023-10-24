## 6.1 Enable MFA factors

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

