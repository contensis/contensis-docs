1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-dotnet)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 10 December 2024

## On this page

-   [Fork the Razor Pages Leif example 🍴](#fork-the-razor-pages-leif-example)
-   [Cloning the repository 🤝](#cloning-the-repository)
-   [Running the Application 🥳](#running-the-application)
-   [Using your own content 📚](#using-your-own-content)

This step-by-step guide will take you through getting your entries from Contensis and displaying them using the Delivery API and a simple .Net Razor Pages app.

We'll start by setting up our [demo project](https://github.com/contensis/razor-page-leif-example), which is a simple .NET blog application. This app will pull in data from our demo Leif project using Contensis.

## Fork the Razor Pages Leif example 🍴

First, we need to fork the Razor Pages Leif example on GitHub to create our own copy of the repo. To do this:

1.  Log into your GitHub account.
2.  Go to [https://github.com/contensis/razor-page-leif-example](https://github.com/contensis/razor-page-leif-example) and fork the repo.

## Cloning the repository 🤝

Now we have our own fork of the repository, we need to clone it to create a copy of the fork on our local machine. There are two ways to do this – using SSH or HTTPS. If you have already set up SSH keys for your GitHub account, then it's easier to use SSH. If you haven't set up SSH keys, you can use HTTPS instead.

### Clone the repository using SSH

1.  First, open up a terminal and `cd` into your local development folder.
2.  Now clone the repository using SSH with the following command:

Bash

```
git clone git@github.com:{your-username}/razor-page-leif-example.git
```

3.  Then navigate to the project directory:

Bash

```
cd razor-page-leif-example
cd RazorPageLeifExample
```

### Clone the repository using HTTPS

If you haven't set up SSH keys for your GitHub account, you can use HTTPS instead of SSH to clone repositories. Use the following steps to configure Git to use HTTPS.

1.  Depending on your operating system, open Terminal (on macOS and Linux) or Command Prompt (on Windows).
2.  Enter the following commands to configure Git with your GitHub credentials:

Bash

```
git config --global user.name "Your GitHub Username"
git config --global user.email "your.email@example.com"
```

3.  Now enter the following command to clone the repository using HTTPS:

Bash

```
git clone https://github.com/{your-username}/razor-page-leif-example.git
```

4.  Then navigate to the project directory:

Bash

```
cd razor-page-leif-example
cd RazorPageLeifExample
```

## Running the Application 🥳

Now we've successfully cloned the repo and are in the correct folder, we can run the app locally on our machine. To run your app locally, enter the following command in your terminal:

Bash

```
dotnet watch
```

This will start the server. You can then access the application by visiting `http://localhost:3000` in your web browser.  
The application should look something like this:

![](/image-library/resources-images/getting-started-guides/razor-pages-leif-example.x0894eabe.png?q=80&f=webp)

If you get any errors, make sure the following are installed on your machine:

## Using your own content 📚

At the moment the application is using data from our public demo environment. To start using your own data, you'll need to connect your own Contensis environment. Follow these steps to connect a free trial environment:

1.  Create an account with [Contensis](https://www.contensis.com/account/registration) or [log in](https://www.contensis.com/account/login).
2.  Navigate to your [account dashboard](https://www.contensis.com/account/dashboard) and launch your free trial environment. (If you don't have a free trial, you [can request one here](https://www.contensis.com/contact-us/general-enquiries)).
3.  The first thing we need to do is update the `CONTENSIS_CLIENT_ID` and `CONTENSIS_CLIENT_SECRET` in the `.env` file with credentials from our own API key. Go to Settings > API Keys in your Contensis project.
4.  Press the **New API Key** button in the top-right corner to create a new API key.
5.  Copy the `CONTENSIS_CLIENT_ID` and `CONTENSIS_CLIENT_SECRET` from your API key into the `.env` file.

![](/image-library/resources-images/user-guides-images/adding-a-new-api-key.xdb577f35.png?q=80&f=webp)

6.  You now need to replace the `PROJECT_API_ID` in the `.env` file with the API ID from your own project. In your Contensis project, go to Settings > General and copy the API Name field.

![](/image-library/resources-images/getting-started-guides/api-name-field.xc0f6ddb3.png?q=80&f=webp)

7.  Open the `.env` file in your IDE again and replace the `PROJECT_API_ID` with the API ID from your Contensis project.
8.  Finally, determine your `ALIAS` by examining your CMS URL, for instance, cms-leif.cloud.contensis.com. Extract the part that follows cms-. In this example, the `ALIAS` would be 'leif'.

That's it, you're all set up! 👏

## On this page

-   [Fork the Razor Pages Leif example 🍴](#fork-the-razor-pages-leif-example)
-   [Cloning the repository 🤝](#cloning-the-repository)
-   [Running the Application 🥳](#running-the-application)
-   [Using your own content 📚](#using-your-own-content)