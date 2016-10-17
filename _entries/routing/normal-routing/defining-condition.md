---
sectionclass: h3
sectionid: defining-condition
parent-id: defining-routes
is-parent: no
number: 3150
title: Condition
---

The last part is an optional Condition that can be used to make sure that a route is only matched if certain conditions are met. This could e.g be a check to ensure that the route is only invoked if it was used by a mobile user-agent. A route condition is defined using a lambda expression of type `Func<NancyContext, bool>`.

```
Post["/login", (ctx) => ctx.Request.Form.remember] = _ =>
{
     return "Handling code when remember is true!";
};

Post["/login", (ctx) => !ctx.Request.Form.remember] = _ =>
{
     return "Handling code when remember is false!";
};
```
