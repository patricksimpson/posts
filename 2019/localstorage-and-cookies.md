---
title: "LocalStorage and Cookies"
date: "2019-01-04 3:47 PM"
summary: "LocalStorage issues on mobile Safari in private mode..."
tags: ["programming", "javascript"]
---

I was doing some reading up on `localStorage` and found out that Safari on mobile (in private mode) have 0MB storage allocation.
So if you try to write to localStorage, mobile safari/chrome (in private mode) an error like `QUOTA_EXCEEDED_ERR` will be thrown.
In this case, checking for `window.localStorage` and polyfilling won't suffice, because `window.localStorage` exists, just has a 0MB memory allocation limit!

## Cookies

So cookies are still useful to cover for `window.localStorage` when it's not supported like this.
See: https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API and https://github.com/marcuswestin/store.js/blob/master/storages/cookieStorage.js via `store.js`

Also good: https://blog.whatwg.org/tag/localstorage

Just to note, this also applies to `window.sessionStorage` even though the data is deleted after the tab/window is closed, it still gets a 0MB storage allocation. Bummer.
