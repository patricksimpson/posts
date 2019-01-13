---
title: Automation FTW Bust Your Cache
date: "2014-04-08"
summary: "Cache busting won't solve your money problems, but it will clean up those stale CSS and JS files."
tags: ["programming", "old"]
---

*Originally posted on the [Foundry](http://bit.ly/1oJhYFJ) via [Sparkbox](http://seesparkbox.com).*

Have you ever made a change to a CSS or JavaScript file and noticed that you're not seeing updates in the browser?
Well, you might just have a cache problem. A quick way to bust cache is to simply add a query string to the filename. [However, query strings are not the best](http://bjk5.com/post/4918954974/js-css-packaging-to-minimize-requests-and-randomly-evil).

The best way to bust your cache is to use a hash (based on the file's contents) as part of the filename itself to create a file "fingerprint".  Changing the filename of your cached asset (css, js, favicon) files  appears like a new (uncached) file. The server then makes a new request to a fresh (updated) copy of your asset file, which is great: users will get the latest updated assets without having to clear out their cache.

Fingerprinting files is great, but doing that manually is a nightmare.

## Automation FTW
At Sparkbox, we use Grunt (task automater) to build amazing websites. So I combined two grunt tasks, [Bushcaster](https://github.com/stryju/grunt-bushcaster) and [string-replace](https://github.com/erickrdch/grunt-string-replace) for a solution to the cache problem: [Bushcaster-string-replace](https://github.com/patricksimpson/bushcaster-string-replace).

Let's go over the important stuff in the [Gruntfile.coffee](https://github.com/patricksimpson/bushcaster-string-replace/blob/master/Gruntfile.coffee).

### Bushcaster

      grunt.cacheMap = []

You'll need this to store the pattern/replacement object collected in the bushcaster "onComplete" call.

In the Bushcaster options, you'll probably want the noProcess flag.

  noProcess: true

I learned this the hard way. Basically, Grunt was modifying references in the files, which screwed up binary files, like images, favicons, etc. Itâ€™s best just not to â€œprocessâ€ any of the files for now.

### String Replace
The string-replace was the best grunt task that I could find that would accept a pattern/replacement object built in the onComplete step previously.

So all you'll need to do is specify the replacements as that object previously collected in grunt.cacheMap (call it whatever you want).

      options:
        replacements: grunt.cacheMap


#### Note
This repo has a build directory, which will place all the *.html files inside. It's important to know that that might not be the case for the project you're working on. Be careful **NOT** to overwrite your actual source files.

    'string-replace':
          dist:
            files:
              'build/': '*.html' # dest: source

## Wrapping Up
When you have cache busting in place, you can enjoy setting a long [expires](http://httpd.apache.org/docs/2.2/mod/mod_expires.html) to your asset files. We know that fingerprinted assets will always be different, you can then adjust your .htaccess file to allow for longer cacheing times on assets you are busting. [Example](https://gist.github.com/patricksimpson/9509712).

[Our build process (using Assemble and Grunt)](add link to our build process) needed a solution to the cache problem. Using these two Grunt libraries, you have an asset fingerprinting, cache-busting tool for your static site. It's important to add, Ruby on Rails already has cache-busting functionality with the [asset pipeline](http://guides.rubyonrails.org/asset_pipeline.html#what-is-fingerprinting-and-why-should-i-care-questionmark).

So there you have it! This is our solution for now for our static sites. Now that you know, give it a shot. Enjoy busting all the caches!
