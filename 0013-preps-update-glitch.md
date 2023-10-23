## 1.3 Update Glitch App

In this task, we will integrate CIC with our Glitch Application.

In Glitch, go to the source code page of your Glitch application and in the left menu panel under Files, go to "src" folder. Once you are there, click to modify the file `auth_config.json`.

![](https://github.com/lerer/cic2-workshop/blob/main/images/001/auth-config.png?raw=true")


Then:
- Set the **`domain`** value to your CIC domain (the value that you got in the previous step)
- Set the **`clientId`** value to your CIC application ID (the value that you got in the previous step)
- Don’t touch the **`audience`** for now, we will do that later
  


**NOTE**: Glitch auto-saves so there is no save button.

**That’s it!** The CIC SPA SDK is already embedded into your application, so all that’s left to do is testing. All we had to do was put in some configuration. Please go to the next step to test your login.

**(Optional):** If you would like to learn more about the following topics in this task, please see the following: [Add Login to your Single Page Application](https://auth0.com/docs/quickstart/spa/vanillajs/interactive). You can also see the CIC SDK in action by navigating in your Glitch application to public ➡ src ➡ index.js.

