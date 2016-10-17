---
sectionclass: h3
sectionid: defining-secret
parent-id: defining-routes
is-parent: no
number: 3160
title: The Secret for Selecting the Right Route to Invoke
---

There are a couple of gotchas you should be aware of when it comes to the default behavior, in Nancy, for selecting which route to invoke for a request. It sounds easy enough, you pick the one that matches the `Method`, `Pattern` and `Condition` of the request, right? In the simplest case that is true and how it is selected, but what if things are a bit more complicated?

You could, for example, have two routes with patterns that would capture the same request under certain circumstances. These two routes could either be defined in the same module or split across several modules.

Turns out it’s not complicated after all, you just need to remember a couple of things

1. The order in which modules are loaded are non-deterministic in between application start-ups
2. Routes in a given module are discovered in the order in which they are defined
3. If there are several possible matches, the most specific match, i.e the route pattern that has the highest number of matching literal segments and fewest capture segments
4. If two, or more, routes are equal matches to a request, the first one is selected and which one this is depends on the module load order and the route order inside of the modules
