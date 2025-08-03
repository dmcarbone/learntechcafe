---
date: '2025-08-03'
draft: false
title: "Install Hugo, Pick a Theme, and View Your New Blog Locally"
description: "Part 2 of our Create-a-Free-Blog Tutorial. We'll walk you through installing Hugo static site generator, picking a theme for your blog and viewing it locally in your browser."
tags: ["blogging tutorial", "free blog hosting", "ad-free blog", "beginner", "static site generator", "hugo", "github", "netlify", "build a blog", "markdown"]
categories: ["blogging", "web development", "create a blog tutorial"]
cover:
    image: "/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/mybloghomepage.png"
    alt: "Image of a newly created, basic blog homepage."
    caption: "You'll create  you first, basic blog site and view it locally on you computer."
image: "/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/mybloghomepage.png"
---

## Create-a-Free-Blog -- Part 2

Thanks for joining us! Grab a drink -- today we’re going to get hands-on and generate your blog **locally** using [Hugo](https://gohugo.io/), a fast and modern static site generator. This means your blog won’t be live on the internet just yet -- we’ll get there in Part 3.

We’ll install Hugo, pick a theme, create your first post, and preview your blog in your browser.

If you missed the first post, see [Part 1: Create a Clean Zero-Ad Blog for Free](/posts/tutorials/blog/create-a-free-blog-tutorial/part1-create-a-clean-zero-ad-blog-for-free/).

---

## What You'll Need

* A computer with a stable internet connection (Windows, macOS, or Linux)
* A terminal or command line tool (pre-installed on all operating systems)
* A code editor -- we recommend Visual Studio Code, and if you don't have this already, we'll
show you how to install it.

---

## What is Hugo?

[Hugo](https://gohugo.io/) is a free, open-source **static site generator** written in Go. It turns plain text files written in Markdown into a complete, fast-loading blog or website. Unlike platforms like WordPress, Hugo creates **static** files (called HTML, CSS and JavaScript(JS)) that are easy to host and maintain.

> {{<bot>}} HTML, CSS and JS are the three foundational languages used to create websites. 

Hugo makes creating a blog easy by generating most of the above files for you. You only really need to worry about creating posts (more to come on that) -- however, you can customize your blog using these languages as much as you're comfortable with. We won't be touching on them much in these tutorials.

**Benefits of using Hugo**:

* Super fast page loads
* No databases to manage
* Perfect for learners, writers, or developers
* Completely free and ad-free

---

## Installing Hugo and Git

We’ll guide you through installing Hugo for Windows, macOS, and Linux. You’ll also need [Git](https://git-scm.com/), which is required to install themes.

### Windows Setup

1. **Open PowerShell as Administrator**
   * Right-click PowerShell and choose **Run as Administrator**
2. **Install Scoop (a package manager)**
   * First you must install a package manager. I recommend Scoop, an open-source package manager.
   * In Powershell, enter the following code and press *Enter*.

   ```powershell
   Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
   irm get.scoop.sh | iex
   ```

   * When prompted, type *Y* and press *Enter*.
3. **Install Hugo Extended**
   * Next run the following:

   ```powershell
   scoop install hugo-extended
   ```

4. **Verify Installation**
   * Hugo should now be installed. To verify the installation, type the following:

   ```powershell
   hugo version
   ```

   * You should see this output:

   ```powershell
   hugo v0.xx.x-XXXXXXX+extended windows/amd64
   ```

5. **Install Git**
   * Download Git from [git-scm.com/download/win](https://git-scm.com/download/win) and run the installer -- Git is what lets you use Hugo themes for your website.

### macOS Setup

1. **Install Homebrew (if you don’t have it)**
   * First you must install a package manager. Homebrew is the most common package manager on macOS. If you don't have it installed already, first, open your terminal and paste the following command:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Hugo and Git**
   * In your terminal, run the following to install both Hugo and Git at once. Git is what allows you to install Hugo themes for your site.

   ```bash
   brew install hugo git
   ```

3. **Check Hugo Version**
   * Hugo and Git should now be installed. To verify the Hugo installation, type the following:

   ```bash
   hugo version
   ```

   * You should see this output:

   ```bash
   hugo v0.xx.x+extended darwin/arm64 (or amd64)
   ```

### Linux (Linux Mint 22.1 example)

> Commands may vary depending on your distribution. We here at *LearnTechCafe* use Linux Mint 22.1.

> {{<bot>}} Minty!

1. **Download the latest Hugo Extended release**

   * Visit the [Hugo Releases Page](https://github.com/gohugoio/hugo/releases)
   * Download the latest extended version of the following file to your `Downloads` folder: `hugo_extended_0.xx.x_Linux-64bit.tar.gz`

2. **Extract and Install**
   * Extract the file from your `Downloads` folder and install Hugo by running the following: 

   ```bash
   cd ~/Downloads
   tar -xzf hugo_extended_0.xx.x_Linux-64bit.tar.gz
   sudo mv hugo /usr/local/bin/
   sudo chmod +x /usr/local/bin/hugo
   ```

3. **Verify Installation**
   * Hugo should now be installed. To verify the installation, type the following:

   ```bash
   hugo version
   ```

   * You should see this output:

   ```bash
   hugo v0.xx.x+extended linux/amd64
   ```

4. **Install Git**
   * Now install Git by running the following. Git is what lets you install themes in your Hugo website.

   ```bash
   sudo apt install git
   ```

---

## Install Visual Studio Code

From here on out, the same instructions apply to all operating systems.

If you don’t already have a code editor, download and install [Visual Studio Code](https://code.visualstudio.com/download) (VS Code). It’s lightweight, beginner-friendly, and works across all major platforms.

---

## Create Your Hugo Site

Now that Hugo is installed, let's create your blog!

1. **Open your terminal** and run:

   ```bash
   hugo new site myblog --format yaml
   ```

   You can replace `myblog` with any name you like -- typically, the name of your blog (no spaces). In this tutorial, we will continue to use the name `myblog`. The `--format yaml` portion is optional. It changes the default configuration file from *hugo.toml* to *hugo.yaml*, which is generally easier to read. In the terminal, you should see something like the following:

   <a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/create-myblog-terminal.png" target="_blank" rel="noopener noreferrer">
   <img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/create-myblog-terminal.png" alt="Output from terminal after creating a new site." style="display: block; margin: 0 auto;">
   </a>

   > **Tip:** Note the second line which says `Your New Hugo site was created in...`. Remember this folder location -- this is where your new site folder is stored.


2. **Navigate to your new folder** and explore the structure. This is the **root** folder
   and contains the structure of your entire blog -- it's where you'll store your theme, content, images, etc. You’ll see folders like `content`, `themes`, and the configuration file, `hugo.yaml`.

   > {{<bot>}} You can optionally move your root folder to another location, just do not remove the content within it.
   
   The folder structure should look like the following:

   ```
   myblog/
   ├── archetypes
   │   └── default.md
   ├── assets
   ├── content
   ├── data
   ├── hugo.yaml
   ├── i18n
   ├── layouts
   ├── static
   └── themes
   ```

---

## Pick and Install a Hugo Theme

Now for the fun part -- choosing a theme for your blog! Hugo offers dozens of free themes maintained by open-source developers.

1. Browse [Hugo themes](https://themes.gohugo.io/) and explore designs.
2. We recommend [PaperMod](https://themes.gohugo.io/themes/hugo-papermod/) -- it’s a solid
   option for a clean, modern blog, and is what *LearnTechCafe* uses. This is what we'll be using for this tutorial.

### To Install PaperMod:

**Note**: similar instructions apply to all Hugo themes. Just go to [Hugo themes](https://themes.gohugo.io/), click the theme you want, and look for a link to that theme's GitHub Repository (Repo).  
1. Visit the [PaperMod GitHub Repo](https://github.com/adityatelange/hugo-PaperMod)
2. Click the green **<> Code** button and select **Download ZIP**
3. Unzip the file
4. Copy the entire unzipped folder into your Hugo site’s `themes` directory
   It will be called something like `hugo-PaperMod-master`. Rename this folder to exactly `PaperMod` (capitalization matters).

In your root folder should now see:

```
myblog
├── archetypes
│   └── default.md
├── assets
├── content
├── data
├── hugo.yaml
├── i18n
├── layouts
├── static
└── themes
    └── PaperMod

```

### Edit Configuration File to Recognize Theme

You're almost ready to write your first post! All that's left is to make sure your configuration file points to your theme.

1. Open VS Code, then drag your root folder into the Explorer pane (see image below for an
   example of what it should look like). This will let you see your entire blog folder in
   VS Code. Open up the configuration file, `hugo.yaml`.
2. I recommend editing the `baseURL` to be `""`. We'll come back to this in Part 3.
> {{<bot>}} Each blue text followed by a colon is called a **parameter**, which controls
   various parts of the site. The text following it, after the space, is called the **value** for that parameter.
3. Finally, type a new parameter called `theme` and set the value to `PaperMod`. This
   tells Hugo which theme to use. If you don't do this, you won't be able to run or view your site. Save.

<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/VS-myblog-config.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/VS-myblog-config.png" alt="This is what dropping your root folder into Visual Code Studio looks like, along with how to edit your config file." style="display: block; margin: 0 auto;">
</a>

---

## Create Your First Post

Time to write a basic post to see your blog in action. Back in the terminal, generate a new post file by running:

```
hugo new posts/my-first-post.md
```

This creates a draft post in `content/posts/my-first-post.md`. The `posts` folder will contain all your posts -- you can always add subfolders to break up your post structure as you get more comfortable with Hugo.

Locate and open your first post file in VS Code and:
* Change `draft: true` to `draft: false`.

> {{<bot>}} By default, a new post is considered a draft and is labelled as `draft: true`. This value must be changed to `draft: false` in order to be published live.

* The front matter is the information that is pre-populated at the top of the file, between the two `---` lines. Add some test content under the front matter. Just a sentence or two will do for now.

---

## Run Your Blog Locally

Now let's see your blog! To preview your site run:

```
hugo server
```

Open your browser and visit: [http://localhost:1313](http://localhost:1313). You should see your blog running locally on your computer! Try clicking on the post to open it up in a new page. You'll also see a niftly toggle button near the top of the page which switchs your site between light and dark mode.

<a href="/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/mybloghomepage.png" target="_blank" rel="noopener noreferrer">
<img src="/posts/tutorials/blog/create-a-free-blog-tutorial/part2-install-hugo/mybloghomepage.png" alt="This is something like what you should in your browser after running your site locally." style="display: block; margin: 0 auto;">
</a>

> {{<bot>}} Outstanding! To stop running your blog locally, either close the terminal, or, click `CTRL + C` twice to stop while keeping the terminal open.

---

## Recap

You just:
* Installed Hugo and Git
* Created your blog site folder
* Installed a theme
* Created your first post
* Ran the blog locally in your browser

Nice work! From now on, you can preview your content and changes live in your browser. Play around with updating some content in your post.

---

## Coming Up Next

In Part 3 of our Create-a-Free-Blog Tutorial, we'll walk you through how to publish your blog live using GitHub and Netlify. We'll get into using Markdown to write and customize you posts in Part 4.

This blog is still super-new, so we don’t have an email list (yet). But we’d love your feedback!

[💬 Send us a message](mailto:hello@learntechcafe.com) -- let us know what you'd like to see next.

---

**Coming soon:** Markdown cheat sheet + Hugo command quick guide! 
