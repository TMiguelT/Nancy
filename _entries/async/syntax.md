---
sectionclass: h2
sectionid: async-syntax
parent-id: async
is-parent: no
number: 4200
title: Syntax
---

Both the Before/After pipelines, and the main route delegates, can be specified as async. The syntax is *almost* identical to the sync code, but with the following changes:

* The before and after hooks take two parameters, context and a cancellation token, rather than just the context.
* The route definition has an additional boolean parameter, and the delegate takes two parameters, the captured params, and the cancellation token.
