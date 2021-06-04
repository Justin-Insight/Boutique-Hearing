# Quintessence a Hugo Boilerplate With Substance

The [Hugo](https://gohugo.io/) boilerplate we use for our projects.

**Disclaimer** - This boilerplate has been heavily integrated with [Netlify](https://www.netlify.com/), and therefore many features are specific to the Netlify platform and may not work with other hosting providers.

**Disclaimer** - Quintessence is a boilerplate (starter kit) for Hugo projects. It's not a Hugo theme. Check the [theme](#themes) docs for more information.

## Getting Started

To get started, you can either clone the repository, or deploy straight to [Netlify](#deploy-to-netlify). Then run the following commands from the project root:

```
npm install
hugo server

```

Hugo will now spin up a high performing dev server with built-in hot reloading. Open up a content file and make an edit to see your changes immediately take effect.

## File Structure

```
│
└──── /assets                - Source files for assets (SCSS and JS)
│
└──── /content               - Markdown files for all our core pages and blog posts. Site is configured to use page bundles so you will find related page assets such as images saved right in these bundles instead of being saved in the static > images folder.
|
└──── /layouts               - Template files
│   │ 404.html               - 404 Template
│   │ index.headers          - Custom Netlify HTTP headers
│   │ index.redirects        - Custom Netlify redirect rules
│   │ robots.txt             - Template for robots.txt
│   │
│   └──── /_default          - Base templates for list & singular pages
│   │   │ baseof.html        - Base template
│   │   │ list.html          - List/taxonomy template
│   │   │ single.html        - Singular page/post template
│   │
│   └──── /partials          - Partials
│       │ header.html    - Sites primary <header>
│       │ footer.html    - Sites primary <footer>
│   │
│   └──── /static            - Hugo static resources
│
│ .gitignore
│ LICENSE
│ README.md
│ config.toml                - Hugo configuration
│ postcss.config.js          - PostCSS configuration for Hugo Pipes
│ netlify.toml               - Netlify configuration
│ package.json
```

## Adding a Blog Post

This site is built using Netlify CMS as a headless git-based CMS. If you're a developer you'll likely have more fun manually creating your blog files but you also have the flexibiliy to use the CMS.

### Manually create a new post

1. In your code editor navigate to content > blog and create a new folder.

2. Name your folder using your blog post title and in the way you want your URL to be displayed ex. my-new-blog-post Once fully configured, Hugo will then display this post URL as /blog/my-new-blog-post/

3. Create an index.md file

4. Add in your post front matter following the example below. This site is structured to use title, date, image and image_alt

```
---
title: Your Hearing Aid Shopping Guide
date: 2019-11-13T04:13:24.350Z
draft: false
description:
image: shopping-bags.jpg
image_alt: hand holding a number of shopping bags
---
```

### Create a new post using Netlify CMS

1. Navigate to https://boutiquehearing.com/admin/#/ and log in

2. Click on Post in the Collections menu and then click New Post

3. The post fields here are mirrors of the post front matter. Enter in your title, date, draft state, description, image and body. Note: The draft state will be set to true by default, select and turn off to automatically publish your post when you're ready.

4. When ready to publish, simply click the Publish button in the top right corner. Netlify CMS will then create your new folder structure and appropriate markdown file for your post and commit that to your git repo. This will then trigger a new build in Netlify. Give Netlify a minute or two to rebuild your site and then go view your newsly published blog post.

## Deploy to Netlify

This site is hosted with Netlify and built with a continuous deployment to Netlify from GitHub. When you push to github it instantiates a new build on Netlify. Don't know how to use GitHub? Start training.

1. git pull to make sure your local repository is up to date with any code changes

2. Create a new feature branch for the website additions that you are making ex. git checkout -b newFeatureBranchName

3. Add and commit your changes to your new feature branch that you just created

4. Push your commit using git push origin newFeatureBranchName

5. Go to GitHub and click on "branches"

6. Click "New pull request" to open a new pull request for review

7. You can now navigate to Netlify and view your PR in a preview URL using Netlify's Deploy Previews

8. Once your code has been reviewed and your feature branch is merged with the master branch, Netlify will instantiate a new build automatically
