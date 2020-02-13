### Pipe `|` is Awesome

[It's worth bringing up again](https://patricksimpson.me/posts/elegant-design/), because it's such a simple program but has the potential for infinate possibilities. 

The Unix philosophy is to do one thing and do it well, the `pipe` or `|` hindges on this by redirecting the output of a program as the input of another.

This means, anything can be used by anything... :boom:

### NPX :thumbsdown:

Forget npx, try this: 

`export PATH="node_modules/.bin:$PATH"`

This hack makes anything in your `node_modules/.bin` directory accessible to you as a runnable program based on your relative path. Meaning.. if you `npm install` you can run them without using NPX or pathing to the bin directoy everytime.


### TL;DR Manpages

This is a fantasic idea: https://tldr.sh/ 

For a person that got the whole "RTFM" thing in the past... this makes life a whole lot easier.