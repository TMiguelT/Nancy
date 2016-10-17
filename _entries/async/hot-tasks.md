---
sectionclass: h2
sectionid: async-hot
parent-id: async
is-parent: no
number: 4400
title: Hot Tasks / 4.0 Support
---

While there is nothing in the async support that *requires* 4.5 async/await (it's not used internally and still targets .net 4), we *do* expect that Tasks returned by routes to be "hot" (already started) If you choose to use this using only the TPL or using RX, please ensure every task that's returned from the delegates is hot, or the request will likely never return.
