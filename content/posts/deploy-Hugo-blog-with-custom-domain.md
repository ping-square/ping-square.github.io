+++
title = "Deploy a Hugo Powered blog to Github Pages"
date = 2024-09-08T09:31:39-05:00
summary = "How do you get a blog for free along with free hosting..."
description = "This is a step-by-step tutorial that will guide the reader through the proccess of setting up a free blog with free hosting"
draft = false
toc = false
readTime = true
autonumber = false
math = true
tags = ["database", "java"]
showTags = false
hideBackToTop = false
+++
# Introduction
A blog is an amazing way to build your personal brand by sharing the knowledge, that we accumulate every day. Simply put, a blog is an academic paper with a broader audience that allows more flexibility in tone, structure, and writing stylee. This article aims to guide readers to setup a professional blog while not spending a dime.

# What is Hugo
[Hugo](https://gohugo.io/) is one of the most popular open-source static site generator built with the Go programming language, known for its speed and flexibility. Other popular open-source static site generator alternatives include [Jekyll](https://jekyllrb.com/) and [Pelican](https://getpelican.com/), which I will cover in future tutorials.

# Why choose Hugo?
Not everyone is an HTMl programmer, and most people do not want to become one. Hugo allows you to write content using the simple and intuitive [Markdown](https://www.markdownguide.org/) syntax, while it handles the conversion to HTML and publishing to your site. Hugo follows the Go language’s philosophy of simplicity, gentle learning curve and comprehensive documentation.


# Setup Hugo Static Site
depending on the OS (Operating System) you are using, you can follow this [Tutorial](https://gohugo.io/installation/) from the Hugo official website to setup Hugo on your personal machine. On the other hand, To install Hugo on macOS, follow these steps:

#### Step 1: Install Homebrew (if you don't already have it)
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
Now that Hugo is installed, you can create your first static site:

1. Create a new folder where you want to create your Hugo site and move to that folder. In my case, I created a folder called _`project`_
1. Navigate to the folder where you want to create your Hugo site:
   ```bash
   mkdir project     # create the folder
   cd project        # move to the folder created above
   ```
2. Run the command to create a new Hugo site:
   ```bash
   hugo new site my-hugo-site
   ```
   Keep in mind that you can change `my-hugo-site` to any name that best describes what you want.
   ![Alt text for image]( /images/0_image.png )

   This creates a new folder called _`my-hugo-site`_ with the basic structure needed for a Hugo project as listed below.
   ![Alt text for image]( /images/3_image.png )

#### Step 5: Add a Theme (recommended)
[Hugo themes](https://themes.gohugo.io/) are tools you use to give you blog/site the look that you want. Go to https://themes.gohugo.io/ and select your theme. In my case I chose _`PaperMod`_ theme. Then click on the theme to open it and finally click on the **Download** button to open the corresponding page in github which also contains a step-by-step [tutorial](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation) on how _`PaperMod`_ theme should be installed. 

1. Navigate into your new Hugo site:
   ```bash
   cd my-hugo-site
   ```
2. Initialize Git in _`my-hugo-site`_, hence turning it into a local repository.
    ```bash
    git init
    ```
    initializing Git at this stage will make it possible to use the `git submodule` command bellow.
   ![Alt text for image]( /images/first_image.png )

3. Clone the _`PaperMod`_ theme  into the *themes* directory, adding it to your project as a [Git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules).
   ```bash
   git submodule add https://github.com/patrickDjembat/hugo-PaperMod.git themes/PaperMod
   ```
   ![Alt text for image]( /images/2_image.png )

4. Update the site configuration file (`hugo.toml`) to include the theme:
   ```bash
   echo 'theme = "PaperMod"' >> hugo.toml
   ```
   ![Alt text for image]( /images/4_image.png )

   This step initializes the site with a theme that determines the style and layout of your Hugo site. Hugo sites can use various themes available in its theme directory or on GitHub.

#### Step 6: Build and Serve the Hugo Site
1. Run the following command to start a local web server and see preview of your new Hugo site:
   ```bash
   hugo server -D
   ```
   ![Alt text for image]( /images/5_image.png )

2. Open a web browser and go to `http://localhost:1313` to view your site.
   The `hugo server -D` command runs a local web server and automatically reloads the site whenever you make changes. The `-D` flag includes any draft content.
   ![Alt text for image]( /images/6_image.png )
3. publish the site withoud deploying it
```bash
hugo
```

# Move the Site to Github

#### Step7: Create a public repository on github
log into your [github account](https://github.com/)
1. click on on **Repositories** then click on **New repositoy**
2. give a name to your repository. In my case I chose `kareersquare.github.io` where the suffix `github.io` is needed if you intend to publish this site using [github pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages).
3. make your repository public by checking the box.
4. DO not add a README.md file
5. click on **Create Repository** at he bottom of the page.

![Alt text for image]( /images/7_image.png )

#### Step 8: push the static Hugo site (local repository) to the remote repository
1. When you create a new repository on GitHub, you still need to initialize and configure your local project as a Git repository before it can interact with the remote repository (`kareersquare.github.io`). The sequence of commands:
```bash
echo "# ping-square.github.io" >> README.md  # create a README.md file
git init                                     # This initializes a Git repository in your local project directory.
git add README.md                            # This stages the README.md file for a commit
git commit -m "first commit"                 # This creates the first commit in your local Git repository.
```
2. push the static site to the remote repository (`kareersquare.github.io`)
```bash
git branch -M main                                                                  # renames the default branch to main
git remote add origin https://github.com/KareerSquare/kareersquare.github.io.git    # This adds a remote repository (your GitHub repository) to your local Git configuration.
git push -u origin main                                                             # This pushes your local changes to the main branch of the remote repository on GitHub
```
3. If you check all the folders in the remote repository `kareersquare.github.io`, they do not match the files that were created under the local repository (`my-hugo-site`). And the capture below explains why:
![Alt text for image]( /images/8_image.png )
Essentially, there are still files which are untracked. Let's fix that.
```bash
git add .
git commit -m "complete commit of my-hugo-site folder"
git push origin main
```
![Alt text for image]( /images/9_image.png )


# Publish the site through Github page

#### Change the Build and deployment source
1. In the public repository we created earlier, that is `kareersquare.github.io`, click on **Settings**
2. then click on **Pages**.
3. Finally, click on the arrow in front of **Deploy from a branch** and select **Github Actions**.
![Alt text for image]( /images/10_image.png )

#### create a Workflows in your local repository (`my-hugo-site` ) 
1. Create an empty file in your local repository.
```bash
.github/workflows/hugo.yaml
```
2. Copy and paste the YAML below into the file you created. Change the branch name and Hugo version as needed.
```yaml
# Sample workflow for building and deploying a Hugo site to GitHub Pages
name: Deploy Hugo site to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches:
      - main

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

# Default to bash
defaults:
  run:
    shell: bash

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.134.1
    steps:
      - name: Install Hugo CLI
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
          && sudo dpkg -i ${{ runner.temp }}/hugo.deb          
      - name: Install Dart Sass
        run: sudo snap install dart-sass
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
          fetch-depth: 0
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5
      - name: Install Node.js dependencies
        run: "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
      - name: Build with Hugo
        env:
          HUGO_CACHEDIR: ${{ runner.temp }}/hugo_cache
          HUGO_ENVIRONMENT: production
          TZ: America/Los_Angeles
        run: |
          hugo \
            --gc \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"          
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```
3. publish the site withoud deploying it
```bash
hugo
```
4. push the changes to the remote repository
```bash
git add .
git commit -m "complete commit of my-hugo-site folder"
git push origin main
```
5. Verify that the workflow has been deployed to the remote repository
![Alt text for image]( /images/11_image.png )
6. you can verify the site created under `https://kareersquare.github.io/`