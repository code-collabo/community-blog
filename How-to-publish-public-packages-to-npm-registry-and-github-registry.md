# Title: **HOW TO PUBLISH PACKAGES TO NPM AND GITHUB REGISTRIES**

***

### **The Node Package Manager is an online repository where NodeJS developers can publish their packages and libraries.**

### **Besides being an online repository, npm is a command-line tool enabling developers to interact with registered packages. This tool provides features such as package installation, version management, and dependency management.**

### **The article will guide you step-by-step on publishing packages to NPM (Node Package Manager) and GitHub Package Registry. It covers the necessary steps for both registries, which may involve several steps.**


*Blog post by [Israel Adedamola Adebayo](https://github.com/KamiNation).*

***

### **Prerequisites**
Below is the list of things you need to get started
- Nodejs installed
- GitHub account.
- GitHub repository for your package.

***

### **Publishing to NPM**
#### To publish packages to NPM registries, you can follow these steps:
1. You log in to your NPM account on your system. Run this command to log in.
```terminal
npm login
```


Your terminal will show a prompt to fill in your `username`, `password`, and a `two-factor authentication code` (if you enabled it on your account).

If you have followed every step above, you can now proceed to publish your package. 
Run this command to publish your package
```terminal
npm publish
```
   

To execute this command, you must provide a one-time password sent to your email address. After verification, npm will publish your package.

***

### **Publishing to GitHub Registries**
#### To publish packages to GitHub registries, you can follow these steps:
1. A personal access token is needed from the account you want to publish to. The personal access token should have access to the `read:packages` and `write:packages` scopes. 

2. Create a new `.npmrc` or edit an existing .npmrc in your home directory (~/.npmrc). You will now add the following line below, replacing `TOKEN` with the personal-access token you created above.  
```terminal
//npm.pkg.github.com/:_authToken=personal-access-token-goes-here
```

3. You will need to tell the package where to publish explicitly, or it will publish to the npm registry. You can do this in two ways:
   
   i. You can create a new `.npmrc` or edit an existing file in the same directory as your `package.json` file at the root of your project. Add the following line specifying the GitHub Packages URL and the account owner, and replace `OWNER` with the username of the GitHub user
   ```terminal 
   registry=https://npm.pkg.github.com/OWNER”
   ```

   ii. You can edit the `package.json` file and include a publishConfig entry. You can do this by adding the below code: 
   ```terminal
    "publishConfig": { 
    "registry":"https://npm.pkg.github.com"
    },
    ```

4. You must authenticate your token by logging into NPM with the npm login command. 
```terminal
npm login --registry=https://npm.pkg.github.com
```
Replace `username` with your GitHub username, `token` with your personal access token (PAT), and `public-email-address` with your email address that shows as a prompt in your terminal.

Finally, navigate to the root of your repository, where your package.json file is, and run the below command to publish.
```terminal
npm publish
```

### Conculsion
This article explains the steps required for publishing packages to both NPM and GitHub registries, outlining the prerequisites and detailed procedures for each platform. These instructions are essential for developers looking to distribute their packages effectively.


Resources:  

https://dev.to/jgierer12/how-to-publish-packages-to-the-github-package-repository-4bai  

https://codeytek.com/using-github-package-registry-publish-npm-packages/    

https://blog.bitsrc.io/github-package-registry-is-it-worth-trying-out-62163aa3d518  

https://sevic.dev/npm-publish-github-actions/  
  
https://ecanarys.com/introduction-to-github-package-registry/  

https://www.makeuseof.com/npm-publish-package-how/  

https://sebhastian.com/publish-package-to-npm/



