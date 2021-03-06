---
title: "Why Emacs?"
date: "2020-03-29 5:44 PM"
summary: "Why I use Emacs, What is Emacs, and why does Evil Mode sound bad?"
tags: ["blog", "emacs", "programming"]
---

## I Love Vim

I've [decided to make this section it's own post](/posts/i-love-vim). I appreciate good editors, like Vim.

## Emacs!

Emacs has so much to offer, from a [healthy package system](https://melpa.org/#), complete [Vim emulation](https://www.emacswiki.org/emacs/Evil), [Magit](https://magit.vc/), [Org mode](https://orgmode.org/), [Dired](https://www.gnu.org/software/emacs/manual/html_node/emacs/Dired.html), and [so much more](https://github.com/patricksimpson/dotfiles/tree/master/emacs#emacs-packages---melpa). 

If you are looking for something lighter weight, quick edits... remote in, open Vim. Edit. Save. Done. 
Vim is there (virtually on every Unix system). It works. It's great.

I use Emacs because it can do anything. It can be anything. It can run Vim, keep notes, manipulate the file system, and so much more...

But, Emacs isn’t for everyone, and Vim isn't either. 

Know your tools. If you are happy with your editor and are a little curious, carry on.

### What is Emacs?

At its core is an interpreter for Emacs Lisp, a dialect of the Lisp programming language with extensions to support text editing.

In 1976, [Stallman](https://www.emacswiki.org/emacs/RichardStallman) wrote the first Emacs (“Editor MACroS”), which organized these macros into a single command set and added facilities for [Self Documentation](https://www.emacswiki.org/emacs/SelfDocumentation) and to be extensible. [TecoEmacs](https://www.emacswiki.org/emacs/TecoEmacs) soon became the standard editor...[read more on Wikipedia](https://en.wikipedia.org/wiki/Emacs).

In 1984, Stallman began writing another Emacs implementation based on the former co-planning with Gosling, naming it GnuEmacs, which became the first program in the GNU project.

"Standing on shoulders of giants" is a metaphor which means "Using the understanding gained by major thinkers who have gone before in order to make intellectual progress." Using Emacs, you're leveraging 44 years of group-think, combined with the progress of so many others.

Emacs has over 10,000 built-in commands and its user interface allows the user to combine these commands into macros to automate work.

### Basics

Some of the key binds (keyboard shortcuts) might look strange, here's what they mean:

Meta: `M-` Command or your "super" key. 

Control: `C-`  

So that `C-x` would be Control key, plus `x` pressed together.

- `C-x C-c` Kill Emacs, `save-buffers-kill-terminal`.
- `C-x C-e` Evaluate the current expression. This is cool, as you can do this on any elisp in your buffer.
- `C-x C-f` read a file into Emacs (or create one).
- `C-x C-s` save a file back to disk.

### Describe

`describe` is a powerful feature in Emacs that will tell you all the information you need about particulars.

- `describe-function`
- `describe-variable`
- `describe-mode`
- `describe-key`

### Melpa

[MELPA](https://melpa.org/#) is a growing collection of package.el-compatible Emacs Lisp packages built automatically on our server from the upstream source code using simple recipes. (Think of it as a server-side version of el-get, or even Homebrew.)

`M-x`: package-list-packages

Packages can be installed without restarting emacs: 

`package-list-packages` or `package-install` + `RET` + `<package_name>` + `RET`.

### Evil Mode

[Evil](https://www.emacswiki.org/emacs/Evil) is an extensible vi layer for Emacs. It provides Vim features like Visual selection and text objects, and is the successor to the now-obsolete Vimpulse and vim-mode. Its home page.

`evil-mode` an advanced Vim emulation layer. Once installed, you can run it via `evil-mode` and you should have a complete Vim experience, within Emacs!

Packages:

 - [evil](https://github.com/emacs-evil/evil)
 - [evil-leader](https://github.com/cofi/evil-leader)
 - [evil-magit](https://github.com/emacs-evil/evil-magit)

### Magit

This is my next favorite thing about Emacs. Like my buddy [Adam](https://adamsimpson.net/), I would probably still use Emacs just for Magit. It's that good. [magit](https://github.com/magit/magit).

Magit can teach you things you never knew about `git`. Like `--force-with-lease` and [why you should be using this as your default push](https://thoughtbot.com/blog/git-push-force-with-lease

Magit, [makes git fast and easy](http://emacsrocks.com/e17.html).

### Others
 
 - [ivy](https://github.com/abo-abo/swiper)
 - [projectile](https://github.com/bbatsov/projectile)
   - [counsel-projectile](https://github.com/ericdanan/counsel-projectile)
   - [projectile-rails](https://github.com/asok/projectile-rails)
 - [flycheck](https://github.com/flycheck/flycheck)
 - [tide](https://github.com/ananthakumaran/tide)
 - [company](https://github.com/company-mode/company-mode)
 - [hyrda](https://github.com/abo-abo/hydra)

#### Theme

 - [doom-themes](https://github.com/hlissner/emacs-doom-themes)
   - [doom-tomorrow-night](https://github.com/hlissner/emacs-doom-themes/blob/master/themes/doom-tomorrow-night-theme.el)
 - [doom-modeline](https://github.com/seagle0128/doom-modeline)
 - [all-the-icons](https://github.com/domtronn/all-the-icons.el)

## Customize

What all these years of Vim has taught me, learn to customize and never stop customizing. 

This year, I completely gutted my Emacs configuration and replaced it, line by line, plugin by plugin. It's fast, lightweight, and looks great.

[Check it out here](https://github.com/patricksimpson/dotfiles/tree/master/emacs).

## Resources

A post containing a bunch of helpful Emacs resources!

- [Emacs Resources](/posts/emacs-resources).
