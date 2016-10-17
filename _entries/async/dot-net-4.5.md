---
sectionclass: h2
sectionid: async-dot-net-4.5
parent-id: async
is-parent: no
number: 4100
title: .NET 4.5 Targeting
---

If you're getting the error:

`Operator '+=' cannot be applied to operands of type 'Nancy.BeforePipeline' and 'lambda expression'
Cannot convert lambda expression to type 'Nancy.BeforePipeline' because it is not a delegate type`

Confirm that your project is targeting .NET 4.5 before starting to use the async/await keywords.
