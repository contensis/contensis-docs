1.  Once you have [configured](https://www.contensis.com/help-and-docs/guides/managing-users/single-sign-on/overview) your AD FS server and set up [AD FS in Contensis](https://www.contensis.com/help-and-docs/guides/managing-users/single-sign-on/overview), you should see a new **Sign in with AD FS** button on the Contensis login screen.

![](/image-library/resources-images/user-guides-images/adfs-17.x0c6c5af8.png?q=80&f=webp)

2.  Press **Sign in with AD FS** to be redirected to your AD FS logon screen.

![](/image-library/resources-images/user-guides-images/adfs-18.x4db03723.png?q=80&f=webp)

3.  Enter your username and password and press **Sign in**. You will be logged into Contensis.

If this is the first time a user has logged in, a user will be created in Contensis with a username which matches their AD username. If a Contensis user already exists with the same user name, then the user will be converted to an AD FS user. No permissions or group assignments will be lost.

All users created via an AD FS login are added to a system group called *AD Users*, this enables you to give the *AD Users* some default permissions.