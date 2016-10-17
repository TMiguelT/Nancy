---
sectionclass: h2
sectionid: run-anywhere
parent-id: introduction
is-parent: no
number: 1100
title: Built to Run Anywhere
---

Nancy is built to run anywhere and we mean it. Right from the start, Nancy was designed to not have any dependencies on existing frameworks. Built with the [.NET framework client profile](http://msdn.microsoft.com/en-us/library/cc656912.aspx), Nancy can be used pretty much wherever you want to, since it’s completely self contained with its own request and response objects.

One of the core concepts in Nancy is hosts. A host acts as an adaptor for a hosting environment and Nancy, thus enabling Nancy to run on existing technologies such as ASP.NET, WCF and [OWIN](http://owin.org), or integrated in any given application.

Specific host implementations are not shipped with the core Nancy framework. They are shipped separately, as are many other additional functionalities such as forms authentication, from the sources mentioned earlier. Building a Nancy application is like picking your favourite parts from a web framework buffet! Usually the bare minimum you will use when building a Nancy service are the core framework and a host.
