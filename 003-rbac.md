# Role based Access Control

## 3.0 Intro to Role Based Access Control (RBAC)


Role-based access control (RBAC) refers to the idea of assigning permissions to users based on their role within an organization. It offers a simple, manageable approach to access management that is less prone to error than assigning permissions to users individually.


For example, if you were using RBAC to control access for an HR application, you could give HR managers a role that allows them to update employee details, while other employees would be able to view only their own details.



In this challenge, you will create 2 roles:
- **Admin role** - that provides all the permissions for the Dashboard API, namely inviting users to an organization, setting up SSO for an organization, viewing the members of an organization and their stats.
- **Member role** - that only has the permissions to view stats



## 3.1 Create Roles and assign permissions

### Step 1: Enable RBAC

Let's enable Role Based Access Control (RBAC) for our API first.
1. Navigate to **Applications** > **APIs** on the sidebar
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/003/nav-to-api.png?raw=true)


2. Click on your Dashboard API

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/dash-api.png?raw=true)


3. Under the `RBAC settings` section, turn on `Enable RBAC` and `Add permissions in the access token` and click `Save`.

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/api-settings.png?raw=true)



### Step 2: Create Roles

1. Navigate to **User Management** -> **Roles** in the Auth0 dashboard.

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/nav-to-roles.png?raw=true)


2. Click on `Create Role` to create a new **Admin** role.

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/new-admin-role.png?raw=true)


3. Go to the permissions tab for the newly created role and click on Add Permissions.

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/perm-tab.png?raw=true)


4. Select the Dashboard API that was created previously from the Add Permissions drop down

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/select-dash-api.png?raw=true)


5. Select all the permissions for the Dashboard API and click on Add Permissions

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/select-all-perms.png?raw=true)


  The Admin role should have the following permissions

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/adm-role-look.png?raw=true)


6. Repeat the procedure to create another role named **Member**

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/member-role.png?raw=true)


7. Go to the Permissions tab for the Member role and click on Add Permissions

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/member-perm-tab.png?raw=true)


8. Select the Dashboard API from the Add Permissions drop down

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/select-dash-api.png?raw=true)


9. Select (only) the `view:stats` permission and click on Add Permissions

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/member-view-perm.png?raw=true)


  The Member role should have `view:stats` permission

![](https://github.com/lerer/cic2-workshop/blob/main/images/003/member-role-look.png?raw=true)


### Good Job!
⁠We are ready to move to the next challenge where we will use these roles.


