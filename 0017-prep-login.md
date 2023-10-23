## 1.7 Login

In this section, you will test your custom application and validate that your test user can authenticate successfully.

> __Note:__ To avoid any problems, this __should__ be done on a different browser session than the one you have been using. Opening an incognito tab is the easiest way to do so.

#### 1. Open your glitch app 
Launch a new browser profile or incognito tab, paste in the URL from your Glitch Preview Page and then click on `Login`.
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/001/login-button.png?raw=true)


#### 2. Click on Sign up 
Since you do not have an account, create a new user. 

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/signup-link.png?raw=true)

Any credentials would do (as long as you remember them), for example:

```
Email = example@atko.email
Password = Cic2-workshop
```

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/signup.png?raw=true)


#### ⁠3. That’s it! 
If successful, you will see:
- An updated profile icon in the upper right.
- When you click on the profile icon, you will see a dropdown.
- Click on the links `ID Token` and `Access Token`. This will open jwt.io and display the contents of the JWT tokens.
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/001/token-links.png?raw=true)


#### 4. Discuss about the tokens 
The token is opaque, but the user data is a JSON object. Why is that?
⁠
![](https://github.com/lerer/cic2-workshop/blob/main/images/001/jwtio.png?raw=true)


