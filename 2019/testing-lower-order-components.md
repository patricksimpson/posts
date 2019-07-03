---
title: "Testing Lower Order Components"
date: "2019-07-02 10:12 PM"
summary: "Testing components wrapped in HOCs can be annoying; Just don't do it."
tags: ["javascript", "react", "programming", "blog"]
---

[Higher Order Components](https://reactjs.org/docs/higher-order-components.html) (HOCs) are one of those “gotcha”’s in React that confuse and irritate even seasoned of engineers. While I realize React Hooks is some kind of mircle sent forth from the ether... HOCs are still being widely used in older codebases, so chill.

When testing a component wrapped in HOCs, the best way I have found, make it a “simple” component. Just export a non-wrapped component as well as the wrapped component.

In Jest you’ll find, even using `mount` instead of `shallow` mounting, you’ll get `null` for wrapped component instances, that sucks… Instead, just export a non-wrapped HOC.

`export default StateHolder(StateDisplayerOne)`
`export { StateDisplayerOne }`

This allows for complete control over the props, also doesn’t wrap the component on an unrelated component context.

Happy testing.
