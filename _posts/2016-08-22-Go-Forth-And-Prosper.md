---
layout: post
title: Go Forth And Prosper
author: Nicholas Samson
---

>  And now, once again, I bid my hideous progeny go forth and prosper. I have an affection for it....

## Frankenstein's Monster 
-----

  Until recently, I never considered myself a fan of Go. The language seemed Spartan, without many of the syntactically sweet tools other languages offered.

  What kind of a language doesn't even have exceptions? Or while statements, for that matter?

  With object-oriented languages having been around since *long* before I was born, it seemed ludicrous that not only did Go not have inheritance, it didn't even have a real concept of an object!

  It wasn't until I started working on [my big Ethereum project](/projects) that I got any real exposure to Go, and in the time since that started, I've gone from being disgusted by the concept of the language to being the biggest proponent of it that I know.

## A Change Of Heart
-----

  A big part of that project was that I had to port a large number of features from the [Go implementation](https://github.com/ethereum/go-ethereum) of Ethereum to a somewhat restricted subset of C++. I got jealous when I saw what go-ethereum could do in a few lines that took me dozens. It's not until you get to work with a minimalist language that you truly understand exactly how verbose C++ and similar languages are; take a look at this example.

  I want to create an empty collection of integers, and then add another collection of integers to it, and then prints them. Let's see what this looks like in each of those languages.

Here's Go:
<script src="https://gist.github.com/nes77/7762f2c45e8e4285caa8704b87b1f0e7.js"></script>

And here's C++:
<script src="https://gist.github.com/nes77/28be1771ec5213bf148ef6014bf3d21d.js"></script>

  Sure, it's not the biggest of features, but the Go implementation is significantly short, if not by line count, then by character count. Not to mention, the C++ API appears fairly unintuitive for someone unfamiliar with the design behind the language; Go's choice of limiting the core data structures, but giving those structures a clear and simple API, means users don't have to read a thick book of the history of the language to understand the motivations behind the standards. In addition, the ease with which information about objects (like a string representation) can be obtained in Go means that it's easy to create log entries for complicated data structures.

  I know what someone who really knows Go might be thinking: *why aren't you mentioning goroutines? Or channels? or \[insert feature here\]?* Well, first, I wanted the example to be short enough to read in a moment, and implementing goroutines in C++ would take many, many more lines than I wanted for a short example. In addition, a simple list-like collection is probably going to be the thing you use the most when you program. Also not mentioned is the staggeringly huge standard library, including things like arbitrary precision mathematics, HTTP/TLS support, and included tooling for dependency management and testing (looking at you, almost every other programming language), all of which make creating large programs very fast. Perhaps best of all is a big benefit of that large standard library; if your project has no native dependencies, your code will compile on almost every mainstream platform, with no changes to your code (unless, obviously, you're using system specific features). Linux, Windows, OSX (or MacOS, I suppose), x86, x86-64, ARMv7; it doesn't matter. Your code just works. It comes much closer to "Write Once, Compile Anywhere" than any other language I've worked with, and that makes me very happy.

## To Summarize
-----
  Try Go. It may take some time to get used to its unorthodox design, but the language just gets out of your way, and lets you program. And isn't that what programming languages were really meant to do?
