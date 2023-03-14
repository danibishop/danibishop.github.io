---
layout: post
tags: chatgpt tools
categories: opinion lists
published: True
---

# Three wrong uses of ChatGPT for development

Starting 2023, everybody is trying to productize ChatGPT. That is a reality we have to deal with. It is just what it is.

There are thousands of articles about how to use ChatGPT, why it is cool, how astonishing it is. I do not care about that in the context of this post. Even if ChatGPT was the best tool ever to generate text/code, I am listing here three cases where I think it is not a good idea.

> Disclaimer: my goal is not to point to this or that product and say how bad it is. I am not providing any links to any product, even when I have seen them and tested some of them.

## ChatGPT to generate commit messages

It seems natural: you take the diff between two code commits and infer the commit message from it. It is so straightforward that it must be a good idea. But it is not.

Commit messages are intended to provide a human-readable description of the changes. They are written by humans for humans so the **intention** of the changes is clear.

You cannot know the **intention** of the changes from a diff. The diff is the **how** of the changes, not the **why**.

*"But Dani, people write terrible commit messages. Let's use ChatGPT to generate them!"* I agree that some people write terrible commit messages. That is a reason to train them; not to let a machine write terrible commit messages.

There are really nice templates for commit messages. There are [conventions](https://www.conventionalcommits.org/en/v1.0.0/) and there are tons of articles explaining how to write good commit messages (a nice starting point is [here](https://cbea.ms/git-commit/)).

*"But Dani, some commits need a nice summary of what has been done because they have many changes."* Ok. Am I the only one who clearly sees that the problem here is the commit size, not the commit message?

## ChatGPT to generate changelogs

This is very similar to the previous case. There are already tools that generate changelogs from the git history. I never liked this idea (well... not "never", I advocated for it some years ago...) as people tend to use it as a black box and copy/paste the output to whatever changelog database they use. Even worse, some people generate **release notes** this way.

You could argue that, if you put such information in the commits, this process becomes really trivial but I can think of many commit messages that are not related to customer facing changes (i.e. "Refactor to improve readability of X class", "Fix bug in Y method", "Add unit tests for Z class to cover R case").

Again, **changelogs are meant to be read by humans** and should contain information about the **intention** of the changes. You cannot know the intention of the changes from the code.

Imagine generating commit messages from the diff using a machine learning model and using those commit messages to generate a changelog and/or a release note. You would end up with **the ilusion** of having proper documents and would probably have to spend a lot of time fixing them.

## ChatGPT to generate tests

This one is my favourite. I recently saw this tool that promotes itself showing some source code and the generated unit tests for it.

Aside from violating TDD principles (you could generate **extra** tests aside from the ones you use to design but no the whole test suite), it violated basic testing principlies such as unit testing private methods and testing implementation details.

Even more: the example they show **does not even run** because it lacks imports. And, if you fix the imports, tests don't pass.

Could you generate tests properly from the code? I am pretty sure you can if you rely on some static analysis prior to the machine learning model to generate code that looks like tests that pass by executing your code. I mean... I have done it without ML in the past. In fact, I generated test templates with known assertions as I was doing a code generation tool for a specific domain. Those tests were meant to check that developers using the code were using the API correctly.

Is this desirable as a generic tool? I do not think so. This conflicts with proper TDD as it masks the need to make tests first. I am not going to argue here about TDD being the right way to go or not: latest studies say that using TDD along with other techniques is a good predictor of success in average, but you are free to test however you prefer. Just don't use ChatGPT to generate the tests :)

Do you know **what would be awesome?** A tool that generates code from TDD tests. That I would like to see.

