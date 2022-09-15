# How to publish Visual Studio Code Extensions?

> Note: this is not a professional guide or step by step guide, it's just an unofficial guide that helps me understand few things more easily, usually when I am publish/update extension after a long time and forget how to get it done.

All the vscode extensions are published in [Visual Studio Code Marketplace](https://marketplace.visualstudio.com/vscode), if you have developed your own extension and want to publish in on marketplace so that others can find it as well then you can follow the guide below.

> Visual Studio Code already made a documention on [Publishing Extensions](https://code.visualstudio.com/api/working-with-extensions/publishing-extension) you should read it first.

I am only adding some extra noticeable points because each time I publish a new version I forget a couple of things.

If you read the offical documentation, you'll know for publishing a vscode extension you need 2 things

1. `vsce` cli
2. Personal Access Token

Installing `vsce` cli and using it easy thing so nothing to explain about it.
However getting personal access token could be tricky or you forget it how to do it. so we'll get the steps for it.

---

## Getting token first time

1. First of all you need to go <https://portal.azure.com/> and register and login. I will suggest you to choose **Sign in with Github** for login.

2. Once, you're logged-in, in your dashboard home page, you'll find **Azure DevOps Organizations** under **Azure services**, if you don't then you can search in the search box and click on it.

3. Then you'll redirect on new page, in that page you'll find a link labeled by **My Azure DevOps Organizations**, click on that.

4. Now you'll redirect on a new url that will be similar to this <https://aex.dev.azure.com/me>, you'll find a button **Create New organization**, click on that and create a new organization, it will generally ask for **Name** and **Slug**.

5. After you created the organization, you'll redirect on organiazation main page, if you don't then you'll find a link like this <https://dev.azure.com/{organization-slug}/> click on that and open it.

6. on this organization page, you'll be shown to create the project. you can skip that you don't really need it for token.

7. Now on top-right you'll find a user icon(hover on that icon it will show User Settings), click on that, then in menu list choose "Personal access tokens"

8. Rest guide is same as [given here](https://code.visualstudio.com/api/working-with-extensions/publishing-extension#get-a-personal-access-token).

---

## Getting new tokens (not first time)

1. You can open <https://dev.azure.com/{organization-slug}> the link and it will take you to the organization page and then you can follow point 7 & 8 from above.

2. if you don't remember orgnaziations slug, then follow point 1, 2, 3 from getting first time section, then you'll find your organization list, click on link then follow point 7 & 8.
