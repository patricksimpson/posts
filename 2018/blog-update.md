---
title: "Blog Update"
date: "2018-12-29 5:21 PM"
summary: "A small little update on my blog progress."
tags: ["blog", "personal", "programming"]
---

The holiday break is almost over already and of course I found very little time to work on any of my little side projects... suprise!

## Why Blog Anyway?

I believe in blogging. It may not be obvious from my lack of posts, but having it there is important.

My "new and improved" blog is really just about removing all barriers to just writing posts.
Some may say "that's easy, just install wordpress" or "just write on medium". There in lies
a problem for me. Medium, I don't really own the content. Also Medium could just up and
vanish, then what? Wordpress... I went down that route before and though I'd rather
use Wordpress over Medium, Wordpress requires you to run a server. I wanted to remove
that from the equation. That way, my hosting requirements are next to nothing.

## What's New?

Simple, effective.

    build.js

It's a small little script that compiles my templates and posts into static html, I will post an update on this later.

### Markdown

Posts are just markdown files. I've opted to use [front-matter](https://github.com/jxson/front-matter), even though I dislike it's formatting. It does make it much simplier to
edit posts in a single file.

### EJS Templates

Templating is done using [EJS](https://ejs.co/). I've come to really like EJS and find it to be really
easy to work with. It's "just javascript" and is very easy to compile into static html.

### S3 Hosting

Setting up S3 push locally:

    aws s3 cp build/ s3:patricksimpson.me/ --recursive

Pushes the entire `build` directory to S3. That's it.

## What's next?

### CI Publishing

I want to be able to publish from anywhere, not just my computer using S3 push. I plan
 on having my CI automatically publish to S3 whenever I commit a new post.

### RSS and Micro Blog

I believe if you blog, you should be using RSS! Hooking up with shouldn't be to hard once I have RSS.

### Photos

Adding photos can really add value to the blog. Of course I could easily embed images
using Markdown, but there's no real good (easy) way to add them from my phone to this blog.
