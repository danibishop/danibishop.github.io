---
layout: post
tags: mistakes
categories: basics, agile, dev-experience
published: True
---

# What Luke Skywalker thinks about your project

> *Amazing. Every word of what you just said was wrong. The Rebellion is reborn today. The war is just beginning. And I will not be the last Jedi.* - Luke Skywalker

I am sure that most of you reading here can give this description when asked about "how do you organize your development process":

*Well, we do Scrum because we are Agile. We estimate the most important stories to know how much work can be done during the sprint. Then we start developing. Each developer takes a story and creates a branch on top of the development branch. When the task is done, the developer creates a pull request and the code is reviewed by the team. If everything is ok, the code is merged into the development branch. When the development branch is ready, we merge it into the master branch and deploy it to production.*

## First mistake: "We do Scrum because we are Agile"

Scrum is not Agile. Agile is [Agile](https://agilemanifesto.org/). Scrum is a wrapper to make XP (extreme programming) ["more palatable to management"](https://beny23.github.io/posts/my_take_on_engineering_room_9/)

## Second mistake : "We estimate the most important stories to know how much work can be done during the sprint"

Importance comes from value. Priority should come from cross-matching value and effort. Max value, min effort: that's the top priority. As nobody will tell you how many monetary units you will receive from a completed story, estimating the effort is just a waste of time.

Discuss about the most relevant topics regarding your product/service. You need some rough estimation **as a team** to bet on what should be done first, but do not let the estimation be the main driver of your development.

## Third mistake: "Each developer takes a story"

Then you get Bob, who knows about the frontend. Then, Alice, who only knows about the API. And Ron, who nobody knows what he knows about, but he is the only one who knows how to deploy the application for some reason.

Tackle stories as a team from definition to production.

## Fourth mistake: Doing Gitflow

This is not literal from the explanation but it is "common sense" nowadays in many organizations and teams.

Atlassian itself has stated that **GITFLOW IS OUTDATED**. As they state [here](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow): *"Gitflow is a legacy Git workflow"*

Stop doing Gitflow and start doing trunk-based development with feature flags or some similar mechanism. Happiness will come to your team.

> This post is part of a series. [Read the next part here](/2024/10/24/en/all-you-said-is-wrong-part-II.html)