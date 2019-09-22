---
title: 'Building a Website with Hugo (Part 1: Setup and Installation)'
author: 'Sawit Trisirisatayawong'
date: 2019-09-18T21:41:50+07:00
tags:
  - hugo
  - tutorial
  - beginner
categories:
  - webdev
  - tutorial
---
![Person Using MacBook](/images/person-using-macbook.jpg)
<center>*Photo by Glenn Carstens-Peters on Unsplash*</center>
## Introduction

Ever wanted to create a website but don't have enough time to learn all the tools necessary to build, maintain, and optimize one? Or wish making website pages is more like writing a blog? Then Hugo might be what you're looking for. It brings all the benefits of a static site generator - 100% Flexibility, Security, Speed and is used by many companies such as [1Password](https://1password.com), [Kubernetes](https://kubernetes.io), and [the Government of Virginia](https://www.virginia.gov)

## Install the necessary components

To get started, you will need to make sure [Git](github.com), [Hombrew](brew.sh), and [Hugo](gohugo.io) are installed on your system

### Homebrew

Homebrew is a [package manager](https://en.wikipedia.org/wiki/Package_manager) which allows you to install other useful packages and tools onto your Mac. To install, open up your Terminal app by finding it in the Applications folder in Finder or search for it using Spotlight. After opening it up, copy and paste the following command:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Git

With Homebrew installed, run:

```bash
brew install git
git --version #Verify installation
```

Then set your Git username and email with:

```bash
git config --global user.name "Sawit Trisirisatayawong"
git config --global user.email "sawit.tr@gmail.com"
```

Be sure to replace the credentials with your own

### Hugo

Finally, install Hugo with:

```bash
brew install hugo
hugo version #Verify installation
```

If the installation went correctly, you should see something similar to

```bash
❯ hugo version

Hugo Static Site Generator v0.58.1/extended darwin/amd64 BuildDate: unknown
```

<center>*Terminal showing Hugo version*</center>

## Creating the site

### Create project directory and install theme

After completing installation above, navigate to the folder you want to keep your website files in Terminal and run.

```bash
hugo new site samplesite #Replace samplesite with preferred folder name
cd sameplesite
```

Then we can navigate into the folder and install a theme to use. We'll be using [Hello-Friend-Ng](https://themes.gohugo.io/hugo-theme-hello-friend-ng/) here. See [themes.gohugo.io](https://themes.hugo.io) for all available themes.

```bash
# Download the theme
git init
git submodule add https://github.com/rhazdon/hugo-theme-hello-friend-ng.git themes/hello-friend-ng

#[Hugo homepage after adding links to header (your config.toml configuration file
# and add the Ananke theme.
echo 'theme = "hello-friend-ng"' >> config.toml
```

### Adding content

By default Hugo have already created a site with a default homepage, which in our case looks like

![Default Hugo site with hello-world-ng theme](/images/hugo-hello-world-ng-default.png)

But this is looks pretty boring. Let's add some content to it. Create your first post page with

```bash
hugo new posts/my-first-post.md
```

This will create a new page Markdown file called **'my-first-post.md'** in 'samplesite/content/posts'.
Now if you navigate to the folder and open it up it should look like:

```md
---
title: 'My First Post'
date: 2019-09-19T15:34:27+07:00
draft: true
toc: false
images:
tags:
  - untagged
---
```

Edit the file how you want. To add content to it, insert it after the second '- - -' below 'drafts: true'. Note that Hugo pages uses the [Markdown language](https://en.wikipedia.org/wiki/Markdown). Refer to the [Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for how to edit these files.

### Adding links to header

Now that we have the page ready, we need to add links to the header to get to it. We do this by editing the **'config.toml'** file

```toml
 baseURL = "http://example.org/"
 languageCode = "en-us"
 title = "My New Hugo Site"
 theme = 'hello-friend-ng'
 ####Add the lines below####
 [menu]
    [[menu.main]]
     identifier = "home"
     name       = "Home"
     url        = "/"
   [[menu.main]]
     identifier = "posts"
     name       = "Posts"
     url        = "posts/"
```

Once that's complete, we're ready to preview our site!

## Running Hugo server locally

Now if run

```bash
hugo server -D
```

and navigate to http://localhost:1313/, we can see what we've made so far
![Hugo homepage after adding links to header](/images/hugo-friend-ng-first-draft.png)

<center>*Hugo hompage after our edits*</center>

![Hugo posts page](/images/hugo-friend-ng-posts.png)

<center>*Posts page containing our newly created post*</center>

![Hugo posts page](/images/hugo-friend-ng-first-post.png)

<center>*The content of our new post*</center>

## Conclusion and Next Steps

Looking great! In the next part we'll cover each part of the Hugo framework in more detail and how to host it (for free!) so that anyone on the web can access it.
