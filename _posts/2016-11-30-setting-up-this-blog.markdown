---
published: true
title: Setting up this blog
layout: post
---

## How I did became aware of GitHub pages

2 weeks ago I heard about the GitHub project GitHub Pages. This project hosts a static website bound to your GitHub account build and served by [Jekyll](https://jekyllrb.com).

My colleague [bktid](https://bktid.github.io) posted about his adventure and how he did his setup.


## Steps I took to create this blog

After talking with [sch3lp](https://sch3lp.github.io) I figured out that setting up my own blog shouldn't be that hard.
However since I had zero knowledge about _Jekyll_, I used [tinypress.co](http://tinypress.co) to have a functional blog in a few seconds.
[Tinypress.co](http://tinypress.co) provides a web-interfaces which integrates with your GitHub-repo. It also offers a CRUD to manage your own posts on your GitHub page.

I only used [tinypress.co](http://tinypress.co) for the initialisation of this blog. Since I like to have more insights on how _Jekyll_ works, I removed the integration from [tinypress.co](http://tinypress.co). Now I'm adding posts on my local machine and pushing it to my git-repo first instead of using the editor provided by [tinypress.co](http://tinypress.co).

[Bktid](https://bktid.github.io) mentioned some [experimental setup](http://jekyllrb.com/docs/windows/#installation), which included installing chocolatey and ruby on windows.
I did give it a try and I succeeded! Seems it wasn't the `technical mumbojumbo` like I thought it would be.



## Issue(s) I've encountered

### Posts not showing on my home page (locally)

While writing this first post I noticed that my post wasn't shown on my `index.html` (_which contains an overview of posts_) hosted locally but it was shown on the webpage hosted on my GitHub page.

After google-ing I found out that the paginator plugin is [no longer standard in Jekyll 3.x]((https://jekyllrb.com/docs/pagination/)) like it was in Jekyll 2.x.


To fix this you have 2 options:
 * Replace paginator with site in the following piece of code in your `index.html`

   ```
    for post in paginator.posts
   ```

 * Add the following line to your `_config.yml`

   ```
   gems: [jekyll-paginate]
   ```

   And install the gem with ruby

   ```
   gem install jekyll-paginate
   ```

Since I want to work with pagination I modified my `_config.yml` and installed the gem.

_Kudos to GitHub Pages and Jekyll_

[![](githubpages.png)](https://pages.github.com/) [![](jekyll.png)](https://jekyllrb.com)