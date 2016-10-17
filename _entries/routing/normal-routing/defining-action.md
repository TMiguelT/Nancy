---
sectionclass: h3
sectionid: defining-action
parent-id: defining-routes
is-parent: no
number: 3140
title: Action
---

A route Action is the behavior which is invoked when a request is matched to a route. It is represented by a lambda expression of type `Func<dynamic, dynamic>` where the dynamic input is a `DynamicDictionary`, a special dynamic type that is defined in Nancy and is covered in [[Taking a look at the DynamicDictionary]]

The response can be any model and the final result will be determined by [[Content Negotiation]]. However, if it is of the type `Response` then content negotiation will be ignored and the response will be sent straight back to the host.

The `Response` object declares several implicit cast operators which enables an action to also return, instead of a `Response` object, any of the following

1. `int` which will be interpreted as a HTTP status code of the response
2. `HttpStatusCode` enumerable value
3. `string` which will be interpreted as the body of the response
4. `Action<Stream>` which is a function that writes to the response stream
