---
layout: post
title: GSoC 2021 - End of Community Bonding Period
comments: true
tags: [ gsoc, SymPy]
---

GSoC community bonding offically came to end yesterday and from today the official coding period has started.
The community bonding period was really productive as we started early and finalized the API design.

Key `highlights` of this week’s work are:

* **[Implement PinJoint and Joint class](https://github.com/sympy/sympy/pull/21564)**

  * This PR implements `Joint` class and `PinJoint` class.
    `Joint` class will serve as an abstract base class which would be inherited by other
    joint classes.
    The `PinJoint` class is the practical implementation of a Pin Joint. This class inherits
    `Joint` class and forms KDEs, orient frames, set linear and angular velocities all by itself,
    according to the `PinJoint`.
<br><br>
