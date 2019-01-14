---
title: "Lunr.js Search"
date: "2019-01-13 11:47 PM"
summary: "A little about Lunr.js searching on a static site"
tags: ["javascript", "programming"]
---

Searching posts was always something I wanted to add to my blog, and now,
thanks to [Lunr.js](https://lunrjs.com) it's here.

## Building an index

Indexing my posts wasn't too bad. Since all of my posts are stored in `md` files,
the first step was building a consumable feed for Lunr. Also, I simply piggybacked on the already
complete javascript object `rss`:

    rss.forEach((post) => {
        let doc = {
          "title": post.meta.title,
          "slug": `${post.meta.slug}`,
          "href": `https://patricksimpson.me/posts/${post.meta.slug}`,
          "date": `${post.meta.pubDate}`,
          "postDate": `${post.meta.postDate}`,
          "summary": `${post.meta.summary}`,
          "body": `${post.content}`
        };
        jsonFeed.push(doc);
      });

Next, building up an index was done like this:

    const searchIndex = lunr(function() {
      this.field('title', { boost: 10 });
      this.field('summary', { boost: 5 });
      this.field('body');
      this.ref('href');
      jsonFeed.forEach( doc => {
        store[doc.href] = {
          'title': doc.title,
          'date': doc.postDate
        };
        this.add(doc);
      });
    });
    // Write out the lunr file...
    fs.writeFileSync('build/lunr.json', JSON.stringify({
      index: searchIndex.toJSON(),
      store: store
    }));

You can see both of these files right now if you really want to:

https://patricksimpson.me/index.json and https://patricksimpson.me/lunr.json

## Client side

Now this was a bit tricky at first I admit, it took some trial and error...

My blog is completely static (hosted on S3, see [blog-update](https://patricksimpson.me/posts/blog-update/)). Basically, there is no backend to call, to perform the search function.
The only way this was going to work was with JS. (Which means, search only works for people using JS). Making it a [progressive enhancement](https://en.wikipedia.org/wiki/Progressive_enhancement) (Makes the expirence nicer, but doesn't detract from the content in anyway).

### Search template

First thing, I added a `search` template to my home page. (It's the little form that shows up on botht he home page and the search page).

Next, added the actual `search` landing page. This enabled me to only load `lunr.js` on the search "page", (so you don't waste bandwidth).
Also, providing a new template page, that would work to kick off searches, based on [GET requests](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods). This means, you don't actually
have to interact with the html "form" you can just type any old `?q=blah` in the URL, also provides a perma link for searches. Win-win.

### Search Client

The client side code then performs a search, using Lunr client side JavaScript.

I've provided the entire `search.js` file here on this gist:

https://gist.github.com/patricksimpson/41c8320d40159cc8e9e7fda768437e6b

First, I perform a fetch (of the [lunr.json](https://patricksimpson.me/lunr.json) file mentioned before).

    fetch('/lunr.json').then(function(response) {

[from line 9](https://gist.github.com/patricksimpson/41c8320d40159cc8e9e7fda768437e6b#file-static-search-js-L9)

Then, we need to create the "Lunr" instance index:


    let index = lunr.Index.load(data.index)

[from line 13](https://gist.github.com/patricksimpson/41c8320d40159cc8e9e7fda768437e6b#file-static-search-js-L13)

Passing that along to the "search" method. We'll simply use `search` on Lunr, based on the pre generated `index` in the `lunr.json` file.

    let results = index.search(query.value);

[from line 42](https://gist.github.com/patricksimpson/41c8320d40159cc8e9e7fda768437e6b#file-static-search-js-L42)

The rest is just some simple DOM manipulation, Vola, working static search!

![](http://g.recordit.co/RTKrDJg80U.gif)

## End

Hope you liked this post and the search functionality. If you have questions, feel free to ask me via twitter or email (or mail?).

Lunr was inspired by [Solr](https://lucene.apache.org/solr/), which is a powerful search!

Checkout https://lunrjs.com/ for more information on Lunr search.
