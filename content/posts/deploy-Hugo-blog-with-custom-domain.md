+++
title = "Deploy a Hugo Powered blog to Github Pages and publish on a custom domain"
date = 2024-09-08T09:31:39-05:00
summary = "How to deploy a blog Powered by Hugo to Github Pages With a custom domain hosted on Goddady.com"
description = "This is a step-by-step tutorial that will guide the reader through the proccess of installing a blog for free and publishing it on a custom website."
draft = false
toc = true
readTime = true
autonumber = true
math = true
tags = ["database", "java"]
showTags = false
hideBackToTop = false
+++
# Introduction
A blog is an amazing way to build your personal brand by sharing the knowledge, that we accumulate every day. Simply put, a blog is an academic paper with a broader audience and allows more flexibility in tone, structure, and writing stylee. This article aims to guide readers to build a static site on their local machine, then upload it to Github to finally publish it on a custom domain.

# What is Hugo
[Hugo](https://gohugo.io/) is one of the most popular open-source static site generator built with the Go programming language, known for its speed and flexibility. Other popular open-source static site generator alternatives include [Jekyll](https://jekyllrb.com/) and [Pelican](https://getpelican.com/), which I will be covered in future tutorials.

# Why choose Hugo?
Not everyone is an HTMl programmer, and most people do not want to become one. It allows you to write content using the simple and intuitive [Markdown](https://www.markdownguide.org/) syntax, while Hugo handles the conversion to HTML and publishing to your site. Hugo follows the Go language’s philosophy of simplicity, offering a gentle learning curve and comprehensive documentation. In this tutorial, I will explain why Hugo is a great choice for building a free blog.


# Setup Hugo Static Site
depending on the OS (Operating System) you are using, you can follow this [Tutorial](https://gohugo.io/installation/) from the Hugo official website to setup Hugo on your personal machine. On the other hand, To install Hugo on macOS, follow these steps:

<details>
  <summary>Step 1: Install Homebrew (if you don't already have it)</summary>
[Homebrew](https://brew.sh/) is a package manager for macOS, and it simplifies the installation of software.

1. Open the **Terminal** (you can find it using Spotlight search or in `Applications > Utilities > Terminal`).
2. Install Homebrew by running this command:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
3. After the installation completes, follow the instructions that appear in the Terminal to add Homebrew to your system's `PATH`.

   This typically involves running:
   ```bash
   echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
   eval "$(/opt/homebrew/bin/brew shellenv)"
   ```
   Homebrew allows you to easily install and manage software on macOS, and this step ensures it's properly configured for future installations.
</details>

#### Step 2: Install Hugo via Homebrew
1. Run the following command in the Terminal to install Hugo:
   ```bash
   brew install hugo
   ```
   This command tells Homebrew to download and install Hugo. Homebrew fetches the latest version of Hugo and installs it in the appropriate location.

#### Step 3: Verify the Installation
1. After installation, check that Hugo is installed correctly by running:
   ```bash
   hugo version
   ```
   This verifies that Hugo is installed and gives you the version number, confirming that everything is set up properly.

#### Step 4: Create a New Hugo Site
Now that Hugo is installed, you can create your first site:

1. Create a new folder where you want to create your Hugo site and move to that folder. In my case, I created a folder called _`project`_
1. Navigate to the folder where you want to create your Hugo site:
   ```bash
   mkdir project
   cd project
   ```
2. Run the command to create a new Hugo site:
   ```bash
   hugo new site my-hugo-site
   ```

   This creates a new folder called _`my-hugo-site`_ with the basic structure needed for a Hugo project.
    ```bash
    ls -l my-hugo-site
        total 8
        drwxr-xr-x@ 3 dtp  staff  96 Sep  8 14:22 archetypes
        drwxr-xr-x@ 2 dtp  staff  64 Sep  8 14:22 assets
        drwxr-xr-x@ 2 dtp  staff  64 Sep  8 14:22 content
        drwxr-xr-x@ 2 dtp  staff  64 Sep  8 14:22 data
        -rw-r--r--@ 1 dtp  staff  83 Sep  8 14:22 hugo.toml
        drwxr-xr-x@ 2 dtp  staff  64 Sep  8 14:22 i18n
        drwxr-xr-x@ 2 dtp  staff  64 Sep  8 14:22 layouts
        drwxr-xr-x@ 2 dtp  staff  64 Sep  8 14:22 static
        drwxr-xr-x@ 2 dtp  staff  64 Sep  8 14:22 themes
    ```

#### Step 5: Add a Theme (Optional but recommended)
Hugo uses themes to style your site. You can add one by following these steps:

[Hugo themes](https://themes.gohugo.io/) are designed to give various style to your blog. Go to https://themes.gohugo.io/ and select your theme. In my case I chose _`PaperMod`_ theme. Then click on the theme to open it and finally click on the **Download** button to open the corresponding page in github containing a step-by-step [tutorial](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation) on how _`PaperMod`_ theme should be installed. 

1. Navigate into your new Hugo site:
   ```bash
   cd my-hugo-site
   ```
2. Initialize an empty Git repository in the current directory (_`my-hugo-site`_).
    ```bash
    git init
    ```
    [Alt Text](assets/img/first_image.png)

3. Clone the _`PaperMod`_ theme  into the *themes* directory, adding it to your project as a [Git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules).
   ```bash
   git submodule add https://github.com/patrickDjembat/hugo-PaperMod.git themes/PaperMod
   ```
4. Update the site configuration file (`hugo.toml`) to include the theme:
   ```bash
   echo 'theme = "PaperMod"' >> hugo.toml
   ```

   This step initializes the site with a theme that determines the style and layout of your Hugo site. Hugo sites can use various themes available in its theme directory or on GitHub.

#### Step 6: Build and Serve the Hugo Site
1. Run the following command to start a local server and see your new Hugo site:
   ```bash
   hugo server -D
   ```

2. Open a web browser and go to `http://localhost:1313` to view your site.
   The `hugo server` command runs a local web server and automatically reloads the site whenever you make changes. The `-D` flag includes any draft content.

----------






# Move the Site to Github

# Publish to a custom domain


<details>
  <summary>Click to expand</summary>

  This is a detailed explanation that will only be visible when the section is expanded. 

  - You can format text in **bold** or *italic*.
  - You can also include links, images, or code blocks.

</details>
