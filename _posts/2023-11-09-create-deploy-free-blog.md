---
title: "How to create a complete blog website and host for free"
date: 2023-11-09
last_modified_at: 2023-11-09
tags:
  - "Blog"
  - "Hosting"
comments: true
---

In this post, we go through on how to set up a blog/portofolio website with [Jekyll](https://jekyllrb.com/) and host the website on [Netlify](https://www.netlify.com/) for completely free. No coding required guys!

## Introduction

[Jekyll](https://jekyllrb.com/) is a blog-aware static site generator written in Ruby which we use to build our website and we deploy our site to [Netlify](https://www.netlify.com/). Netlify is primarily used for serverless application hosting and they have a generous **100GB free traffic per month**😊 which is totally helpful for starters. Not just Netlify, [Azure Static Web App](https://azure.microsoft.com/en-ca/products/app-service/static), [Github Pages](https://pages.github.com/) and others offer 100GB free traffic. 

Taking off a server and using a static website has huge benefits.
* Don't have to pay for a expensive server to host
* If there's a need for dynamic content we can use Javascript and API's to deliver content(JAMStack).
* Deploy our website to Content Delivery Networks(CDN) for super fast loading of pages and so on..

## How to setup our website with Jekyll

### Install Jekyll on Windows/Linux/Mac

Follow the [installion](https://jekyllrb.com/docs/installation/) instructions listed on Jekyll website to install Ruby languge on your desktop and install Jekyll, bundler as gems. <br>For windows, run the command `bundle add webrick` to add webrick gem after initializing the project so that you don't run into webrick errors that come in windows when you run the website.

### Initialize the project

Create a new Jekyll Site with the below command
```bash
jekyll new my-blog
```
cd into `my-blog`
```bash
cd my-blog
```
You'll see the default files and folders that `Jekyll new` command created inside `my-blog` folder.
`Jekyll new` command includes a simple starter blog site using [Minima](https://github.com/jekyll/minima) theme.
![Jekyll new folder cmd folder structure]({{ site.url }}{{ site.baseurl }}/assets/images/uploads/2023-11-09-jekyll-new-folder-default-files.png)

To run and test the website on local server, run the below command and go to [http://localhost:4000](http://localhost:4000) to see it live.
```bash
bundle exec jekyll serve
```

### Use theme Minimal Mistakes

The easiest way to build our website is to use popular Jekyll theme [Minimal mistakes](https://github.com/mmistakes/minimal-mistakes). This theme has lot of documentation and customization options and I believe it fits all your blog needs. All you have to do is edit one file `_config.yml` to do customizations for our website.

There are a couple ways to install the theme. But I'd recommend gem based installion as it is easy to update the theme in the future.

1. To add theme as a gem add below line at the end of `Gemfile`.
   ```ruby
   gem "minimal-mistakes-jekyll"
   ```
1. To install Minimal Mistakes theme as gem and update existing gems, type below bundler command in
   terminal.
   ```bash
   bundle
   ```
1. Now, change the default theme from `minima` to `minimal-mistakes-jekyll`in `_config.yml` file to set your theme to Minimal Mistakes.
   ```yaml
   theme: minimal-mistakes-jekyll
   ```

### Setup the theme

1. Change the front matter of the home page in `index.markdown` to the following
   ```
   ---
   layout: home
   author_profile: true
   ---
   ```
1. Change the `layout: post` in `YYYY-MM-DD-welcome-to-jekyll.markdown` to `layout: single`
1. Remove `about.markdown`

Now, run the website with `bundle exec jekyll serve` and go to [http://localhost:4000](http://localhost:4000) to check the changes.

### Customize the website

Customize the website following the docs of theme especially visiting [Configuration](https://mmistakes.github.io/minimal-mistakes/docs/configuration/), working with [posts](https://mmistakes.github.io/minimal-mistakes/docs/posts/) and [pages](https://mmistakes.github.io/minimal-mistakes/docs/pages/) first.

<!-- 
### Add a new post

Jekyll posts are written under `_posts` folder and file names for posts are written in the format `YYYY-MM-DD-file-name.md`. File name is used in the URL of the post. For example `https://website.com/YYYY/MM/DD/file-name`. We can later customize the `URL slug` for our liking. -->

## Deploy site to Netlify.

The best way to deploy is to connect Netlify to GitHub Repository instead of manually uploading site files to Netlify. 

### Create a git repository and push to GitHub 

1. Initialize the git repository
   ```bash
   git init
   ```
1. Stage the current directory files to commit 
   ```bash
   git add .
   ```
1. Make your first commit in your local repository
   ```bash
   git commit -m "Initial commit"
   ```
1. Now, Create a empty github repository. Go to [Github](https://github.com), click on `+` icon and create a new repository, give a repository name, For ex., `my-blog` and click on `Create repository`
1. Add the URL of the remote github repository to your local repository.
   ```bash
   git remote add origin your_git_repository_URL
   ```
1. Push your local local repository code to Github.
   ```bash
   git push -u origin master
   ```

### Connect Github and Netlify

1. Go to [Netlify](https://app.netlify.com) and sign up for an account. Create a new team with a name. Now, click on `Import an existing project` under `Add new site`.
   ![Add new site]({{ site.url }}{{ site.baseurl }}/assets/images/uploads/2023-11-09-add-new-site.jpg)
1. Now select, `Deploy with Github` and Authroize Netlify on next screen to connect to Github
   ![Deploy with Github]({{ site.url }}{{ site.baseurl }}/assets/images/uploads/2023-11-09-deploy-with-github.png)

1. Search for your repository.If your repository won't show up when you search, press `Configure Netlify On Github`.
   ![Configure Netlify on Github]({{ site.url }}{{ site.baseurl }}/assets/images/uploads/2023-11-09-configure-netlify-on-github.png)
   
1. Scroll down on the pop-up window and add your specific repository from the dropdown or give access to all repositories and press `save`.
   ![Give repository access]({{ site.url }}{{ site.baseurl }}/assets/images/uploads/2023-11-09-give-repository-access.png)

1. Now, you see your repository. Select it.
   ![Select your repository]({{ site.url }}{{ site.baseurl }}/assets/images/uploads/2023-11-09-select-your-repository.jpg)

1. On the next page, we configure deployment settings for the website. The default options populated by Netlify are sufficient. Now, hit on that deploy button.

1. Our website is deployed to netlify sub-domain. Now, Setup a custom domain with Https.
   ![Delpoyed]({{ site.url }}{{ site.baseurl }}/assets/images/uploads/2023-11-09-deployed.jpg)

Everytime you make changes on your website, like adding a new post or configuring a setting.
Commit your changes and push to github(see below commands). 
```bash
git add .
git commit -m "your-commit-message"
git push
```
Netlify will automatically deploy your new changes whenever there's a change in Github repository.

Hope you enjoyed this post. If you have any comments or need help type them below, I'll reply to every single one of them.
