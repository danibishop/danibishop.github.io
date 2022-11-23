---
layout: page
tags: debugging basics tools
---
## (re-)Learn to debug

> This post is also available in [Spanish](es-learn-to-debug.html).

> tl;dr: Instead of reading code or inserting "temporary" code, learn to debug. It's a skill that will make your life easier once you start using it. You don't even need to "master" it, just learn the basics and you'll be fine.

### Do you see yourself in any of these situations?

* You get a legacy codebase and you have to make changes to it. It has no tests and no docs. You need to understand it fast. You then try to read the code and run it to see what it does, maybe printing some stuff to console. After 2 weeks, you decide to run to the hills and retire from software development forever.

* You have a fancy project composed of multiple interconnected sub-systems/components/whatever you call them. You need to make a change in one of them, but you don't know how it will affect the rest of the system. Luckily, you have tests in place! But these tests require a lot of configuration that is not documented. You spend 2 days trying to get the tests to run, and then you realize that they don't even cover the part of the system you need to change. You decide to run to the hills and retire from software development forever.

* You have a bug in your code. You try to fix it, but you can't reproduce it. You try to add some logging to see what's going on, but you can't reproduce it. You try to add some "temporary" code to see what's going on, but you can't reproduce it. You decide to run to the hills and retire from software development forever.

## If yes...

Then you will be a much happier person once you learn **how to use a debugger**.

> Debuggers are tools that allow you to inspect the state of your program while it's running. They allow you to set breakpoints, which are points in your code where the program will stop and allow you to inspect the state of the program. You can then step through the code, line by line, and inspect the state of the program at each step. You can also inspect the state of variables, call functions, etc.


## But debugging is hard!

Debugging is not hard; using ugly or complicated tools is hard. There is a lot of discussion about "how unfriendly is `gdb`", but aside from these debates in the `C/C++` world, debugging most of the code out there is quite easy and straightforward nowadays most of the time.

Debugging Python, Javascript, Typescript, Java, C#, etc., which represent

## An example

TBD

## Some authoritative example

Here you have John Carmack talking about IDEs and tools.

{% include youtubePlayer.html id=tzr7hRXcwkw %}

> He's the creator of Doom, Quake, Wolfenstein 3D, and many other games. He's also a very good programmer. He's talking about how he uses the debugger to understand the code he's reading.
