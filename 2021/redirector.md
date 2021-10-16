---
title: "Redirector"
date: "2021-10-16 9:01 AM"
summary: "Using redirector to avoid certain undesirable web"
tags: ["blog", "software", "random"]
---

Recently I read about a little browser plugin called [Redirector](https://chrome.google.com/webstore/detail/redirector/ocgpenflpmgnfapjedencafcfakcekcd).
It’s a great little tool that allows you to change the end result of the URL of your browser. 
What’s powerful about this tool is it allows you to run regular expressions on the URL to transform your URL into new URLs. 

### Avoid Medium

I am not a huge fan of Medium for [reasons](https://nomedium.dev/).
Unfortunately however, there is a lot of content on Medium. 
To avoid medium you need to redirect away from medium. 
Thanks to https://scribe.rip/ you can do this with the redirector. 
(Also, thanks to scribe for posting about Redirector!)

`*medium.com/(.*)` -> `https://scribe.rip$1`


### Avoid “new” reddit

`^https?://w*.?reddit.com/(.*)$` -> `https://old.reddit.com/$1`

Will redirect you to old.reddit.com 

Feel free to check out [these redirects here](https://gist.github.com/patricksimpson/47027726f39ddd406f96a81d7e9454f7). Comment on this gist to add more or make improvements! 

You can download & import these redirects [here](https://gist.githubusercontent.com/patricksimpson/47027726f39ddd406f96a81d7e9454f7/raw/841c9694aa20a75da92b4e5a2c1c7ee7a3f8e28e/redirectors.json)

Enjoy!
