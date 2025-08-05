---
date: '2025-08-04'
draft: true
title: "Publish Your Blog with GitHub and Netlify"
description: "Part 3 of our Create-a-Free-Blog Tutorial. Learn how to publish your blog online using GitHub and Netlify — totally free and ad-free."
tags: ["blogging tutorial", "free blog hosting", "netlify", "github", "static site generator", "hugo", "publish your blog", "beginner"]
categories: ["blogging", "web development", "create a blog tutorial"]
cover:
    image: "/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-github-netlify/publish-cover.png"
    alt: "A browser showing a live blog hosted on Netlify."
    caption: "By the end of this tutorial, your blog will be online and publicly viewable!"
image: "/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-github-netlify/publish-cover.png"
---

## Create-a-Free-Blog — Part 3

Welcome back! In [Part 2](/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/), we built your blog **locally** using Hugo. Today, you're going to **publish it live on the internet** — completely free, and with zero ads — using [GitHub](https://github.com) and [Netlify](https://netlify.com).

Let’s go live.

---

## What You’ll Need

* A [GitHub](https://github.com/signup) account (free)
* A [Netlify](https://app.netlify.com/signup) account (also free)
* Your Hugo blog folder (from Part 2). In this tutorial this folder is named `myblog`
* An internet connection

---

## Create a GitHub Repository

GitHub will act as the storage for your blog's source code. Here’s how to create a repository (repo).

1. Log into GitHub, click the `+` button, then click **New repository**
<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/new-repository.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/new-repository.png" alt="In GitHub, select New repository." style="display: block; margin: 0 auto;">
</a>
2. Name it anything you'd like, in this tutorial the repository is named `myblog`. Leave it **public**
3. Add a description if you'd like. Leave all other settings blank
4. Click **Create repository**
5. Copy the **HTTPS URL** it gives you (e.g. `https://github.com/yourname/myblog.git`)
<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myblogrepositoryurl.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myblogrepositoryurl.png" alt="Copy your HTTPS url from GitHub." style="display: block; margin: 0 auto;">
</a>

---

## Initially Push Your Hugo Blog to GitHub

Locate your blog folder and record the path -- you'll use this a lot. Open a terminal and run `cd` followed by the path to you blog folder. Here's an example using `myblog`:

```bash
cd /home/dan/Documents/website/myblog
```

Now run this in terminal, replacing the url with the **HTTPS URL** you obtained from your new GitHub repository. This sets the remote and branch; which allows you to sync changes made on you local blog files to you GitHub repo.

```
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourname/myblog.git
git branch -M main
git push -u origin main
```

> {{<bot>}} You’ll only need to set the remote and branch once, using the terminal.

After setting the remote and branch, from now on you can edit your local files, then **push** the changes to GitHub by **committing** manually using VS Code. You'll only need to touch the terminal to run your local server from now on!

## How to Update Your Blog to GitHub Manually

Here's the process you will follow from now on to make edits to your blog and push the changes to your GitHub repo. After that, we'll use Netlify to publish live.

1. Open up a post in VS Code, edit the content (just add a few words) and save it. Now, on the pane on the left hand side of the screen, select the **Source Control** tab. See image below.
2. Next, you should see the change you just made (and any other changes you've made as well) listed under the **Changes** dropdown. Click the `+` button to **Stage Changes**. There is can also an option to **Stage All Changes** that appears if you hover over the **Changes** title. Doing this pushes you changes to the repo dropdown, called **myblog Git** in this excerise.
3. To commit the changes and push them to you GitHub repo, enter a name for your commit by describing the changes you made.
4. Click **Publish Branch**. This button will now appear as **Commit** the next time you wish to push a change to GitHub. Finally, click **Sync Changes**.
<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myfirstcommit.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myfirstcommit.png" alt="In VS Code, edit your post, stage changes, commit to GitHUb and sync." style="display: block; margin: 0 auto;">
</a>

Your edits have now been synced to the GitHub repo. Now that you know how to make edits you're now ready to publish you blog live!

## Deploy Your Blog on Netlify

Now let’s get it online with Netlify.

1. Log into Netlify. You'll need to createa team name.
2. Click **Add new project** then **Import an existing project**
3. Choose GitHub and, if requested, authorize Netlify to access your account
4. Select your repository (ex. `myblog`). Remmeber, the GitHub repo must be public. It is
possible to set this to private as well, however we won't go over that today.
5. In the next screen:
    * Assign **Team** to the team you created initially.
    * For **Project name**, use the name of you website, although you can name it anything, as long as isn't already taken. This will be used as the base of your url. Ex. `learntechcafe-myblog` becomes `https://learntechcafe-myblog.netlify.app`. This can always be changed later if you change your mind.
    * **Branch to deploy:** leave as `main`
    * **Build command:** hugo
    <a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig1.png" target="_blank" rel="noopener noreferrer">
    <img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig1.png" alt="Configuration settings for Netlify, image 1." style="display: block;">
    </a> 
    * **Publish directory:** public
    * Next, click **Add environment variables**. For **Key** enter `HUGO_Version`. For **Value** you must get the Hugo version you are using from the terminal using the below command. It should look something like `0.148.1`.
    ```
    hugo version
    ```
    <a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig2.png" target="_blank" rel="noopener noreferrer">
    <img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig2.png" alt="Configuration settings for Netflify, image 2" style="display: block;">
    </a> 
    * Click **Deploy Site**. The site name should be the project name you chose.

Wait a minute or two while Netlify builds your blog. When it’s done, you’ll get a public URL like:

`https://your-site-name.netlify.app` (ex. `learntechcafe-myblog.netlify.app`)

Open the link in your browser. Congrats — your blog is live!

> {{< bot >}} You can rename your site under **Domain Management**, **Production domains** in Netlify. Just click the **Options** button next to your new site, and select **Edit project name**.

## Final Tweak

Now that your blog is live, there is one last thing left to update. First you must update Your baseURL parameter in `hugo.yaml`, which ensures that links work properly on the live site.

* Open h`ugo.yaml` in VS Code
* Change: `baseURL: "" ` to `baseURL: "https://your-site-name.netlify.app/"`

Done! Remeber, from now on you can save your changes in VS Code, stage your changes, and push them to GitHub by committing your changes. You can always commit changes via the terminal, however I recommend using the VS Code interface as it's easier for beginners to use.

## Optional: Add a Custom Domain

Not a fan of the end of you url, `....netfliy.app`? Want a custom domain like `thisisthecoolestblogever.com`? Unfortunately, you'll have to pay for a custom domain. Luckily, most domain names will only cost you around $15-$20 CAD.

If you decide you want a custom domain, you must purchase a domain from a registrar (e.g., Namecheap or Google Domains). Or you can just use Netlify to purchase a domain:

In Netlify, go to **Domain management**, then **Production domains**. Click **Add a domain** then **Buy a new domain**. Search for an available domain name, and enter your payment information to purchase. You domain name will automatically be assigned to your new site (assuming you only have one project so far).


## Recap

You just:
* Created a GitHub repo and pushed your Hugo blog code
* Connected GitHub to Netlify to publish your site
* Updated your Hugo configuration in `hugo.yaml`
* *(Optionally)* set a custom domain

Your blog is now live and ready to share with the world!

## Coming Up Next

In Part 4, we’ll cover how to write blog posts using Markdown, including:
* Headers, bold, italic
* Code blocks and inline code
* Links, images, and blockquotes

Have a question or want to show off your blog? 💬 [Send us a message](hello@learntechcafe.com) — we’d love to see what you’re working on!