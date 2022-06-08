---
title: Website Basics
author: Michael McCarthy
date: last-modified
categories:
  - tutorials
  - website
---

## How the website works

The OSSSG website is built using [Quarto](https://quarto.org), and the source files for the website are managed on [GitHub](https://github.com). The GitHub repository for the website is located at <https://github.com/Open-Science-Student-Support-Group/osssg-website>.

If you navigate to the GitHub repository you can view the source files for the website. The source files for the website fall into two broad categories:

- Input files
- Output files

**Input files** provide the scaffolding for the website, containing things such as settings for pages, written content, image files, and so forth. **Output files** contain the content that we publish to the web. This content is [rendered by Quarto](https://quarto.org/docs/websites/publishing-websites.html) from the website's input input files, then written to the `_site` directory. The `_site` directory contains the output files for the website (indeed, *it is the website!*); everything else can be thought of as an input file.

We publish the content in the `_site` directory to the web using [Netlify](https://www.netlify.com/), which is integrated with the website's GitHub repository. Whenever a new commit is made on the `main` branch of the GitHub repository, Netlify will publish the content in the `_site` directory to the web.

## Site file structure

The main content for the site is stored in the following files and directories:

- `_quarto.yml` controls site-wide parameters and is where navbar and footer contents are specified
- `_variables.yml` controls site-wide variables, such as the email used in our contact page
- `index.qmd` is the site's home page
- `about`, `contact`, `documents`, `events`, and `news` contain those respective pages for the site
  - `documents`, `events`, and `news` are listing pages
      - The `index.qmd` file in each directory controls parameters for the post listings.
- `404.qmd` is the 404 page for the site
- `styles.css` and `theme.scss` are used for additional CSS and SASS styling for the site's appearance, such as fonts and colours

Other files:

- `_templates` contains templates you can use for creating new posts for the sites various listing pages.     - Please see the `README.md` file inside `_templates` or the [New Post Workflow](/documents/posts/new-post-workflow) document for more information
- `_common` includes files that are common to several pages across the site
    - Please see the `README.md` file inside `_common` for more information
- `_site` contains the files for the rendered site
    - Do not modify anything in this directory directly, it's pointless
        - Whenever you render the site it will be overwritten. 

## Creating and editing content

See the [New Post Workflow](/documents/posts/new-post-workflow) document.

## Learning more about Quarto

Please see the [getting started](https://quarto.org/docs/get-started/) page for installation information, and the Quarto [guide](https://quarto.org/docs/guide/) and [reference](https://quarto.org/docs/reference/) for information on how the site was built and how you can modify it.
