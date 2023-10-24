## 6.0 Intro to flexible security

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
