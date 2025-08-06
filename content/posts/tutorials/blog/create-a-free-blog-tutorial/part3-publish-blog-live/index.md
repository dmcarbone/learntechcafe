---
date: '2025-08-05'
draft: false
title: "Publish Your Blog with GitHub and Netlify"
description: "Part 3 of the Create-a-Free-Blog series: Step-by-step guide to hosting your Hugo blog on GitHub and deploying it with Netlify — 100% free, ad-free, and beginner-friendly."
tags: ["blogging tutorial", "free blog hosting", "netlify", "github", "static site generator", "hugo", "publish your blog", "beginner"]
categories: ["blogging", "web development", "create a blog tutorial"]
cover:
    image: "/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyprojectcover.png"
    alt: "Project dashboard showing a new, live blog hosted on Netlify."
    caption: "By the end of this tutorial, your blog will be online and publicly viewable on Netlify."
image: "/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyprojectcover.png"
---

## Create-a-Free-Blog — Part 3

Welcome back! In [Part 2](/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/), we built your blog **locally** using Hugo. Today, we're going to **publish it live on the internet** — completely free, and with zero ads — using [GitHub](https://github.com) and [Netlify](https://netlify.com).

Let’s go live.

---

## What You’ll Need

* A [GitHub](https://github.com/signup) account (free)
* A [Netlify](https://app.netlify.com/signup) account (also free)
* Your Hugo site folder (from Part 2). In this tutorial this folder is named `myblog`
* An internet connection

---

## Create a GitHub Repository

GitHub will store your blog’s source code -- everything inside your site folder will be pushed to a GitHub repository so that it's accessible by a hosting site, in this case, Netlify. Here’s how to create a repository (repo).

1. If you haven't already, create a GitHub account. Log into GitHub, click the `+` button, then click **New repository**.
<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/new-repository.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/new-repository.png" alt="In GitHub, select New repository." style="display: block; margin: 0 auto;">
</a>
2. Name it anything you'd like, in this tutorial the repository is named `myblog`. Leave it **public**.
3. Add a description if you'd like. Leave all other settings blank.
4. Click **Create repository**.
5. Copy the **HTTPS URL** it gives you (e.g. `https://github.com/yourname/myblog.git`).
<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myblogrepositoryurl.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myblogrepositoryurl.png" alt="Copy your HTTPS URL from GitHub." style="display: block; margin: 0 auto;">
</a>

---

## Initially Push Your Hugo Blog to GitHub

Locate your site folder and record the path -- you'll need this path frequently. Open a terminal and run `cd` followed by the path to your site folder. Here's an example using `myblog`:

> {{< bot >}} Your path might be structured a bit differently depending on your operating system. For example, Windows might begin with `C://...`.

```bash
cd /home/dan/Documents/website/myblog
```

Now run the below commands in terminal, replacing the URL with the **HTTPS URL** you obtained from your new GitHub repository. This sets the remote and branch, allowing you to push changes made on your local site files to your GitHub repo.

```
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourname/myblog.git
git branch -M main
git push -u origin main
```

> {{<bot>}} You’ll only need to set the remote and branch once, using the terminal.

After setting the remote and branch, from now on you can edit your local files, then **push** the changes to GitHub by **committing** manually using VS Code. You'll only need to touch the terminal to run your local server from now on!

## How to Update Your Blog to GitHub Manually

Now that's done, here's the process you will follow to make future edits to your blog and push the changes to your GitHub repo. In the next section, we'll use Netlify to publish live.

1. Open your [post from Part 2](https://learntechcafe.com/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/#create-your-first-post) in VS Code, edit the content (just add a few words) and save it. Now, on the pane on the left hand side of the screen, select the **Source Control** tab. See **#1** in image below.
2. Next, you should see the change you just made (and any other changes you've made as well) listed in the **Changes** section. Click the `+` button to **Stage Changes**. Staging just tells Git what changes to include in the next commit -- nothing is live just yet! There is also an option to **Stage All Changes** that appears when you hover over the **Changes** title. Doing this moves your changes into the **Staged Changes** area of the Source Control panel (see **#2** in image below ).
3. To commit the changes and push them to your GitHub repo, enter a short message describing the changes you made. See **#3**.
4. Click **Publish Branch** (see **#4**). This button will now appear as **Commit** the next time you wish to push a change to GitHub. Finally, click **Sync Changes** (this will appear after you publish branch or commit).
<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myfirstcommit.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/myfirstcommit.png" alt="In VS Code, edit your post, stage changes, commit to GitHub, and sync." style="display: block; margin: 0 auto;">
</a>

Your edits have now been synced to the GitHub repo. Now that you know how to make edits to your blog, you're now ready to publish your blog live!

## Deploy Your Blog on Netlify

Now let’s get it online with Netlify.

1. Log into Netlify. You'll need to create a team name.
2. Click **Add new project** then **Import an existing project**.
3. Choose **GitHub** and, if requested, authorize Netlify to access your account.
4. Select your repository (ex. `myblog`). Remember, the GitHub repo must be public. You can make this private, but we won't cover that today.
5. In the next screen:
    * Assign **Team** to the team you created initially.
    * For **Project name**, use the name of your website, although you can name it anything, as long as it isn't already taken. This will be used as the base of your URL. Ex. `learntechcafe-myblog` becomes `https://learntechcafe-myblog.netlify.app`. This can always be changed later if you change your mind.
    * **Branch to deploy:** `main`
    * **Build command:** `hugo`
    <a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig1.png" target="_blank" rel="noopener noreferrer">
    <img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig1.png" alt="Configuration settings for Netlify, image 1." style="display: block;">
    </a> 
    * **Publish directory:** public
    * Next, click **Add environment variables**. For **Key** enter `HUGO_VERSION`. For **Value** you must get the Hugo version you are using from the terminal using the command below. It should look something like `0.148.1`.
    ```
    hugo version
    ```
    * Leave all other settings as default.
    <a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig2.png" target="_blank" rel="noopener noreferrer">
    <img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part3-publish-blog-live/netlifyconfig2.png" alt="Configuration settings for Netlify, image 2" style="display: block;">
    </a> 
    * Click **Deploy Site**. The site name should be the project name you chose.

Wait a minute or two while Netlify builds your blog. When it’s done, you’ll get a public URL like:

`https://your-site-name.netlify.app` (ex. `learntechcafe-myblog.netlify.app`)

Open the link in your browser. Congrats — your blog is live!

> {{< bot >}} You can rename your site under **Domain Management**, **Production domains** in Netlify. Just click the **Options** button next to your new site, and select **Edit project name**.

## Final Update to `baseURL` Parameter

Now that your blog is live, there is one last critical item left to update. **You must** update Your `baseURL` parameter in your site's `hugo.yaml` file.

> **Tip:** Setting the `baseURL` parameter ensures that links work properly on the live site. If you don't update this, your live site might show broken links or odd styling!

* Open `hugo.yaml` in VS Code (located at the root of your site folder)
* Change: `baseURL: "" ` to **`baseURL: "https://your-site-name.netlify.app/"`**
* Save and commit changes to GitHub

Done! Remember, from now on you can save your changes in VS Code, stage your changes, and push them to GitHub by committing your changes. You can always commit changes via the terminal, but I recommend using the VS Code interface as it's easier for beginners to use.

## Optional: Add a Custom Domain

Not a fan of the end of your URL (ex.`.netlify.app`)? Want a custom domain like `thisisthecoolestblogever.com`? Unfortunately, you'll have to pay for a custom domain. Luckily, most domain names will cost around $15--$20 CAD per year.

If you decide you want a custom domain, you must purchase a domain from a registrar (e.g., Namecheap, Google Domains, etc.). Or you can just use Netlify to purchase a domain:

* In Netlify, go to **Domain management**, then **Production domains**. Click **Add a domain** then **Buy a new domain**. Search for an available domain name, and enter your payment information to purchase. Your domain name will automatically be assigned to your new site (assuming you only have one project in Netlify so far).


## Recap

You just:
* Created a GitHub repo and pushed your Hugo blog code
* Connected GitHub to Netlify to publish your site
* Updated your Hugo configuration in `hugo.yaml`
* *(Optionally)* set a custom domain

Your blog is now live -- ready to share with the world!

## Coming Up Next

In Part 4, we’ll cover how to write blog posts using Markdown, including:
* Headers, bold, italic
* Code blocks and inline code
* Links, images, and blockquotes

Have a question or want to show off your blog? 💬 [Send us a message](hello@learntechcafe.com) — we’d love to see what you’re working on!