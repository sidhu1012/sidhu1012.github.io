---
layout: post
title: GSoC 2021 - Week 5 and Week 6
comments: true
tags: [ gsoc, SymPy]
---

Key `highlights` of this week’s work are:

* **[Unpin the symengine version](https://github.com/sympy/sympy/pull/21725)**

  * Once the `PinJoint` was merged the master branch started failing on master
    branch because the `symengine` version in optional dependencies was pinned to an
    old build. So this PR unpins that version so that always the latest version of
    symengine is installed.
<br><br>

* **[Fix failing master branch](https://github.com/sympy/sympy/pull/21728)**

  * This PR aimed to change the use case of `pi` in `Joints` which was causing the master
    build to fail.
<br><br>

* **[Check if velocity is defined in frame before taking derivative of pos](https://github.com/sympy/sympy/pull/21730)**

  * While working on `PrismaticJoint` I found a hidden test case of automatic calculation of
    velocity. In joints we have a limitation that we can set relation of child body to immediate
    parent body only. In a chain/series of joints there is no way to set relation of child body
    to any other parent body, in that case we need a way to compute velocity relations(we can
    already compute pos relations). The automatic velocity calculation accounted only for the
    differentiation of the related position vector rather than checking defined velocity in intermediate
    frames. So this PR aims to check velocity in intermediate frame first before looking at position vector.
<br><br>

* **[Add warnings to magnitude and angle_between](https://github.com/sympy/sympy/pull/21749)**

  * Python ignores the leading negative sign while computing so that could lead
    to an inappropriate result. So added `Warnings` section to `magnitude` and
    `angle_between` functions of class `Vector` in `physics.mechanics` to make
    user aware of it.
<br><br>

* **[Implement forces and torques](https://github.com/sympy/sympy/pull/21712)**

  * All forces and torques would be attached to their respective bodies on which they are acted upon.
    So made `.loads` attribute of class `Body` immutable to have complete control over the forces and torques added. Made `.apply_force()` and `.apply_torque()` to handle equal and opposite forces/torques.
    Also added `clear_loads()` function to clear all the loads from a body and a `remove_load` function
    to remove entire torque from the body or entire force from a point on the body.
<br><br>

* **[JointsMethod](https://github.com/sympy/sympy/pull/21759)**

  * Made a method `JointsMethod` to form the equations of motion of a system created with joints.
    It takes an inertial frame/body and all the joints and then computes all kdes using Kane's
    method in backend. It has all attributes of Kane's method.

