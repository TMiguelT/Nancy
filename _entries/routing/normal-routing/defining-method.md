---
sectionclass: h3
sectionid: defining-method
parent-id: defining-routes
is-parent: no
number: 3110
title: Method
---

The Method is the [HTTP method](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) that is used to access the resource. Nancy supports the following methods `DELETE`, `GET`, `HEAD`, `OPTIONS`, `POST`, `PUT` and `PATCH`.

By default, `HEAD` requests are automatically handled for all routes that are declared for `GET` requests. If you want to manually handle `HEAD` requests, you can set `StaticConfiguration.EnableHeadRouting` to `true` and define the routes in your modules.
