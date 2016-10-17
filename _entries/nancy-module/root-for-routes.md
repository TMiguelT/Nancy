---
sectionclass: h2
sectionid: root-for-routes
parent-id: exploring-module
is-parent: no
number: 2200
title: Using modules to create a root for your routes
---

One of the small, yet neat, features of a module is the ability to define a module path. You can think of this as a root namespace for all the routes that are defined in the module. Each route will be subordinate to the path of the module. This saves you from having to repeat the common parts of the route patterns and also to nicely group your routes together based on their relationship

```c#
public class ResourceModule : NancyModule
{
    public ResourceModule() : base("/products")
    {
        // would capture routes to /products/list sent as a synchronous GET request
        Get["/list"] = parameters => {
            return "The list of products";
        };
    }
}
```
