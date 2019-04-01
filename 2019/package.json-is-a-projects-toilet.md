---
title: "Package.json is a Project's Toilet"
date: "2019-04-01 12:54 PM"
summary: "What is a package.json file anyway? Who was eating all that corn?"
tags: ["blog", "programming", "javascript"]
---

You may be thinking… 💩gross… but hold that thought. It could be really great... or not.
My advice, **the first file you should open when starting to work on an existing project is the package.json file**.
Yes, before the readme. The readme is great and all, but package.json can't lie. Package.json could be a sign of a troubled project.
The package.json tells you the health of a project. (Added a sprinkle of React, a lil’ lodash, it will show up in the package.json, or that corned beef… wait.)

There’s an old adage that says, while interviewing for a company, [go to the bathroom](https://studentloanhero.com/featured/bathroom-job-interview/).
If the bathroom is well kept, that’s a good sign. You can apply this logic to the `package.json` file.
Package.json contains the dependencies for your project and the tasks for you to run (starting, running, etc).
Also, it's decisions on architecture, resources, process, all in a single file. It’s a is a great place to start.

Things look for:

- Too many dependencies the project may have can be a sign of care or a sign of trouble, especially if there are a lot of dependencies that are out of date, or no longer being used. It says “no one has taken the time to careful audit these dependenices”, trouble!

- Too few or non-working tasks may be a sign of trouble as well, again not enough attention to detail...

- Ordered tasks (alphabetically) is a good sign, someone took the time and careful attention to detail to clean that up.

- A project version and clear project description, it would be a good sign this project is well maintained or perhaps just part of a larger system of packages, this is an important detail.

- A repository link. Check for it, ensure it’s in there and active.

- Audit dependencies for security issues, and versions, is this project using tight semvar rules? Can things be updated? When was the last update made here? Again these are signs of decisions being made.

- Does this project get published? Should it be private? This detail should be there as well.

The package.json tells you what you need to know to get started and making an impact on a project.  Check it out, it might just be in need of a cleanup and a toilet brush.

More information on package.json files:

https://npm.github.io/using-pkgs-docs/package-json/the-package-json-file.html
https://npm.github.io/using-pkgs-docs/package-json/using-a-packagejson.html

*This is only semi-satire, but it's still not a bad analogy. But please use your own analogy in that next meeting*.
