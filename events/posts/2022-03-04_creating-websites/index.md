---
title: Creating a website with open source software
subtitle: A workshop on creating websites with R Markdown for new and experienced R users.
date: 2022/02/19
categories:
- workshops
---

## Event Details

| __Speaker__: [Michael McCarthy](https://michaelmccarthy.tidytales.ca)
| __Date and Time__: March 4, 2022, from 4:00 PM to 6:00 PM 
| __Location__: University of Calgary

::: {.tool}
<a href="https://github.com/mccarthy-m-g/osssg-website-workshop" role="button" class="btn btn-outline-dark">
<i class="fab fa-github"></i>
Materials
</a>
:::

A website is a wonderful place for showcasing yourself, mobilizing knowledge in your learning community, building an online portfolio, or anything else you can imagine! Thanks to the power of open source software, creating a stylish website is quick, easy, and free. No programming experience required.

In this workshop we will explore open source tools and workflows for creating and deploying websites. By the end of the workshop you will have your very own website up and running on the web; bring a picture and bio so you can begin to customize your site!

We will focus on three types of websites for this workshop, discussing their differences and the pros and cons of each approach:

-   Single page sites
-   Multipage sites
-   Blogs

## Before the workshop

To prepare for this workshop, please do the following.

**Create a GitHub account**: GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere. Create an account at <https://github.com>.

**Sign up for Netlify using your GitHub account**: Netlify is a platform for hosting and deploying static websites whose source files are stored on GitHub. Sign up at <https://app.netlify.com/signup>.

**Install GitHub Desktop**: GitHub Desktop is is an application that enables you to interact with GitHub using a GUI instead of the command line or a web browser. Download and install it from <https://desktop.github.com>.

**Install R**: R can be downloaded from CRAN (the comprehensive R archive network) using the following link <https://cloud.r-project.org>. A new major version of R comes out once a year, and there are 2-3 minor releases each year.

**Install RStudio**: RStudio is an integrated development environment, or IDE, for R. Download and install it from <http://www.rstudio.com/download>. RStudio is updated a couple of times a year. When a new version is available, RStudio will let you know. It's a good idea to upgrade regularly so you can take advantage of the latest and greatest features.

## During the workshop

We will be exploring three R packages---[postcards](https://github.com/seankross/postcards), [distill](https://rstudio.github.io/distill/), and [blogdown](https://pkgs.rstudio.com/blogdown/)---that can be used to build a website. To install these packages, run the following in the R console.

```r
install.packages(c("postcards", "distill", "blogdown"))
```

Each of these packages come with a function to build the basic skeleton for a website, which you can then fill out, add on to, and customize to make the site your own.

```r
# Create a postcards website
postcards::create_postcard()

# Create a distill website or blog
distill::create_website()
distill::create_blog()

# Create a Hugo website or blog
blogdown::new_site()
```

## After the workshop

The R community has made great resources on building and customizing websites with the packages we explored today. Check them out!

### General resources

- [Building a blog with R](https://youtu.be/MrW5XFf7aps)
- [How to Get Your Materials Online With R Markdown](https://youtu.be/QcE4RBH2auQ)

### Distill resources

- [Distill for R Markdown](https://rstudio.github.io/distill/)
- [Building a blog with distill](https://themockup.blog/posts/2020-08-01-building-a-blog-with-distill/)
- [The distillery](https://distillery.rbind.io/)

### Blogdown resources

- [blogdown: Creating websites with R Markdown](https://bookdown.org/yihui/blogdown/)
- [Hugo Themes](https://themes.gohugo.io/)
- [A blogdown new post workflow with Github and Netlify](https://www.garrickadenbuie.com/blog/blogdown-netlify-new-post-workflow/)
- [Up & running with blogdown in 2021](https://www.apreshill.com/blog/2020-12-new-year-new-blogdown/)
