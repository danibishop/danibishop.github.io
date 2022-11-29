---
layout: post
tags: debugging
categories: basics
---
## Learn to debug

> tl;dr: Instead of reading code or inserting "temporary" code, learn to debug. Debugging allows you to see the actual values of variables and how the execution jumps from one line to another. Nowadays, most IDEs have built-in solutions for most common languages, so you don't even need to be an expert: with just a bit of basic knowledge you'll be able to debug your code.

### Do you see yourself in any of these situations?

* You get a legacy codebase and you have to make changes to it. It has no tests and no docs. You need to understand it fast. You then try to read the code and run it to see what it does, maybe printing some stuff to console. After 2 weeks, you decide to run to the hills and retire from software development forever.

* You have a fancy project composed of multiple interconnected sub-systems/components/whatever you call them. You need to make a change in one of them, but you don't know how it will affect the rest of the system. Luckily, you have tests in place! But these tests require a lot of configuration that is not documented. You spend 2 days trying to get the tests to run, and then you realize that they don't even cover the part of the system you need to change. You decide to run to the hills and retire from software development forever.

* You have a bug in your code. You try to fix it, but you can't reproduce it. You try to add some logging to see what's going on, but you can't reproduce it. You try to add some "temporary" code to see what's going on, but you can't reproduce it. You decide to run to the hills and retire from software development forever.

## If your answer was "yes"...

Then you will be a much happier person once you learn **how to use a debugger**.

> Debuggers are tools that allow you to inspect the state of your program while it's running. They allow you to set breakpoints, which are points in your code where the program will stop and allow you to inspect the state of the program. You can then step through the code, line by line, and inspect the state of the program at each step. You can also inspect the state of variables, call functions, etc.

* Debuggers are non-intrusive: they don't modify your code in any way. They just allow you to inspect the state of your program while it's running.
* You can debug your tests. If some test suddendly fails, you can debug it to see what's going on (some people could argue that this smells like a bad test because it cannot be "easily understood", but that's a different topic).

## But debugging is hard!

Debugging is not hard; **using ugly or complicated tools is hard**. There is a lot of discussion about "how unfriendly `gdb` is", but aside from these debates in the `C/C++` world, debugging most of the code out there is quite easy and straightforward nowadays most of the time.

Debugging Python, Javascript, Typescript, Java, C#, etc. (which represent around the 70% up to 90% of the code out there depending on the source you check) is nowadays fully supported by the IDEs and editors you use. You don't need to learn a new tool, you just need to learn how to use the one you already have.

## Some authoritative example

Here you have John Carmack talking about IDEs and tools.

{% include youtubePlayer.html id="tzr7hRXcwkw" %}

> He's the creator of Doom, Quake, Wolfenstein 3D, and many other games. He's also a very good programmer. He's talking about how he uses the debugger to understand the code he's reading.

## TODO

* [ ] Add example
* [ ] Add references to pros and cons