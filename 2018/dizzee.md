---
title: 'Dizzee for Emacs'
summary: 'Just a little quick post about Dizzee for Emacs application management'
date: '2018-06-29 11:23 PM'
tags: ['emacs', 'tech', 'prgramming']
---

I needed a way to run multiple applications at the same time that didn't involve opening multiple terminal sessions.

## Dizzee

[Dizzee](https://github.com/davidmiller/dizzee) is a small little emacs tool that enables running seperate project commands to run without leaving emacs.

First you want to install dizzee ([via melpa](https://melpa.org/#/dizzee)):

In your emacs settings file `settings.el`

```lisp
(use-package dizzee
  :ensure t
  :config (progn
    (defvar dz-projects "~/dotfiles/emacs/dz-projects.el")
    (if (file-exists-p dz-projects)
    (load-file dz-projects)))
)
```

A project is defined in your `dz-projects.el` file such as:

```lisp
(dz-defservice cool-project-client "npm"
                        :args ("run" "serve")
                        :cd "/Users/patrick/github/cool-project-client")
```

and say you want a project running a server...

```lisp
(dz-defservice cool-project-server "rails"
                        :args ("server" "-p" "3001")
                        :cd "/Users/patrick/github/cool-project-server")
```

What dizzee does is start these processes within emacs, lets you start/stop these servers without leaving Emacs.

You could even setup a keybind (or [hyrdra](https://github.com/abo-abo/hydra)) to launch your applications! Or simply `M-x cool-project-start`.
