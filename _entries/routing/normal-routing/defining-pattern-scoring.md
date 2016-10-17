---
sectionclass: h3
sectionid: defining-pattern-scoring
parent-id: defining-routes
is-parent: no
number: 3130
title: Pattern Scoring
---

Sometimes you may end up with two routes which end up giving a positive match.

For example say we defined the following:

```csharp
public class HomeModule : NancyModule
    {
        public HomeModule()
        {
            Get["/{category}"] = parameters => "My category is " + parameters.category;

            Get["/sayhello"] = _ => "Hello from Nancy";

        }
    }
```

The first route contains a Captured Segment, while the second route is a Literal Segment.

When the routes are matched they get scored.

A literal has a score of `10000` while a capture has a score of `1000`, if both routes contain the same number of segments then the route with the highest score wins and that route is picked.

If we browse to the URL `http://www.site.com/sayhello` both routes would match and the 2nd route would score `10000` and that method will execute.
