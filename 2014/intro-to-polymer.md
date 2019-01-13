---
title: "Intro to Polymer"
summary: "Enter the future, of web components"
date: "2014-11-20"
tags: ["old", "programming"]
---

## What is Polymer?

An opinionated way to embrace the future web component standard (http://www.w3.org/standards/techs/components#w3c_all).

https://www.polymer-project.org/

Big frameworks are doing some form of "web components"

 - Ember.js - http://emberjs.com/
 - Angular.js - https://angularjs.org/

## Why use Polymer?

From hacker news:

When you ask "should I use Polymer", what I hear is, "should I get a jump start on the upcoming future of the web"? Lets be clear here, Mozilla, IE, Chrome etc... are all merging on these technologies.

Object observers, templating, web components etc... are all emerging, Polymer is just one way you can use them now and tie them all together in an opinionated way.

If you don't like it you don't have to use polymer you could just use plain ol JS and achieve the exact same solution, just slightly more verbose and with less support.

https://news.ycombinator.com/item?id=7971847

In other words, if you want to start using web components, Polymer is one way to accomplish it.

## Examples

To run Polymer you'll need polymer, run: `bower install Polymer/polymer`

Import Elements

```html
<link rel="import" href="elements/my-name.html">
```

### Why this is awsome?

A huge benefit is _reusability_ and _shared_ [component libraries](http://customelements.io). For example, Polymer provides [core](https://www.polymer-project.org/docs/elements/core-elements.html)  and [paper](https://www.polymer-project.org/docs/elements/paper-elements.html) elements.

To use it a core element, such as `core-ajax` all I needed to do was run: `bower install Polymer/core-ajax`

```html
<link rel="import" href="../bower_components/polymer/polymer.html">
<link rel="import" href="../bower_components/core-ajax/core-ajax.html">
<polymer-element name="my-name" noscript>
  <template>
    <core-ajax url="http://polymer.dev/twitter.json" auto response="{{res}}"></core-ajax>
    <div> Hello, my name is {{res.name}} </div>
  </template>
</polymer-element>
```

### Reusability

Web compontents promotes reusability, which can give your next project a jump start on framework, structure and [more](http://customelements.io).

Write once, reuse it, time and time again. That's music to my ears.

This is something I am very excited about, and will continue to monitor. For now, here is a list of resources that I have found insanely useful.

## Resources

### Polymer

 - https://www.polymer-project.org/
 - https://www.polymer-project.org/docs/polymer/polymer.html

### Others

 - React.js: http://facebook.github.io/react/
 - X-Tag: http://www.x-tags.org/

### Web Components

 - http://css-tricks.com/modular-future-web-components/
 - http://webcomponents.org/resources/
 - http://w3c.github.io/webcomponents/spec/custom/
 - http://w3c.github.io/webcomponents/spec/shadow/

### What is Shadow DOM?

 - http://webcomponents.org/articles/introduction-to-shadow-dom/
 - http://www.html5rocks.com/en/tutorials/webcomponents/shadowdom/

### Custom Components

 - http://customelements.io/

### Advanced

 - Vulcanize: Inline all your components: https://github.com/polymer/vulcanize
 - Styling Web Components: https://www.polymer-project.org/articles/styling-elements.html
 - Polymer vs X-Tag: http://pascalprecht.github.io/2014/07/21/polymer-vs-x-tag-here-is-the-difference/
 - Polymer + Yeoman: https://www.youtube.com/watch?v=INH_OW4lFSs
