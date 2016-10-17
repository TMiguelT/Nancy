---
sectionclass: h2
sectionid: async-syntax-example
parent-id: async
is-parent: no
number: 4300
title: Example
---

```c#
public MainModule()
{
    Before += async (ctx, ct) =>
        {
            this.AddToLog("Before Hook Delay\n");
            await Task.Delay(5000);

            return null;
        };

    After += async (ctx, ct) =>
        {
            this.AddToLog("After Hook Delay\n");
            await Task.Delay(5000);
            this.AddToLog("After Hook Complete\n");

            ctx.Response = this.GetLog();
        };

    Get["/", true] = async (x, ct) =>
        {
            this.AddToLog("Delay 1\n");
            await Task.Delay(1000);

            this.AddToLog("Delay 2\n");
            await Task.Delay(1000);

            this.AddToLog("Executing async http client\n");
            var client = new HttpClient();
            var res = await client.GetAsync("http://nancyfx.org");
            var content = await res.Content.ReadAsStringAsync();

            this.AddToLog("Response: " + content.Split('\n')[0] + "\n");

            return (Response)this.GetLog();
        };
}
```
