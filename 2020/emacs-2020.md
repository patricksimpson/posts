---
title: "Why Emacs?"
date: "2020-03-29 5:44 PM"
summary: "A fresh new Emacs config for 2020."
tags: ["blog", "emacs", "programming"]
---

## I Love Vim

Much like [Aaron Bieber](https://blog.aaronbieber.com/2015/06/03/evil-mode.html), I started out coding using Vim. (Check out all his great write ups, [like this one](https://blog.aaronbieber.com/2015/05/24/from-vim-to-emacs-in-fourteen-days.html))

And, I do love Vim. It is still one of the greatest editors of all time, and being an EVIL mode user, I love the default keybindings Vim has to offer.

Vim is, highly configurable with many packages/plugins available. There's a steep learning curve, but worth the productivity increase overtime, it's worth the investment. 

One of the the biggest advantage to Vim Bindings  (aside from all the plugins and keyboard shortcuts you can add to your workflow), with the default keybindings, you never have to take your hands off the keyboard or far from the "home row."

Vim was designed to be used on systems without Graphical User Interfaces, with limited mouse support. This is a huge advantage on servers, but another advantage is performance.

## Why Emacs?

Emacs has so much to offer, from a healthy package system, complete Vim emulation, Org mode, and more!

### Basics

Some of the key binds (keyboard shortcuts) might look strange, here's what they mean:

Meta `M-` Command or your "super" key. 

Control `C-`  

So that `C-x` would be Control + x together. 

### Exiting Emacs

`C-x C-c` Kill Emacs, `save-buffers-kill-terminal`.

`C-x C-e` Evaluate the current expression. This is cool, as you can do this on any elisp in your buffer.

For example: `(+ 2 2)` placeing your cursor on `)` and pressing `C-x C-e` will evalulate the elisp.

`C-x C-f` read a file into Emacs (or create one).

`C-x C-s` save a file back to disk.

### Melpa

MELPA is a growing collection of package.el-compatible Emacs Lisp packages built automatically on our server from the upstream source code using simple recipes. (Think of it as a server-side version of el-get, or even Homebrew.)

`M-x`: package-list-packages

Packages can be installed without restarting emacs: 

`package-list-packages` or `package-install` + `RET` + `<package_name>` + `RET`.

### Evil Mode

Evil is an extensible vi layer for Emacs. It provides Vim features like Visual selection and text objects, and is the successor to the now-obsolete Vimpulse and vim-mode. Its home page.

`evil-mode` an advanced Vim emulation layer. Once installed, you can run it via `evil-mode` and you should have a complete Vim experience, within Emacs!

### Magit

This is my next favorite thing about Emacs. Like my buddy Adam, I would probably still use Emacs just for Magit. It's that good.

## Customize

What all these years of Vim has thaught me is, learn to customize and never stop customizing. This year, I completely gutted my Emacs configuration and replaced it, line by line, plugin by plugin. It's fast, lightweight, and looks great.

Give it a shot. If you need help, reach out!
