---
title: New Post Workflow
author: Michael McCarthy
date: last-modified
categories:
  - tutorials
  - website
---

## What you'll learn

This document will guide you through the process of making new posts on our website. Here the term `post` refers to any page on the website that is collected under a [listing page](https://quarto.org/docs/websites/website-listings.html). For example, this document is a post that is collected under the `documents` listing page. The listing pages for this website include:

- `documents`
- `events`
- `news`

You can make new posts under any of these listing pages following the workflow described in this document.

::: {.callout-note}
You can also follow the general workflow described in this document to make other changes to the website.
:::

## How the website works

The OSSSG website is built using [Quarto](https://quarto.org), and the source files for the website are managed on [GitHub](https://github.com). The GitHub repository for the website is located at <https://github.com/Open-Science-Student-Support-Group/osssg-website>.

If you navigate to the GitHub repository you can view the source files for the website. The source files for the website fall into two broad categories:

- Input files
- Output files

**Input files** provide the scaffolding for the website, containing things such as settings for pages, written content, image files, and so forth. **Output files** contain the content that we publish to the web. This content is [rendered by Quarto](https://quarto.org/docs/websites/publishing-websites.html) from the website's input input files, then written to the `_site` directory. The `_site` directory contains the output files for the website (indeed, *it is the website!*); everything else can be thought of as an input file.

We publish the content in the `_site` directory to the web using [Netlify](https://www.netlify.com/), which is integrated with the website's GitHub repository. Whenever a new commit is made on the `main` branch of the GitHub repository, Netlify will publish the content in the `_site` directory to the web.

Thus, the basic new post workflow involves:

1. Creating an input file for the new post
2. Rendering the site to update the `_site` directory to include the new post
3. Committing the input file and `_site` directory to the `main` branch of the GitHub repository to publish the new post to the web

The remainder of this document guides you through this process.

## Prerequisites

### Set up Quarto

For creating and rendering new posts you will need to: 

- Install [Quarto](https://quarto.org/docs/get-started/)
- Install an editor to use with Quarto

There are several editors you can use with Quarto. We recommend one of the following.

::: {.panel-tabset}
#### RStudio (Recommended)

Install [RStudio](https://www.rstudio.com/products/rstudio/download/#download)

Optionally: Read the *Hello, Quarto* [RStudio tutorial](https://quarto.org/docs/get-started/hello/rstudio.html). Note that if you want to run this tutorial yourself you will need to [install R](https://cloud.r-project.org/) and the R packages used in the tutorial. However, you **do not** need to install R to work on our website.

#### Visual Studio Code

Install:

- [Visual Studio Code](https://code.visualstudio.com/download)
- The [Quarto VS Code Extension](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)

Optionally: Read the *Hello, Quarto* [VS Code tutorial](https://quarto.org/docs/get-started/hello/vscode.html). Note that if you want to run this tutorial yourself you will need to install the Python packages used in the tutorial. However, you **do not** need to install Python to work on our website.
:::

### Set up GitHub

For committing files to the website's GitHub repository you will need:

- A [GitHub account](https://github.com)
- A way to connect your local computer to GitHub 

There are many ways to connect your local computer to GitHub. We recommend one of the following.

::: {.panel-tabset}
#### GitHub Desktop

Install [GitHub Desktop]((https://desktop.github.com))

::: {.callout-note}
We recommend this option if you've never used Git or GitHub before.
:::

#### RStudio

Set up RStudio's [built-in Git support](https://happygitwithr.com/rstudio-git-github.html)

::: {.callout-note}
We recommend this option if you already use Git, GitHub, and RStudio for other work. It's especially nice when used in tandem with the [`usethis`](https://usethis.r-lib.org) R package and its [GitHub helpers](https://usethis.r-lib.org/articles/git-credentials.html) and [Pull Request helpers](https://usethis.r-lib.org/articles/pr-functions.html).
:::

#### VS Code

Set up VS Code's [built-in Git support](https://code.visualstudio.com/docs/editor/github)

::: {.callout-note}
We recommend this option if you already use Git, GitHub, and VS Code for other work.
:::

#### Command line

If you're considering this, you don't need our help. :sunglasses:
:::

### Clone the website repository

After you've Set up Quarto and GitHub you can [clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) the website's GitHub repository to your computer. If you have write privileges for the repository then you can clone the site directly; if you don't then you will have to [fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) the repository and then clone your forked GitHub repository to your computer.

The steps to do this are a little different depending on the method you chose to connect your local computer to GitHub in the previous section. Make sure you note where you clone the website respository to on your computer so you can find it later!

::: {.panel-tabset}
#### GitHub Desktop

Follow the [cloning and forking instructions](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-and-forking-repositories-from-github-desktop). The URL for our website's repository is:

```default
https://github.com/Open-Science-Student-Support-Group/osssg-website
```

#### RStudio (built-in Git)

If you do not have write privileges for the repository, first fork it on GitHub, then copy the URL of your fork and complete the steps below. If you do have write privileges, then copy the URL for our website's repository and complete the steps below.

```default
https://github.com/Open-Science-Student-Support-Group/osssg-website
```

1. Open RStudio
2. Create a New Project (from the Project of File menu)
3. Choose to create a new project from Version Control
4. Choose Git
5. Provide the (forked) repository URL then click Create Project

#### RStudio (usethis)

Follow the [pull request helpers](https://usethis.r-lib.org/articles/pr-functions.html) instructions.

#### VS Code (built-in Git)

If you do not have write privileges for the repository, first fork it on GitHub, then copy the URL of your fork and follow the [setting up a repository instructions](https://code.visualstudio.com/docs/editor/github#_setting-up-a-repository). If you do have write privileges, then copy the URL for our website's repository and follow the setting up a repository instructions.

```default
https://github.com/Open-Science-Student-Support-Group/osssg-website
```
:::

## Starting up

### Opening the project

With the prerequisites complete, you are ready to work on the website. The method to open the project depends on the editor you chose.

::: {.panel-tabset}
#### RStudio

Double-click the `osssg-website.Rproj` file located in the root directory of the project. This will start an RStudio session for the project.

#### Visual Studio Code

Open VS Code, then open the project's folder inside VS Code, following the instructions [here](https://code.visualstudio.com/docs/editor/workspaces). This will start a VS Code workspace for the project.
:::

### Previewing the site

After opening the site you can open a live-reloading development server on your computer to preview the website while you work on it. Start the server by running the following in the terminal of RStudio or VS Code:

```default
quarto preview
```

The development server will automatically re-render input files whenever they change. For more details see the Quarto [website workflow documentation](https://quarto.org/docs/websites/index.html#workflow), and the sections on previewing with [RStudio](https://quarto.org/docs/tools/rstudio.html#render-and-preview) and [VS Code](https://quarto.org/docs/tools/vscode.html#render-and-preview).

## The workflow

There are five steps to the new post workflow. The sections below will take you through each step.

### 1. Create a new GitHub branch

First you'll want to create a new branch that you can work on your changes in.

::: {.panel-tabset}
#### GitHub Desktop

Follow the [creating a branch](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/managing-branches#creating-a-branch) instructions.

#### RStudio (built-in Git)

Go to the (forked) website repository in your browser and [create a new branch](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository). Give the branch an informative name such as `post_new-post-workflow`.

Now do the following in RStudio:

1. Go to the Git tab
2. Click the Pull button in the Git tab
3. In the upper right corner of the Git tab, click `main`, then switch to the branch you created

#### RStudio (usethis)

Follow the [pull request helpers](https://usethis.r-lib.org/articles/pr-functions.html) instructions.

#### VS Code (built-in Git)

See the [branches and tags](https://code.visualstudio.com/docs/editor/versioncontrol#_branches-and-tags) section for instructions on creating a new branch.
:::

### 2. Create a new post

The `_templates` directory at the root of the project contains templates you can use to create a new post. Currently there are two templates:

::: {.panel-tabset}
#### Event post template

The event post template is named `1999-01-24_event-post`. This name will be used for the post in its URL on the site.

Modifying the template for new posts:

1. Copy the `1999-01-24_event-post` directory into the `/events/posts/` directory
2. Rename the `1999-01-24_event-post` directory with the appropriate post date and event name
3. Open the `1999-01-24_event-post/index.md` file, edit and modify as needed

::: {.callout-warning}
When renaming the post's directory, follow the formatting used in the template (i.e., `data_post-name`). This keeps the posts organized and easy to parse. Do not include spaces anywhere in the name, only underscores (which should separate the date and post name) and hyphens (which take the place of spaces) are allowed.
:::

#### Generic post template

The generic post template is named `2000-11-18_generic-post`. This name will be used for the post in its URL on the site.

Modifying the template for new posts:

1. Copy the `2000-11-18_generic-post` directory into the `/posts/` directory for the listing page you want to make a post in (e.g., `news` or `documents`)
2. Rename the `1999-01-24_event-post` directory with the appropriate post date and post name
3. Open the `2000-11-18_generic-post/index.md` file, edit and modify as needed

::: {.callout-warning}
When renaming the post's directory, follow the formatting used in the template (i.e., `data_post-name`). This keeps the posts organized and easy to parse. Do not include spaces anywhere in the name, only underscores (which should separate the date and post name) and hyphens (which take the place of spaces) are allowed.
:::

:::

### 3. Author your new post

Once you have copied the template for the new post to the listing page you want you can start editing the input file for the post. This is the `index.md` file located inside the directory for the post. Do not rename this file.

Please see the [Markdown basics](https://quarto.org/docs/authoring/markdown-basics.html) page under the Authoring section in the Quarto [Guide](https://quarto.org/docs/guide/) for details on writing in Markdown, and the Websites section under the guide for website-specific concerns.

If you want to add icons or emojis to your post, see:

- [FontAwesome icons](https://fontawesome.com/v5/search?m=free)
- [Markdown emoji guide](https://gist.github.com/rxaviers/7360908)

::: {.callout-note}
If you are adding files to your post, such as images, try to reduce the size of the files if you can (e.g., by using image compression/optimization). Large files cause pages to load slower.
:::

### 4. Commit and push your changes

When you are happy with your new post, run the following command in the RStudio or VS Code terminal:

```default
quarto render
```

This will render all the output files for the site, including your new post. Now you’re ready to commit these changes to your branch. You’ll want to commit the following changes at minimum:

- The input file for your new post
- Any additional files your new post relies on (e.g., images)
- Everything in the `_site` directory

For your commit message, choose something informative such as “Add ‘new post workflow’ post under documents”, replacing certain parts here with details relevant to your own post.

::: {.panel-tabset}
#### GitHub Desktop

See the [reviewing and committing changes to your project](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/committing-and-reviewing-changes-to-your-project) guide for instructions.

#### RStudio (built-in Git)

In the Git pane:

1. Check all the files you want to commit
2. Click the Commit button to open the commit pane
3. Write your commit message
4. Click the Commit button in the commit pane
5. Click the Push button

::: {.callout-note}
In the commit pane:

- A yellow box indicates a file that hasn’t been committed before
- A blue box indicates a file that is being modified
- A red box indicates a file that is being deleted
- A purple box indicates a file that had been relocated or renamed
:::

#### RStudio (usethis)

In the Git pane:

1. Check all the files you want to commit
2. Click the Commit button to open the commit pane
3. Write your commit message
4. Click the Commit button in the commit pane
5. Follow the [submit pull request](https://usethis.r-lib.org/articles/pr-functions.html#submit-pull-request) instructions

::: {.callout-note}
In the commit pane:

- A yellow box indicates a file that hasn’t been committed before
- A blue box indicates a file that is being modified
- A red box indicates a file that is being deleted
- A purple box indicates a file that had been relocated or renamed
:::

#### VS Code (built-in Git)

Follow the [commit](https://code.visualstudio.com/docs/editor/versioncontrol#_commit) instructions, then Push your changes after committing them.

:::

### 5. Submit a Pull Request

Once you have committed your changes to your new post branch, you can create a pull request to add these changes to the `main` branch of our website’s GitHub repository. 

After you create the pull request, Netlify will create a [Deploy Preview](https://docs.netlify.com/site-deploys/deploy-previews/) that you and your reviewer can use to preview your changes to the site before publishing them to production.

::: {.panel-tabset}
#### GitHub Desktop

Follow the [creating a pull request](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/working-with-your-remote-repository-on-github-or-github-enterprise/creating-an-issue-or-pull-request#creating-a-pull-request) instructions.

#### RStudio (built-in Git)

Follow the [creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) instructions.

#### RStudio (usethis)

Follow the [pull request helpers](https://usethis.r-lib.org/articles/pr-functions.html) instructions

#### VS Code (built-in Git)

Follow the [creating pull requests](https://code.visualstudio.com/docs/editor/github#_creating-pull-requests) instructions
:::

## Cleaning up

If you forked our GitHub repository to make a new post, after your Pull Request is merged into the `main` branch of our GitHub repository you will want to clean up your fork. You have two options here:

- Delete your forked repository
- Delete the branch in your forked repository

The first option is better if you don’t plan to post again on our site. The second option is better if you do plan to post again on our new site since it means less work for your next post.

## Your next post

If you deleted your forked repository, then simply repeat the steps in this guide all over again starting from the [Clone the website repository](#clone-the-website-repository) section.

If you kept your forked repository and just deleted the branch you made in it, first [Fetch the upstream changes](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork) from the `main` branch of our website's repository, then repeat the steps in this guide starting from the [workflow](#the-workflow) section.

## Resources

- [GitHub Learning Resources](https://docs.github.com/en/get-started/quickstart/git-and-github-learning-resources)
- [Deploy previews with Netlify](https://www.pipinghotdata.com/posts/2021-04-01-deploy-previews-with-netlifly/)
- [Pull Request Flow with usethis](https://www.garrickadenbuie.com/blog/pull-request-flow-usethis/?interactive=1&steps=)

