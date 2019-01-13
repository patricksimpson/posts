---
title: "Progressive Enhancement vs. Graceful Degradation"
date: "2011-03-04"
summary: "All about progressive enhancement..."
tags: ["old", "programming"]
---

Progressive Enhancement (PE) is the opposite of Graceful Degradation (GD).

PE works by putting focus on the core “working” features, before adding all the fancy stuff, like CSS and JavaScript. PE starts by making things work, without additional features.


GD works by creating core functionality work with all the fanciness, CSS and JavaScript, then add in the parts that would break (fail) in the case that something would not work for some users.

PE: Start small, build up. GD: Start big, fall down.

PE: Enhance after. GD: Enhance first.

While I would like to say that both of these options are “acceptable”, PE should be the preferred choice. If you start small, enhance after, you ensure that all of your users will have basic functionality, expanding your availability. GD, on the other hand, starts big with many features and JavaScripts which sets the bar high. While it is nice to consider those failing situations (e.g. JavaScript is turned off, browser lacks support) you might miss something.

So in my opinion: Go with progressive enhancement.

Nate Koechley made all of these points in his [video](http://video.yahoo.com/watch/4671445/12486762). I am not trying to sell this as my own idea, but merely what I believe is the right idea.
