---
title: "Intro to CSS3: Pseudo-classes"
date: "2012-08-17"
summary: "CSS can be fun, really!"
tags: ["old", "programming"]
---

Many of you have probably used a CSS pseudo-class. This “concept” was introduced in early versions of CSS. For example the a:link, a:hover, etc. These class definitions could be applied to a “window.event”. This kind of tool was powerful, and paved the way for more advanced usage of CSS.

In 2011, the W3C released “Selectors Level 3“. This introduced the new concept for pseudo-selectors or pseudo-classes. A pseudo-class is defined as a CSS selector that cannot be accessed or selected using simple element selection or is not within the normal document tree.

A pseudo-class starts off with a : (colon) and optionally contains a value between parentheses. Pseudo-classes (for now) start out with a simple element selection. For example:

 	a:hover { ... }

In this example “a” is the element selector, “:” starts the pseudo-class syntax, “hover” is the pseudo class.

Next, it is important to add that you can combine pseudo-classes together. For instance:

	a:hover:focus { ... }

Which will applies the “…” css to the a hover and focus state.

Pseudo-classes

Now that we have a handle on the pseudo-class syntax, I will now go over some of the most interesting pseudo-class definitions. This won’t be a comprehensive user manual of each pseudo-classes; instead I will try to highlight some of the more useful pseudo-classes.

:last-child (:first-child) This pseudo-class is probably one of the most common pseudo-classes that I use on a regular basis. (first-child was used in CSS2), however these two pseudo-classes help identify the last element child in the current element.

:nth-child — This can be used to target an emlement “n” levels down. So if you want to target the 3rd element in a tree of 12 nodes. You’d use: li.nth-child(3). What’s cool about the nth-child pseudo class is that you can use “n” as a starting point and target multiple elements thereafter. So li.nth-child(2n) would target the even elements, while li.nth-child(2n+1) would target the odd elements. Pretty cool for a quick alternating style!

:target — This one traditionally has been used for anchor tags, but the new specifications are more ambiguous. This is good, but be aware of browser compatibility issues with this pseudo class. You can make some pretty neat “hover state” css styling.

:checked (:selected) — this is primarily used for radio buttons and checkboxes as their “on” state. Use this to apply styles for this state.

:empty — This is used to apply styles to elements that have no content. This could be  used for help style empty nodes (or hide them completely).
For more information on CSS3 psesudo-classes visit the W3C selectors level 3 website. Or you can visit the

following list: http://reference.sitepoint.com/css/css3psuedoclasses
