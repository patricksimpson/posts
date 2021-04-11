---
title: "The Need for Speed"
date: "2021-04-11 12:50 PM"
summary: "Speed is the killer feature, then why are we slowing things down with all these files? How can we improve modern web development?"
tags: ["blog", "software", "random", "javascript", "rails", "servers"]
---

As modern web development continues to beat the drum of the JavaScript Single Page Application (SPA), where it’s common to include huge file sizes. 
With each file size increases the time it takes to load your page. We even have tricks to reduce the sizes of these pages, increasing the use of frontend building tools, further increasing 
tech debt and complexity. While it’s true you can certainly create a “really fast”, “slick” Single Page Application (no subsequent loading, sorta, we can talk about all those async requests you’re making later). 
You are bloating not only page size, but the cognitive load (tech debt) of the engineer. 

I am not against all JavaScript SPAs, but I am against using them when they are not appropriate. 
If the software architecture is not mature enough to support 2x the pull requests on a fairly frequent basis. 
The amount of drift the frontend will experience, requires at least 2x the work to maintain. It’s tech debt which will eventually bankrupt your time with updates.
It may not be the silver bullet you’re looking for.

An insanely low-fi website and proper caching, you can reduce your page weight next to nothing, and page reload is insanely fast, if noticeable at all. 
While a SPA might seem like the gold standard in web development, I’d much prefer a solid software architecture, with lightweight (server side) HTML/CSS backed pages, 
to a broken, incomplete and lacking (basic links) frontend application. Sprinkle in some JS as needed. 

### Inspiration

- https://twitter.com/HenrikJoreteg/status/1379871612879597568?s=20
- Speed is the killer feature: https://bdickason.com/posts/speed-is-the-killer-feature/ 
- Best practices for SQL: https://www.metabase.com/learn/building-analytics/sql-templates/sql-best-practices
- Micro Frontends: https://martinfowler.com/articles/micro-frontends.html

