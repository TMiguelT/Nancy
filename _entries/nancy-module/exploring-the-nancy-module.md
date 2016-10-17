---
sectionclass: h1
sectionid: exploring-module
parent-id: content
is-parent: yes
number: 2000
title: Exploring the Nancy Module
---
Modules are the lynchpin of any given Nancy application. Modules are the one thing you simply cannot avoid because they are where you define the behavior of your application. In fact declaring a single module is the bare minimum requirement for any Nancy application.

A module is created by inheriting from the NancyModule class; it’s as simple as that. Once you have a module you can start defining the behaviors of your application, in the form of routes and the actions they should perform if they are invoked. In short, a module tells Nancy how to behave at runtime.

A module does more than allow you to define application behavior. A module also gives you access to a whole range of useful things such as full information about the current request, access to the context in which the request is being processed, helpers for building up specific kinds of responses (e.g json, xml, files, redirects and so on), rendering views and much more.

You can have as many modules as you like in your application, just as long as there is at least one and that it has at least one route defined.
