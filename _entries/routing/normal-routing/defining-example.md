---
sectionclass: h4
sectionid: defining-example
parent-id: defining-custom-constraints
is-parent: no
number: 3151
title: Example
---

Here's an example implementation of an e-mail constraint (_although very simplified_):

```csharp
public class EmailRouteSegmentConstraint : RouteSegmentConstraintBase<string>
{
    public override string Name
    {
        get { return "email"; }
    }

    protected override bool TryMatch(string constraint, string segment, out string matchedValue)
    {
        if (segment.Contains("@"))
        {
            matchedValue = segment;
            return true;
        }

        matchedValue = null;
        return false;
    }
}
```

And usage:

```csharp
Get["/profile/{value:email}"] = parameters => "Value " + parameters.value + " is an e-mail address.";
```

This route will only get hit as long as the `value` segment contains a `@`. The value that's passed to the route is the value returned through the `matchedValue` out parameter.
