---
sectionclass: h3
sectionid: defining-segment-constraints
parent-id: defining-routes
is-parent: yes
number: 3150
title: Route Segment Constraints
---
*Note: Route segment constraints was introduced in version 0.21*

Route segment constraints allows you apply certain constraints to your captured route segments. To apply a constraint to a segment, simply add a `:` followed by the name of the constraint to the route segment:

```csharp
Get["/intConstraint/{value:int}"] = parameters => "Value " + parameters.value + " is an integer.";
```

This will result in your route only getting hit if the value of the `value` segment is an integer.

The following constraints are available out of the box:

 - `int` - Allows only `Int32` (`int`) values.
 - `long` - Allows only `Int64` (`long`) values.
 - `decimal` - Allows only decimal values.
 - `guid` - Allows only GUID values.
 - `bool` - Allows only boolean values.
 - `alpha` - Allows only values containing alphabetical character.
 - `datetime` - Allows only date values, optionally containing time.
 - `datetime(format)` (**Added in 0.22**) - Allows only date and/or time values with the specified `format`. For format values, see [Custom Date and Time Format Strings](http://msdn.microsoft.com/en-us/library/8kb3ddd4.aspx)
 - `min(minimum)` - Allows only integer values with the specified `minimum` value.
 - `max(maximum)` - Allows only integer values with the specified `maximum` value.
 - `range(minimum, maximum)` - Allows only integer values within the specified range. (Between `minimum` and `maximum`)
 - `minlength(length)` - Allows only values longer than the specified minimum `length`.
 - `maxlength(length)` - Allows only values shorter that the maximum `length`.
 - `length(minimum, maximum)` - Allows only values with length within the specified range. (Between `minimum` and `maximum`)
 - `version` (**Added in 1.2**) - Allows only [`Version`](https://msdn.microsoft.com/en-us/library/system.version%28v=vs.110%29.aspx) values, e.g. `1.2.0`.
