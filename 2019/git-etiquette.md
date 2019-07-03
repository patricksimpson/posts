---
title: "Git Etiquette"
date: "2019-06-21  1:17 PM"
summary: "My own personal opinions on proper git etiquette."
tags: ["blog", "programming", "git"]
---

<img src="https://i.postimg.cc/bvN1N1Q9/git-logo.jpg" style="max-width: 256px; float:right;" />

Recently, I found myself expressing my opinions on git etiquette. This comes from many years of experience with all kinds of teams that used git, sometimes differently than my own style or sometimes much better.

I have found that following some minor rules will help you and your team in the long run.

## Pulling

First thing is first `git pull --rebase` ← should be your default pull.

**What does it do?**

It fetches temporarily stashes your work locally. Pulls and updates the local branch based on everything prior to you starting your work. Then applies your commits on top of that work.

**Why is this good?**

This puts it on YOU to merge incoming changes. Hey that work is already merged and “complete”. If a force push or something changed upstream that is the *source of truth*.
Your current work is not and should be updated based on those changes, never the other way around. It’s called being a good git citizen. You’re a great human being afterall, right?

## Branching

I believe branches should always be lower case. This is my own personal belief of course, but honestly why capitalize anything in a branch name? You’re not drafting a blog article, or titling a book... It’s an extension of programming.

`feature--something-really-cool` is easier to read, easier to code, easier to search, and just plain easier to type than `Feature--SomEthinG-Really-Cool`

Why force pinky fingers stress and strain? 😏

I don’t mind other branch naming convetions, such as `feature--` vs `feature/` or `jira-1234/`. Whatever you and your team agree on there. Let’s just agree to not use capital letters please in branch names.


## Committing

Stop. Useless. Commit. Messages.

First, you should be using a commit style. `<type>(<scope>): <subject>` is probably my most favorite pattern to follow, but come up with your own if you want to. Just be consistent. I recommend a [semantic](https://seesparkbox.com/foundry/semantic_commit_messages) approach like my example via [Karma](https://karma-runner.github.io/4.0/dev/git-commit-msg.html).

### Types

[Karma](https://karma-runner.github.io/4.0/dev/git-commit-msg.html) types:

 - feat (new feature for the user, not a new feature for build script)
 - fix (bug fix for the user, not a fix to a build script)
 - docs (changes to the documentation)
 - style (formatting, missing semicolons, etc; no production code change)
 - refactor (refactoring production code, eg. renaming a variable)
 - test (adding missing tests, refactoring tests; no production code change)
 - chore (updating grunt tasks etc; no production code change)

### Scope

If this commit is for a Jira card, spike, etc.. put it in the scope section. This tells anyone reading the log, the larger story for this commit. This is the *larger* reason for this commit.

### Subject

This is the most vauge section (other than body that is). Type a meaningful subject for your commit. If you want to put in more detail, add a `<body>` section to your commit.

Remember, it only takes a few seconds to type a good commit message that will help convey to others the meaning, purpose, and scope of your commit.

Please take some time and think about your commit style!

## Pushing

Before you push remember, pat yourself on the back for getting your work done. Congrats. But hold up...

### Rebase

I know it’s exciting to finally push up your hard work... but let’s remember it’s time to polish up your work and: `git rebase -i origin/master`

`squash` or `fixup` your junk commits, (wip, fixup).

`reword` anything that doesn’t meet your semantic commit messages

Rebasing can be confusing. Mainly you must remember that `theirs` becomes YOUR hard work, and `ours` becomes the upstream (others) work that has not been previously rebased. Check out this [article](https://nitaym.github.io/ourstheirs/) or read up on why this is on [git documentation](https://git-scm.com/docs/git-rebase).

Rebase: Flips the meaning of `ours` vs `theirs`.

Ask for help if your unsure. Verify what’s on master before resolving any conflicts.

Double check; then force push to your branch and open your pull request!

**NEVER FORCE PUSH MASTER** (unless you know what you are doing).

Force push is needed anytime we interactively rebase or ammend commits. Because you’ve now changed previous SHAs... they are new commits, in which new SHAs are generated and old ones disappear. When you are pushing on your own branch after a good rebase session, it’s not and should not be a big deal to force push. Don’t be afraid.

### Push: force with lease

If you are unsure, you can `git push --force-with-lease` (https://thoughtbot.com/blog/git-push-force-with-lease) which will reject if anything was pushed after you rebased. It’s a good way to ensure you’re not destroying others work.

Speaking of `--force-with-lease` that is the default force push with [Magit](https://magit.vc/);
![](https://i.postimg.cc/5t7LHjgd/magit-force-with-lease.png)

It really should be your default `--force` push as well. I highly recommend it.

![](https://i.postimg.cc/W1SJKtQF/use-the-force.jpg)
