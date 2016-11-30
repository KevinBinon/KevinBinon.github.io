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
However since I had zero knowledge about _Jekyll_, I also used [tinypress.co](http://tinypress.co) to have a functional blog in a few seconds.

[Bktid](https://bktid.github.io) mentioned some [experimental setup](http://jekyllrb.com/docs/windows/#installation), which included installing chocolatey and ruby on windows.
I did give it a try and I succeeded!

Now I'm adding posts on my local machine instead of using the editor provided by [tinypress.co](http://tinypress.co).

## Issue(s) I've encountered

### Posts not showing on my home page (locally)

While writing this first post I noticed that my post wasn't shown on my `index.html` (_which contains an overview of posts_) hosted locally but it was shown on the webpage hosted on my GitHub page.

After google-ing I found out that the paginator plugin is [no longer standard in Jekyll 3.x]((https://jekyllrb.com/docs/pagination/)) like it was in Jekyll 2.x.


To fix this you have 2 options:
* Replace paginator with site in the following piece of code in your `index.html`
  ```html
    <div class="posts">
    {&#37; for post in _paginator_.posts &#37;}
    <div class="post">
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