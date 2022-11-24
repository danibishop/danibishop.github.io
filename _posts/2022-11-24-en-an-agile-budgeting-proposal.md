---
layout: post
tags: English
categories: agile business lean
has_math: True
---

## An agile budgeting proposal

> **THIS IS A WIP**

> tl;dr: Every project I have seen in outsourcing companies has a budget. But the budget is not agile. It's a static document that is not updated during the project. This is a draft of one of the potential solutions to this problem.


### Two problems

Let's say you have a nice self-managed team that adapts and delivers value at a fast pace to a costumer of a given service-provider company. You have achieved the Agile nirvana. Haven't you?

There was some bargaining between the service-provider and the costumer, and a **budget** was agreed upon, along with some broad scope and some high-level requirements to be delivered at a certain **deadline**. 

Problems appear when budget seems not to be enough and/or deadline is coming and the customer is not satisfied with the whatever the team has delivered.

Problems also appear then the customer's context changes so wildly that the original scope is no longer valid at all.

Problems also appear when the team is delivering but the customer feels that something is off. The team is not to blame, but the customer is not satisfied.

Should we keep the project going? Is the customer going to lose 100% of the budget regardless of the outcome? Is the provider going to lose 100% of the expected income plus the opportunity cost of blocking the team for a while?

I will explore here a potential solution to these problems. But first we need to define some constraints.

## Necessary conditions

* Customer **trusts** the team
* Customer will prefer a viable product over a perfect one if that means:
    * The product is delivered before the deadline
    * The product is delivered cheaper than the budget
* Customer assumes that the scope will change as both them and the team learn more about **what adds value** and **what doesn't**
* Provider is commited to educate the customer about the agile process
* Provider tries to maximize the project ROI (=maximize income per time unit)
* Provider has a queue of projects to work on and/or values the importance of free earned time
* Customer and provider assume that the context when starting a project **will** change during the execution of it and nobody should be blamed for that, nor charged.

## Hypothesis

This proposal is an equilibrium point between the customer's and the provider's interests. None of them will regret this agreement once the project starts in any reasonable scenario.

## The proposal

* Project can be negotiated as a regular waterfall project in terms of budget and deadline limitations, but these are just **boundary conditions**, not mandatory limits that must be reached.
    * This helps the sales team to sell the project using their regular sales pitch with some variation.
    * This helps the customer to understand the project in terms of their regular project management.

* The development will follow an iterative process where the customer **must** be an active part, providing feedback about value provided.

* All split conditions for the budget left are known and agreed upon by both parties. No surprises. No bargaining post-kickoff.

* If the feedback is bad during the early stages of the development, customer can retire saving most of the budget left, but not all of it. The team will be compensated for the work done and the blocked time (opportunity cost).
    * The earlier the customer retires, the more money they save but the less value they get.

* If the feedback is good during the development, the development will reach some point where the customer will decide that there is no more value to be added before reaching the deadline and the project can be considered **done**.

    * In this case, the customer can save part of the budget left, but not all of it. The team will be compensated for **early delivery** of the **highest possible value**.
    * The customer gets top-value in less time for less money.
    * The team gets higher compensation/effort ratio, plus more time to work on other projects (or to rest).


> The rule to calculate the compensation split for the available budget can be linear, quadratic, a LUT, ... whatever that fits the business model. For the examples, I will use a linear compensation for simplicity.

## Savings/Compensation function $$\sigma(t')$$

* Project has a budget $$B$$
* Project has a duration $$D_B$$
* Elapsed time at a given moment is $$t$$.
* Normalized time is $$t'=t/D_B $$with $$t'\in[0,1]$$
    * $$t'=0$$ means that the project has just started
    * $$t'=1$$ means that the project has reached the deadline
