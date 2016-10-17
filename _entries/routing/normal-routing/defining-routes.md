---
sectionclass: h2
sectionid: defining-routes
parent-id: routing
is-parent: yes
number: 3100
title: Defining Routes
---
*Note: This applies to Nancy 0.17.0 onwards, if you're still using a previous version of Nancy please refer to [Legacy Routing](#legacy-routing)*

Routes are defined in the constructor of a module. In order to define a route in Nancy, you need to specify a `Method` + `Pattern` + `Action` + (optional) `Condition`.

i.e
```c#
public class ProductsModule : NancyModule
{
    public ProductsModule()
    {
        Get["/products/{id}"] = _ =>
        {
            //do something
        };
    }
}
```

or async:

```c#
public class ProductsModule : NancyModule
{
    public ProductsModule()
    {
        Get["/products/{id}", runAsync: true] = async (_, token) =>
        {
            //do something long and tedious
        };
    }
}
```





[<< Part 2. Exploring the Nancy module](Exploring the Nancy module) - [Documentation overview](Documentation) - [Part 3. Custom routing >>](Custom Routing)
