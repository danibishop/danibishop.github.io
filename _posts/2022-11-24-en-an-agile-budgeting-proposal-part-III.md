---
layout: post
tags: WIP
categories: agile business lean
has_math: True
published: True
---

# An agile budgeting proposal - Part III

> DISCLAIMER: This is a WIP

> This is the third and last part of a series of posts about agile budgeting. The first part with the basics can be found [here](agile/business/lean/2022/11/24/en-an-agile-budgeting-proposal-part-I) and the second (with the mathematical theory) [here](agile/business/lean/2022/11/24/en-an-agile-budgeting-proposal-part-II).

## Some questions

### What happens if "project is about to reach deadline and customer is not satisfied with the value delivered"?

That scenario means that the agile process is not working in this project. Not meeting a deadline is something that can be predicted and avoided given the constraints I provided above.

I am not saying that this is not a real problem, I just say that it does not apply to this proposal in its current form.

### Why not predate the budget with a draconian contract?

Because our work is to deliver value, not to pay lawyers to write smart contracts. If you prefer to predate the budget in case of early retirement, go ahead. But then you are not in the software business, you are in the legal business.

This is a suboptimal solution as delivering value way before the deadline has more direct and potential income.

### How the hell are you going to explain this to the customer?

First condition: the customer must trust the team. If the customer does not trust the team, then this proposal is not going to work.

Also, define a $$ABSF(t')$$ that is easy to explain. Maybe a constant is good enough. This is a business decision.

## Degenerate cases

### Provider predatory model

In this model we rely on lawyers to write a contract where, once it is signed, the customer is punished if they decide to retire early. This is a very bad idea, but it is a model that exists in the real world. I just want to express it in terms of the previous equations.

In this case, as the customer has to spend the whole budget in any case, the project will go on until the deadline, no matter what. Trust is destroyed in this kind of scenario, IMHO.

As there is no trust, any attempt to deliver value early will be translated into artificial work that will not add value to the customer. This is a waste of time and money for everybody.

* $$ABSF(t') = 0$$, provider predates the budget excess
* $$S_\$(t') = 0$$, no savings in the budget
* $$C_\$(t') = B_R(t') = B(1-t')$$, but this will eventually be zero as $$t'=1$$ because of artificially extended delivery time.
* $$T_S(t') = 0$$, no savings in time

### Customer predatory model

In this model the provider is not compensated for the blocked time if the customer decides to retire early. 

* $$ABSF(t') = 1$$, customer predates the budget excess
* $$C_\$(t') = 0$$, no compensation for the opportunity cost
* $$S_\$(t') = B_R(t') = B(1-t')$$, all savings in the budget
* $$T_S(t') = 0$$, no savings in time

In this scenario the customer has all power. They can retire at any time and save all the remaining budget. The provider will not be compensated for the blocked time, but they will be compensated for the work done.

Anyhow, under this constraints there is no benefit on delivering early, so the provider will keep value hostage to ensure the next payment. This is a waste of time and money for everybody. Again.

## TODO (for the series)
* [ ] Add all examples
* [ ] Add references
* [ ] Add plots
* [ ] Spanish translation
* [x] Add LaTeX support