* Budget left at a given moment: $$B_{L_t}=B-(B/D)·t=B(1-t/D) = B(1-t')$$
* Budget left is split into two parts:
    * $$S_\$  = B_{L_t}·\sigma(t')$$ are the economic savings for the customer
    * $$C_\$ = B_{L_t}·(1-\sigma(t'))$$ is the economic compensation for the blocked time (opportunity cost)
    * Where $$\sigma(t')$$ is the split factor. $$\sigma(t')\in[0,1]$$
    * $$B_{L_{t'}} = S_\$ + C_\{$}$$
* About the deadline:
    * $$S_{t'} = (1-t')$$ is the normalized saved time for both parties
        > *One extension of the model could imply translating this saved time into money for the provider, given some historical data about the team's productivity. This is not included in this proposal.*
* Provider income: $$P_\$=(B*t'+C_\$)$$

## Constant model

In this model we assume that $$\sigma(t') = \sigma_0$$, where $$\sigma_0$$ is a constant. This means that the customer will save the same percentage of the budget left at any point in time and this amount will be also the compensation for the blocked time.

For example, imagine we settle a project with these parameters:

* Budget: $$B=400000$$
* Duration: $$D_B=10$$months
* Let's give some room to the customer: $$\sigma(t') = \sigma_0 = 0.8$$

Customer wants out at $$t'=0.5$$ (half of the project duration). Then:

* $$B_{L_{t'}} = B·(1-t') = B·(1-0.5) = B·(0.5) = 200000$$ has not been spent yet.
* $$S_\$ = B_{L_{t'}}·\sigma = 200000·0.8 = 160000$$ are the economic savings for the customer
* $$C_\$ = B_{L_{t'}}·(1-\sigma) = 200000·0.2 = 40000$$ is the economic compensation for the blocked time (opportunity cost)
* $$P_\$ = (B·t'+C_\$) = (400000·0.5+40000) = 240000$$ is the provider income
* $$S_{t'} = (1-t') = (1-0.5) = 0.5$$ is the normalized saved time for both parties, which corresponds with 5 months.

> I find this model too simple and not very useful, as it always punishes one side, depending on context. It is just a starting point to explore the possibilities.

## Linear model

In this model we assume that $$\sigma(t') = \alpha t' + \beta$$, and we define one or two optional deadzones for the kick-off and the end of the project.

For example, we could define a project with these parameters:

* $$\beta = ...$$**TBD**

## Quadratic model

In this model we assume that $$\sigma(t') = \alpha t'^2 + \beta t' + \gamma$$, and we define one or two optional deadzones for the kick-off and the end of the project.

> **TBD**. Not sure if anything interesting can be done with this model in a practical scenario.

## Why there is no example for "project is about to reach deadline and customer is not satisfied with the value delivered"?

Because that scenario means that the agile process is not working in this project. Not meeting a deadline is something that can be predicted and avoided given the constraints I provided above.

I am not saying that this is not a real problem, I just say that it does not apply to this proposal in its current form.

## Why not predate the budget with a draconian contract?

Because our work is to deliver value, not to pay lawyers to write smart contracts. If you prefer to predate the budget in case of early retirement, go ahead. But then you are not in the software business, you are in the legal business.

## How the hell are you going to explain this to the customer?

First condition: the customer must trust the team. If the customer does not trust the team, then this proposal is not going to work.

Also, define a $$\sigma(t')$$ that is easy to explain. Maybe a constant is good enough. Maybe some LUT definition is also a good thing.

## Degenerate cases


### Provider predatory model

In this model we rely on lawyers to write a contract where, once it is signed, the customer is punished if they decide to retire early. This is a very bad idea, but it is a model that exists in the real world. I just want to express it in terms of the previous equations.

In this case, as the customer has to spend the whole budget in any case, the project will go on until the deadline, no matter what. Trust is destroyed in this kind of scenario, IMHO.

As there is no trust, any attempt to deliver value early will be translated into artificial work that will not add value to the customer. This is a waste of time and money for everybody.

* $$\sigma(t') = 0$$, provider predates the budget excess
* $$S_\$ = 0$$, no savings in the budget
* $$C_\$ = B_{L_t} = B(1-t')$$, but this will eventually be $$C_\$ = 0 $$as $$t'=1 $$because of artificially extended delivery time.
* $$S_{t'} = 0$$, no savings in time

### Consumer predatory model

In this model the provider is not compensated for the blocked time if the customer decides to retire early. 

* $$\sigma(t') = 1$$, consumer predates the budget excess
* $$C_\$ = 0$$, no compensation for the opportunity cost
* $$S_\$ = B_{L_t} = B(1-t')$$, all savings in the budget
* $$S_{t'} = 0$$, no savings in time

In this scenario the customer has all power. They can retire at any time and save all the budget left. The provider will not be compensated for the blocked time, but they will be compensated for the work done.

Anyhow, under this constraints there is no benefit on delivering early, so the provider will keep value hostage to ensure the next payment. This is a waste of time and money for everybody. Again.

## TODO
* [ ] Add all examples
* [ ] Add references
* [ ] Add plots
* [ ] Spanish translation
* [x] Add LaTeX support
