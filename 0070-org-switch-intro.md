## 7.0 Intro to Organization Switcher


### Enabling collaboration across organizations

In this challenge we will address a scenario when a user is working as a collaborator in more than one organization, such as subcontractors. A simple implementation would be to register the same user twice (one to each organization) and have him/her/it logout and login again when switching between organizations. 


However, the above implementation will not provide the best user experience as it will create user fatigue login and logout with the fact they will need to remember 2 passwords (or more). As well as a SaaS provider, you will own and manage a user profile per each organization the same human is a member of.


An alternative implementation would be to manage a single user identity and have it associated to each allowed organization with its own contextual role.


We will now guide you how to implement the collaboration model as mentioned above.


Note - additional supporting documentation to the following Challenge can be found here: https://auth0.com/docs/manage-users/organizations/login-flows-for-organizations


Let's Start!
