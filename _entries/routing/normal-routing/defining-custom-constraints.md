---
sectionclass: h3
sectionid: defining-custom-constraints
parent-id: defining-routes
is-parent: yes
number: 3151
title: Custom Constraints
---

You can also implement your own, custom constraints. It's as easy as implementing `IRouteSegmentConstraint` and it will automatically be picked up by Nancy, SDHP-style. You can also derive your constraint from one of these convenience classes:

 - `RouteSegmentConstraintBase<T>` - Base class for a named constraint.
 - `ParameterizedRouteSegmentConstraintBase<T>` - Base class for a named constraint that accepts arguments.
