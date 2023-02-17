---
layout: post
tags: WIP
categories: agile business lean
has_math: True
published: True
---

# An agile budgeting proposal - Part II

> DISCLAIMER: This is a WIP

> This is the second part of a series of posts about agile budgeting. The first part can be found [here](en-an-agile-budgeting-proposal-part-I).

## Agile Budget Split Function $$ABSF(t')$$

> As I mentioned in the previous part, **this is the function that condenses all the model**. It's shape defines the balance between the customer's and the provider's interests at any given moment and how money and time are balanced.

*Given that:*

* Project has a maximum budget $$B$$
* Project has a maximum duration $$D_B$$
* Elapsed time at a given moment is $$t$$.
* Normalized time is $$t'=t/D_B$$ with $$t'\in[0,1]$$
    * $$t'=0$$ means that the project has just started
    * $$t'=1$$ means that the project has reached the deadline
* Remaining budget at a given moment is $$B_R(t')=B-(B/D)·t=B(1-t/D) = B(1-t')$$

Then, we can split the remaining budget in two parts if the project stops at a given moment $$t'$$:

* $$ABSF(t')\in[0,1]$$ is the **split factor function**.
    * It represents what percentage of the remaining budget is saved by the customer if they retire at a given moment $$t'$$.
    * $$S_\$(t')  = B_R(t')·ABSF(t')$$ are the **economic savings for the customer**
    * $$C_\$(t') = B_R(t')·(1-ABSF(t'))$$ is the **economic compensation for the future blocked time** (opportunity cost)
    * So, the remaining budget is the sum of both savings plus compensation: $$B_R(t') = S_\$ + C_\$ $$

## Additional results

* $$T_S(t') = (1-t')$$ is the normalized saved time for both parties
    > *Each party saves time, but the model does not evaluate how this time is used nor quantifies it in terms of money.* This could translate into a marketing advantage for the customer and room for other projects or free time for the provider.
* Provider income: $$P_\$(t')=(B*t'+C_\$(t'))=...=B(1-ABSF(t')·T_S(t')) < B$$
    * This amount is never bigger than the maximum budget.
    * If $$ABSF(t') = 0$$, the customer has no savings and the provider gets the full budget. (See the example about the Predatory Provider in the [next post](/en/an-agile-budgeting-proposal-part-III))
    * If $$T_S(t') = 0$$, it means that project reached its end exactly at the predicted maximum deadline, spending all the budget.
    
    


## Constant model

As an example, we can assume that the split function a fixed percentage, so that $$ABSF(t') = ABSF_0$$, where $$ABSF_0$$ is the constant.

> This means that the customer will save the same percentage of the remaining budget at any point in time and this amount will be also the compensation for the blocked time.

For example, imagine we settle a project with these parameters:

* Max budget: $$B=400000$$
* Max duration: $$D_B=10$$months
* Let's give some room to the customer: $$ABSF(t') = ABSF_0 = 0.8$$

Imagine that something happens because things happen and the customer wants out at $$t'=0.5$$ (half of the project duration).

*Then:*

* $$B_R(0.5) = B·(1-0.5) = B·(0.5) = 200000$$ has not been spent yet.
* $$S_\$(0.5) = B_R(0.5)·ABSF = 200000·0.8 = 160000$$ are the economic savings for the customer
* $$C_\$(0.5) = B_R(0.5)·(1-ABSF) = 200000·0.2 = 40000$$ is the economic compensation for the blocked time (opportunity cost)
* $$P_\$(0.5) = (B·t'+C_\$(0.5)) = (400000·0.5+40000) = 240000$$ is the provider income
* $$T_S(0.5) = (1-t') = (1-0.5) = 0.5$$ is the normalized saved time for both parties, which corresponds with 5 months.

### Is the constant model useful?

I find this model too simple but it is an applied example about how to apply the principles. It is easy to understand and it is easy to calculate.

> Maybe some ABSF in a sigmoid shape could be interesting. Something to protect the customer from poor value deliveries in the first stages and to protect the provider from the customer's whims once the project is mature. Maybe some "tunable" sigmoid like [these](https://dhemery.github.io/DHE-Modules/technical/sigmoid/#function) could be interesting.

## Integrating this model in your business as a software provider

* Project can be negotiated as a regular waterfall project in terms of budget and deadline limitations, but these are just **boundary conditions** (maximums), not mandatory limits that must be reached.
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

---

In the [next article](en-an-agile-budgeting-proposal-part-III) I show some Q&A and degenerated cases to get some perspective.
