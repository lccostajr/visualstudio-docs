---
title: Setting up a Git Repository
description: Using Git and Subversion in Visual Studio for Mac.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: E992FA1D-B2AD-4A28-ADC6-47E4FC471060
---
# Set up a Git repository

Git is a distributed version control system that allows teams to work on the same documents simultaneously. This means there is a single server that contains all the files, but whenever a repository is checked out from this central source, the entire repository is cloned locally to your machine.

There are many remote hosts that allow you to work with Git for version control, however the most common host is GitHub. The following example uses a GitHub host, but you can use any Git host for version control in Visual Studio for Mac.

If you wish to use GitHub, make sure that you have an account created and configured before following the steps in this article.

## Creating a remote repo on GitHub

The following example uses a GitHub host, but you can use any Git host for version control in Visual Studio for Mac.

To set up a Git repository, execute the following steps:

1. Create a new Git repo at github.com:

    ![Create new git repo](media/version-control-git1-sml.png)

2. Set Repo Name, description, and privacy. Do **not** initialize Repo. Set .gitignore and license to None:

    ![Set details of git repo](media/version-control-git2.png)

3. The next page gives you an option to display and copy either the HTTPS or SSH address to the repo you have created:

    ![view and copy address](media/version-control-git3.png)

   You'll need the HTTPS address to point Visual Studio for Mac to this repo.

## Publishing an existing project

If you have an existing project that _is not_ already in version control, use the following steps to set it up in Git:

1.  Select the Solution name from the Solution Pad in Visual Studio for Mac.

2. In the Menu bar, select **Version Control > Publish in Version Control** to display the **Select Repository** dialog:

    ![Start checkout in Visual Studio for Mac](media/version-control-git4-sml.png)

    If this menu item appears greyed out in the menu, make sure you have selected the Solution name.

3. Choose the **Registered Repositories** tab and press the **Add** button:

    ![](media/version-control-git5.png)

4. Enter the name of the repository as you would like it to display locally, and paste in the URL from step #3. Your Repository Configuration dialog should look similar to the following. Press OK:

    ![Enter git details dialog](media/version-control-git6.png)

    It is also possible to use SSH to connect to Git.

5. To attempt to publish the app to Git, select the repository, and ensure that both **Module Name** and **Message** text fields are completed:

    ![Attempt to publish project to git](media/version-control-git7.png)

6. Click **Okay**, and then **Publish** from the alert dialog.

7. If you have not already entered your Git credentials in Visual Studio for Mac preferences, enter them now. First, you need to create an Access Token, which is used in place of a password. If you have not created an access token, follow the steps in the Git [Access Token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) documentation.

8. Enter the username and Personal Access Token, and press **Okay**:

    ![Enter username and password for git](media/version-control-git9-sml.png)

9. After a few seconds, the Solution should be published with its initial commit. Confirm it has been published by browsing the Version Control menu item, which should now be populated with many options:

    ![Version Control Menu](media/version-control-git10.png)

10. Once you start to make additional changes, select **Push Changes** to push the changes to the **remote** repository. This will allow all appropriate users to view it on github.com:

    ![Push Changes to remote repository](media/version-control-git11.png)

## Publishing a new project

The new project dialog can be used to publish a new project using git. To enable it, select the **Use git for version control.** checkbox, as illustrated in the following screenshot. This will initialize your repo and add an optional .gitignore file:

![Push Changes to remote repository](media/version-control-git12.png)

## Check out an existing repository

It's likely that you'll have to work with a GitHub repo that exists only on the remote, not on your local machine. Visual Studio for Mac allows you to check this repo out quickly. Follow the steps below to clone it to your machine:

1. In the Menu bar, select **Version Control > Checkout**:

2. This displays the **Connect to Repository** tab:

    ![Connect to Repository tab with details entered](media/version-control-git13.png)

3. On the GitHub page of the remote repository, press the **Clone or Download** button and copy the URL provided:

    ![github url displayed](media/version-control-git14.png)

4. Replace all the text in the **URL** entry field in the **Connect to Repository** tab. This will populate most other fields in this tab for you, as illustrated in the image in step #2.

5. Enter the directory that you want to clone the repo into and press **Checkout**.

> [!NOTE]
> You may experience issues if the repo is over 4 GB in size.

## Troubleshooting

If you have issues with initializing your project with an empty remote repository, you can try the following steps:

1. Go to your solution folder.
1. Press **Command + Shift + .** to show the hidden files and folders.
1. If there's a **.git** folder, delete it.
1. If there's a **gitignore** file, delete it.
1. Press **Command + Shift + .** to hide the files and folders.
1. Open your solution in VS for Mac.
1. On the solution Pad, select your solution node.
1. Browse to the Version Control menu and choose **Publish in Version Control**.
1. Follow the steps of the above tutorial starting from the step 6.

## See also

- [Version control in Visual Studio (on Windows)](/visualstudio/version-control/)