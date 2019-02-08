---
title: "Elegant Design"
date: "2019-02-08  9:12 AM"
summary: "Building amazing software; Iterate and imrpove your system over time."
tags: ["programming", "linux", "javascript", "blog"]
---

Recently, I read this article by Jessie Frazelle called [For the Love of Pipes](https://blog.jessfraz.com/post/for-the-love-of-pipes/), and was struck by something very interesting said in this article about the "Unix philosophy".

I will highlight the top 3 here:

"The Unix philosophy is documented by Doug McIlroy:"

> (i) Make each program do one thing well. To do a new job,
> build afresh rather than complicate old programs by adding
> new "features."
>
> (ii) Expect the output of every program to become the input to
> another, as yet unknown, program. Don't clutter output
> with extraneous information. Avoid stringently columnar or
> binary input formats. Don't insist on interactive input.
>
> (iii) Design and build software, even operating systems, to be
> tried early, ideally within weeks. Don't hesitate to throw
> away the clumsy parts and rebuild them.

[Bell System Techincal Journal - 1978](http://emulator.pdp-11.org.ru/misc/1978.07_-_Bell_System_Technical_Journal.pdf)


## Make each program do one thing well.

This, being the first and probably the most important, is why *inx is elegant. Jessie mentions how her most used program was a `|`  character!?

`|` or the pipe program, allows the output of a program to become the input of another, basically, it’s a function call, right?

unix

    echo "say something" | grep something

JS

    grep(echo("say something"), "something");


The `echo` program outputs "say something", while `grep` takes an input "say something" and looks for the following string "something" and outputs the match "something".

We need to remember this philosophy when we design software today.
Resist writing massive, "kitchen sink" programs. Just make each program do ONE thing well.

## Expect the output of every program to become the input to another, as yet unknown, program

This jives exceedingly well with the first philosophy. This for almost endless use cases, mixing programs, in a sense, a programming language of programs. That is bash scripting in a nutshell.

Again, this is something when designing a system we need to ensure we’re doing well today. Whether you're using immutable JS or one of those TypeScript weirdos (just kidding, I love TS); EXPECT that the output of your programs (or functions) is the input of another. Don’t clutter the output.

## Design and build software, even operating systems, to be tried early, ideally within weeks. Don't hesitate to throw away the clumsy parts and rebuild them.

Lastly, how truly amazing is this statement?
How often do we get stuck on something because we abstracted early? This goes very nicely with the first 2 mentioned previously.

Iterate and improve your systems over time. Elegant.
