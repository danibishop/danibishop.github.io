---
layout: post
tags: WIP
categories: agile business lean
has_math: True
published: False
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
* Budget release is proportional to the elapsed time. This might not reflect all situations, but it is generally a good approximation.

## Hypothesis

This proposal is an equilibrium point between the customer's and the provider's interests. None of them will regret this agreement once the project starts in any reasonable scenario.




## Savings Ratio Function $$SRF(t')$$

Given that:

* Project has a budget $$B$$
* Project has a duration $$D_B$$
* Elapsed time at a given moment is $$t$$.
* Normalized time is $$t'=t/D_B$$ with $$t'\in[0,1]$$
    * $$t'=0$$ means that the project has just started
    * $$t'=1$$ means that the project has reached the deadline
* Remaining budget at a given moment is $$B_R(t')=B-(B/D)·t=B(1-t/D) = B(1-t')$$

Then, we can split the remaining budget in two parts:

* $$S_\$(t')  = B_R(t')·SRF(t')$$ are the economic savings for the customer
* $$C_\$(t') = B_R(t')·(1-SRF(t'))$$ is the economic compensation for the blocked time (opportunity cost)
* So, the remaining budget is the sum of both savings plus compensation: $$B_R(t') = S_\$ + C_\$ $$
* Where $$SRF(t')\in[0,1]$$ is the **split factor function**.
    * It represents what percentage of the remaining budget is saved by the customer if they retire at a given moment $$t'$$.


Also, other derived results:
* $$T_S(t') = (1-t')$$ is the normalized saved time for both parties
    > *One extension of the model could imply translating this saved time into money for the provider, given some historical data about the team's productivity. This is not included in this proposal.*

* Provider income: $$P_\$(t')=(B*t'+C_\$(t'))=...=B(1-SRF(t')·T_S(t')) < B$$
    * This amount is never bigger than the budget.
    * If $$SRF(t') = 0$$, the customer has no savings and the provider gets the full budget. See the example below about the Predatory Provider.
    * If $$T_S(t') = 0$$, it means that all the available time has been used and the customer has no savings.
    * **This is the function that condenses all the model**. It's shape defines the balance between the customer's and the provider's interests at any given moment.
    


## Constant model

In this model we assume that $$SRF(t') = SRF_0$$, where $$SRF_0$$ is a constant. This means that the customer will save the same percentage of the remaining budget at any point in time and this amount will be also the compensation for the blocked time.

For example, imagine we settle a project with these parameters:

* Budget: $$B=400000$$
* Duration: $$D_B=10$$months
* Let's give some room to the customer: $$SRF(t') = SRF_0 = 0.8$$

Customer wants out at $$t'=0.5$$ (half of the project duration). Then:

* $$B_R(0.5) = B·(1-0.5) = B·(0.5) = 200000$$ has not been spent yet.
* $$S_\$(0.5) = B_R(0.5)·SRF = 200000·0.8 = 160000$$ are the economic savings for the customer
* $$C_\$(0.5) = B_R(0.5)·(1-SRF) = 200000·0.2 = 40000$$ is the economic compensation for the blocked time (opportunity cost)
* $$P_\$(0.5) = (B·t'+C_\$(0.5)) = (400000·0.5+40000) = 240000$$ is the provider income
* $$T_S(0.5) = (1-t') = (1-0.5) = 0.5$$ is the normalized saved time for both parties, which corresponds with 5 months.

### Is it useful?

I find this model maybe too simple but it is a first approximation. It is easy to understand and it is easy to calculate.

In the future I will explore different $$SRF(t')$$ functions, but for now I will use this constant model to illustrate the proposal.

> Maybe some SRF that converts the provider income vs t' into a displaced sigmoid function could be interesting. Something to protect the customer from poor value deliveries in the first stages and to protect the provider from the customer's whims once the project is mature. Maybe some "tunable" sigmoid like [these](https://dhemery.github.io/DHE-Modules/technical/sigmoid/#function) could be interesting.

## Final pitch

* Project can be negotiated as a regular waterfall project in terms of budget and deadline limitations, but these are just **boundary conditions**, not mandatory limits that must be reached.
    * This helps the sales team to sell the project using their regular sales pitch with some variation.
    * This helps the customer to understand the project in terms of their regular project management.

* The development will follow an iterative process where the customer **must** be an active part, providing feedback about value provided.

* All split conditions for the remaining budget are known and agreed upon by both parties. No surprises. No bargaining post-kickoff.

* If the feedback is bad during the early stages of the development, customer can retire saving most of the remaining budget, but not all of it. The team will be compensated for the work done and the blocked time (opportunity cost).
    * The earlier the customer retires, the more money they save but the less value they get.

* If the feedback is good during the development, the development will reach some point where the customer will decide that there is no more value to be added before reaching the deadline and the project can be considered **done**.

    * In this case, the customer can save part of the remaining budget, but not all of it. The team will be compensated for **early delivery** of the **highest possible value**.
    * The customer gets top-value in less time for less money.
    * The team gets higher compensation/effort ratio, plus more time to work on other projects (or to rest).

### Some questions

#### What happens if "project is about to reach deadline and customer is not satisfied with the value delivered"?

That scenario means that the agile process is not working in this project. Not meeting a deadline is something that can be predicted and avoided given the constraints I provided above.

I am not saying that this is not a real problem, I just say that it does not apply to this proposal in its current form.

#### Why not predate the budget with a draconian contract?

Because our work is to deliver value, not to pay lawyers to write smart contracts. If you prefer to predate the budget in case of early retirement, go ahead. But then you are not in the software business, you are in the legal business.

This is a suboptimal solution as delivering value way before the deadline has more direct and potential income.

### How the hell are you going to explain this to the customer?

First condition: the customer must trust the team. If the customer does not trust the team, then this proposal is not going to work.

Also, define a $$SRF(t')$$ that is easy to explain. Maybe a constant is good enough. This is a business decision.

## Degenerate cases

### Provider predatory model

In this model we rely on lawyers to write a contract where, once it is signed, the customer is punished if they decide to retire early. This is a very bad idea, but it is a model that exists in the real world. I just want to express it in terms of the previous equations.

In this case, as the customer has to spend the whole budget in any case, the project will go on until the deadline, no matter what. Trust is destroyed in this kind of scenario, IMHO.

As there is no trust, any attempt to deliver value early will be translated into artificial work that will not add value to the customer. This is a waste of time and money for everybody.

* $$SRF(t') = 0$$, provider predates the budget excess
* $$S_\$(t') = 0$$, no savings in the budget
* $$C_\$(t') = B_R(t') = B(1-t')$$, but this will eventually be zero as $$t'=1$$ because of artificially extended delivery time.
* $$T_S(t') = 0$$, no savings in time

### Customer predatory model

In this model the provider is not compensated for the blocked time if the customer decides to retire early. 

* $$SRF(t') = 1$$, customer predates the budget excess
* $$C_\$(t') = 0$$, no compensation for the opportunity cost
* $$S_\$(t') = B_R(t') = B(1-t')$$, all savings in the budget
* $$T_S(t') = 0$$, no savings in time

In this scenario the customer has all power. They can retire at any time and save all the remaining budget. The provider will not be compensated for the blocked time, but they will be compensated for the work done.

Anyhow, under this constraints there is no benefit on delivering early, so the provider will keep value hostage to ensure the next payment. This is a waste of time and money for everybody. Again.

## TODO
* [ ] Add all examples
* [ ] Add references
* [ ] Add plots
* [ ] Spanish translation
* [x] Add LaTeX support
