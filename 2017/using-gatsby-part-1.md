---
title: "Using Gatsby - Part I"
date: "2017-11-26"
summary: "Going into some minor details about using GatsbyJS. I talk about my previous attempts and other things."
tags: ["blog", "programming"]
---

## Background

If you know me, you know that I don’t have a great tract record for a blog.
I’ve used [Wordpress](https://wordpress.org/), [Ember](https://emberjs.com), [Ghost](https://ghost.org/), and even [my own crazy hacked blog](https://github.com/patricksimpson/patricksimpson-old-blog).
None of which has worked out for me unfortunately.

### Fast Forward

This is third time I've attempted a [Gatsby](https://www.gatsbyjs.org/) site. First time, was pre [GraphQL](http://graphql.org/), which I actually did get up and running at some point.

My second attempt was _not_ [good](https://github.com/patricksimpson/patrick-blog-gatsby).  It was several days after the initial launch of Gatsby 1.0.0. I joined up the discord chat, filed a bug, but never got it off the ground.


## The New Gatsby

GraphQL is sort of mind bending at first...  With it, you're defining the data structure that you want. The GraphQL engine [takes care of the rest](http://graphql.org/learn/).

GraphQL is also a _server_ running against whatever data you feed it, and with Gatsby (this blog) I am using the filesystem plugin, which means I have access to queries against my filesystem.

I started out following the tutorial of course, but you can check out the code for this blog, it’s a not too far off from the tutorial. I’ve tagged it here.

### Note

Also, what’s cool about Gatsby, It’s doing all this on my local (my development box), I can build/publish without worrying about needing these services, and well that’s all I need for a blog.


## Next Post

I wanted to post everything in here tonight, but I'll split it up. I've got some code to share and of course my ever so priceless commentary.

My next post I want to write about:

  - A simple GraphQL Query and what it means.
  - My deployment method, less friction, more writing.
  - Any gotchas I found while using Gatsby.


Keep up the great work Kyle, it shows.
