## 3.0 Intro to Role Based Access Control (RBAC)


Role-based access control (RBAC) refers to the idea of assigning permissions to users based on their role within an organization. It offers a simple, manageable approach to access management that is less prone to error than assigning permissions to users individually.


For example, if you were using RBAC to control access for an HR application, you could give HR managers a role that allows them to update employee details, while other employees would be able to view only their own details.



In this challenge, you will create 2 roles:
- **Admin role** - that provides all the permissions for the Dashboard API, namely inviting users to an organization, setting up SSO for an organization, viewing the members of an organization and their stats.
- **Member role** - that only has the permissions to view stats



