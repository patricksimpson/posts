---
title: "Unit Tests Worth It?"
summary: "Thinking about how unit tests hold up over time. What is the true value of unit tests?"
date: "2017-12-02"
tags: ["programming", "javascript", "testing"]
---

This [interesting article][medium] about the value of unit tests has me thinking;  what is the real value in unit tests?

I believe unit tests produce value to developers, but what about beyond that? Can we justify the cost beyond initial development to a business? When a project has reached maintenance, are unit tests actually worth maintaining?

Think of unit tests more as a debugging tool, not a metric to abide by. Code coverage  might be a red herring... A project could have 100% code coverage and still have plenty of bugs and edge cases you never dreamed of. Also, just to point out, that tests themselves are code which could have bugs or missing features just as much as any other code.

I believe the end user cares about the *features* of the system. Developers should place more focus on _integration tests_ as well as _end-to-end tests_ for maximum feature coverage.

The article "[Why Most Unit Testing is Waste][long]" cited in the Medium article is pretty long, but there's a lot of good stuff in there; check it out.

[medium]: https://medium.com/pacroy/why-most-unit-testing-is-waste-tests-dont-improve-quality-developers-do-47a8584f79ab
[long]: https://rbcs-us.com/documents/Why-Most-Unit-Testing-is-Waste.pdf
