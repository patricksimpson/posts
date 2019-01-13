---
title: "Using Gatsby - Part II"
summary: "Here's my details on using Gatsby specifically GraphQL, deployment and performance."
date: "2017-11-30"
tags: ["blog", "programming"]
---

After a little more experimenting, I've finally landed at a good place with [GatsbyJS][gatsby_link] (Gatsby).  Here's my [blog source][blog_link].

If you haven't already, read the Gatsby [tutorial]. My blog was derived from it.

## GraphQL

[GraphQL][graphql_link] is the key that makes everything come together nicely. I admit, it's not easy to understand at first, and I've only just scratched the surface.

For the purpose of my blog, I am using GraphQL to make queries on the file system. This, Gatsby handles the magic of running the GraphQL server in order for these queries to work.

Here is a file system query, using the [remark] plugin, which helps convert the static assets into usable html... because after all markdown is just text!

```javascript
query IndexQuery {

  // Using allMarkdownRemark from Gatsby plugins.
  // Sorting is passed in as a param here.
  // Here I order DESC on the front matter date.

  allMarkdownRemark(sort: {fields: [frontmatter___date], order: DESC}) {
    totalCount // This I was setup in the gatsby-node.js file.
      edges {
        node {
          id
          // front matter data
          frontmatter {
            title
            date(formatString: "DD MMMM, YYYY")
            summary
          }
          // Slug is generated from the gatsby-node.js file
          fields {
            slug
          }
        }
      }
    }
  }
}
```

So we've stubbed out the data that would be returned to us in the GraphQL query here. In this case, I am grabbing all nodes (files) with `allMarkdownRemark`. Each `node` is a file, with it comes the data.

With it, we can easily map each actual post: `data.allMarkdownRemark.edges.map(({ node }) => ...`

Just a note, gatsby will inject the data via props, so long as you have a grapql query defined. Check out [this file for an example][graphql_file].

## Deployment

For me, I already had a droplet setup with Apache running (this could be nginx or whatever you'd like, apache is just running static assets away).

I use [mina][mina_link] as my deployment and adding this in was no problem at all.

For now the biggest deployment pain point is running `gatsby build` on the server takes about 20-30 seconds. This feels slow to me, but I get it. It's compiling down all of my blog posts and other static assets into a flat file system that can be used **without** javascript.

## Performance

I have a lot of improvements I'd like to make. I think typography is expensive and google doesn't do a great job of caching their static assets (2 hours for a font expires?).

Some improvements could be, async loading non-critical assets (like fonts, other css, etc), also don't include typography by default, it's not fast and should be opt-in.

Other than that, Gatsby is _pretty fast_. Out of the box, there's just not much room for improvement. Here are my [webpage speed test results][webpage_link].

## Issues

One of the things I noticed using `gatsby develop` is the live reloading doesn't always pick up on changes. I am constantly refreshing my page and/or starting stopping the service locally when changes are made to GraphQL queries, updates to the filesystem, and renaming or editing posts.

Another issue I had was all of the extras the default build comes with. I ended up refactoring out [glamor][glamor_link] and [glamorous][glamorous_link] in favor of [classnames], which to me is much better,  at least for now. I do plan on looking into these packages more.

## Outro

All in all, GatsbyJS is excellent. I look forward to improving the performance and helping the community in anyway I can. Give it a shot.

[gatsby_link]: https://www.gatsbyjs.org/
[glamorous_link]: https://github.com/paypal/glamorous
[glamor_link]: https://github.com/threepointone/glamor
[graphql_link]: http://graphql.org/
[mina_link]: http://nadarei.co/mina/
[blog_link]: https://github.com/patricksimpson/blog
[graphql_file]: https://github.com/patricksimpson/blog/blob/master/src/pages/index.js
[webpage_link]: https://www.webpagetest.org/result/171130_8W_ca7c786809960f88123dce649189706a/
[remark]: https://github.com/gatsbyjs/gatsby/tree/master/packages/gatsby-transformer-remark
[classnames]: https://github.com/JedWatson/classnames
[tutorial]: https://www.gatsbyjs.org/tutorial/
