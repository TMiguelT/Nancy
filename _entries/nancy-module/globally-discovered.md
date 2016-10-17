---
sectionclass: h2
sectionid: globally-discovered
parent-id: exploring-module
is-parent: no
number: 2100
title: Modules are globally discovered
---

Modules can be declared anywhere you like, just as long as they are available in the application domain at runtime. Nancy will scan and identify all types that are descendants of the NancyModule type.

This means that you could, for example, define modules in external assemblies. As long as the assembly exists in the application domain at runtime - either through a reference or dynamically loaded - it will be scanned. You could leverage this to reuse behavior across applications, you could even create a nice little nuget for it.

If you think that the scanning sounds expensive, don’t worry. This does not happen on each request to the application, it is part of the startup of any Nancy application and is only performed once and the information is then cached.
