---
title: "Conditional Markup, Classes, and Styles"
date: "2012-05-12"
summary: ""
tags: ["old", "programming"]
---

There are many ways to accomplish the same result, as a front-end engineer, I personally know this to be true.  Lately I have been using a new and popular way to display different styles on elements.


In the past, many people included an additional stylesheet based on the browser (IE7.css for IE7 browsers). This method was done by including conditional markup:

    <!--[if IE]>
    <link type="text/css" rel="stylesheet" href="ie.css" />
    <![endif]-->

This old technique, (an hack for IE), will add the code between the “if” only if the the browser is IE. All other browsers will treat this code as a comment.

The new technique, which I personally believe is the absolute cleanest way to have conditional styles applied to old browsers (like IE), is done as follows:

    <!--[if IE 7]><html class="ie7" lang="en"><![endif]-->

This is a much cleaner approach as it allows you to add your styles anywhere.  A style that would only be applied to an IE7 browser would look like this:

    .ie7 a{ position: relative; }

Simple, and clean.

Notice, you are applying a class on the HTML element. This means you will need other conditional styles, including a final HTML tag that will support all other browsers. Be sure you know what your are doing. This new technique include conditional styles has gain popularity thanks to the usage of the HTML5 boilerplate. Please check it out for more information.

Thanks for this, I for one will use this going forward, until of course, the next best thing comes out!
