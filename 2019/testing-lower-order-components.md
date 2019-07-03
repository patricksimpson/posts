---
title: "Testing Lower Order Components"
date: "2019-07-02 10:12 PM"
summary: "Testing components wrapped in HOCs can be annoying; Just don't do it."
tags: ["javascript", "react", "programming", "blog"]
---

[Higher Order Components](https://reactjs.org/docs/higher-order-components.html) (HOCs) are one of those things in the React world that confuse and irritate even seasoned engineers.
I realize React Hooks will make this a non-issue; HOCs are still being widely used in older codebases!

In Jest you’ll find, even using `mount` instead of `shallow` mounting, you’ll get [`null` for wrapped component instances](https://github.com/airbnb/enzyme/issues/711), that sucks…

When testing a component wrapped in HOCs, the best way I have found, make it a “simple” component. Just export a non-wrapped component as well as the wrapped component.

### Just export a non-wrapped component:

```javascript
export default StateHolder(StateDisplayerOne);
export { StateDisplayerOne };
```

This allows for complete control over the props, also doesn’t wrap the component on an unrelated component context.

Enjoy.
