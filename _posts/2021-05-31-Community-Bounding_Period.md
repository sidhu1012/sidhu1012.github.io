---
layout: post
title: GSoC 2021 - Community Bonding Period
comments: true
tags: [ gsoc, SymPy]
---

The first part of GSoC was Community Bonding Period.

In this period my main focus was on :
- Setting up my blog, where I will provide weekly reports on the progress of my project, and synchronizing it with Planet SymPy.
- Finding the suitable API for `Joint` classes and `JointsMethod`. I had a virtual meeting with my mentors, where we dicussed the API. Mentors asked me to solve some problems myself to get a better idea of how the API should be and what would the user want. Before the start of meeting, I was really nervous that how things would proceed as it was our first meet but my mentors are really cool and nice peope that eased some pressure off me and helped me interact efficiently. We decided to meet every Tuesday!
- Setting up a [github issue](https://github.com/sympy/sympy/issues/21519) were we can interact and have discussions, since we decided not to go with live chat yet.

Since I have been contributing to SymPy for the past 1 year, it was easier for me to blend into the community.

Now, as everything has gone as planned, I have decided to make a head start and begin with the implementation of my project.

Key `highlights` of this week’s work are:

* **[Prototype - Implement Joints class](https://github.com/sympy/sympy/pull/21524)**

  * In this PR, I proposed an API design and solved some example problems with this API to demonstrate my API. We will have a detailed dicussion of the API in the upcoming meet.
<br><br>

* **[Body.apply_torque takes frame as optional argument](https://github.com/sympy/sympy/pull/21551)**

  * While solving example problems using proposed API, I found a limitation of class `Body` that torque can't be applied to the Body instance w.r.t any frame other than the `Body.frame`. This wasn't a desired condition and contradicted with docstring. So this PR adds that functionality to the `Body` class, as an optional `frame` parameter is added to `appy_torque()` which defaults to `Body.frame` to make it backwards compatible.
