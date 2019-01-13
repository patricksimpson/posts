---
title: "Developing on Linux"
summary: "Making the switch from developing on MacOS to Linux. What tools are the same, what tools are different?"
date: "2018-02-25 1:12 PM"
tags: ["mac", "tech", "linux", "comments"]
---

I've decided to switch my home development box from MacOS to Linux and in doing so I wanted to have a little record of
my transition to the new OS. Also, just to note, my home dev box was a hackintosh and not as stable as I had originally hoped (shocker, right?).
MacOS and Linux share a common *inx system under the hood, so there are a lot of similarties.

## Graphical User Interface

I've chosen Ubuntu 17.10 simply for the amount of users and community that is built around it. By default
17.10 installed Gnome, with the Ubuntu sidebar, but Ubuntu 18.x will not ship with the sidebar, so the first
thing I did was remove the sidebar and [update gnome](https://www.omgubuntu.co.uk/2017/10/install-vanilla-gnome-shell-ubuntu-17-10).

UI Extras:

  - [Gnome Tweak Tool](https://launchpad.net/gnome-tweaks) for tweaking your UI.
  - [System76/pop gtk theme](https://github.com/pop-os/gtk-theme) an amazing looking theme.
  - The [Monaco font](https://github.com/hbin/top-programming-fonts/raw/master/Monaco-Linux.ttf), for both command line / and GUI Emacs.
  - I am a huge fan of [Moom](https://manytricks.com/moom) on Mac, so I found [gTile](https://extensions.gnome.org/extension/28/gtile/) which is pretty amazing right out of the box.

## Command Line

This is a tool as a developer you should be pretty fond of, right?

I am a zsh user and I did install zsh first. I pulled in my dotfiles, and had to clean out some of the mac related noise is all, everything else just worked right away.

Ubuntu comes with [aptitude](https://wiki.debian.org/Aptitude) vs well App Store? I don't think Mac ships with a CLI "package manager".

On linux you could just use `aptitude` or `apt`, but I love homebrew. Good news, there's a fork for linux called [linuxbrew](http://linuxbrew.sh/).
After linux homebrew installed, all my other tools have been installed using `brew install` which so far has held up nicely!

`brew install node` for example, works like a charm, but installs to /home/linuxbrew/.linuxbrew/bin/brew.

## Development tools

My editor, [Emacs](https://www.gnu.org/software/emacs)... well that was easy, it works great on both systems.

All my other command line tools were available for Linux, such as: git, imagemagick, gpg, node, php, mysql, sqlite, ruby, etc..

## That's it for now

That's about as far as I have come, I am sure there'll be more "conversions" but all-in-all it's been pretty smooth.
I won't talk about the issue with my duel boot, UEFI woes prior to getting to this point. That's a post all on it's own.
