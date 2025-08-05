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
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myblogrepositoryurl.png" alt="In GitHub, select New repository." style="display: block; margin: 0 auto;">
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

Here's the process you will follow from now on to make edits to your blog and push the changes to your GitHub repo.

1. Open up a post 

## Deploy Your Blog on Netlify

Now let’s get it online with Netlify:
Log into Netlify
Click Add new site > Import an existing project
Choose GitHub and authorize Netlify to access your account
Select your myblog  repository
Configure the build settings:
    Build command: hugo
    Publish directory: public
Click Deploy Site

Wait a minute or two while Netlify builds your blog. When it’s done, you’ll get a public URL like:

https://your-site-name.netlify.app

Open the link in your browser. Congrats — your blog is live!

**Tip:** You can rename your site under Site Settings > Domain Management in Netlify.

Update Your baseURL in hugo.yaml
To make sure links work properly on the live site, update the baseURL parameter in your configuration file.

Open hugo.yaml in VS Code

Change:

baseURL: "" 

to:

`baseURL: "https://your-site-name.netlify.app/"`

From now on you can save your changes in VS Code, stage your changes, and push them to GitHub by committing your changes. You can always commit changes via the terminal, however I recommend using the VS Code interface as it's easier for beginners to use.

Insert image of staging an committing

Once you’ve commited, you will see a Sync  option appear. Click sync. Netlify will automatically rebuild your site with the updated link structure. Refresh your browser to see your update. How cool is that?

{{<bot>}} So cool!

Optional: Add a Custom Domain

Want a custom domain like mycoolblog.com?

Purchase a domain from a registrar (e.g., Namecheap or Google Domains). Or you can just use Netlify to purchase a domain, here's how………. Your blog url will change automatically.

If you buy your domain outside of Netlify you must do the following. In Netlify, go to Site Settings > Domain Management > Add Custom Domain.

Follow the steps to point your domain to Netlify.

Recap

You just:
Created a GitHub repo and pushed your Hugo blog code
Connected GitHub to Netlify to publish your site
Updated your Hugo configuration
(Optionally) set a custom domain

Your blog is now live and ready to share with the world!

Coming Up Next

In Part 4, we’ll cover how to write blog posts using Markdown, including:
Headers, bold, italic
Code blocks and inline code
Links, images, and blockquotes

Have a question or want to show off your blog? 💬 [Send us a message](hello@learntechcafe.com) — we’d love to see what you’re working on!