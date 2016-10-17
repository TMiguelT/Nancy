---
sectionclass: h2
sectionid: first-application
parent-id: introduction
is-parent: no
number: 1300
title: Creating Your First Nancy Application
---
Enough talk, let’s see some code! We are going to assume that you have [Nuget](http://nuget.org) installed and are using Visual Studio 2010, however, this works equally as well on [Mono](http://mono-project.com) (using version 2.10.2 or later) and [MonoDevelop](http://monodevelop.com). We’re going to build the ubiquitous “hello world” application using Nancy and Nancy’s ASP.NET hosting.

1. If using Visual Studio 2012 or greater, install the [SideWaffle Template Pack for Visual Studio](http://sidewaffle.com/). Visual Studio 2010 users can install the [Nancy project templates](http://visualstudiogallery.msdn.microsoft.com/f1e29f61-4dff-4b1e-a14b-6bd0d307611a).
1. Create a new `Nancy empty project with ASP.NET host` if using SideWaffle. Create a new `Nancy Empty Web Application with ASP.NET Hosting` if using the Nancy Project templates.
1. Add a `Nancy module`, which is a standard C# class, and define a route handler for the root URL of the web application, by adding a small amount of code to the constructor:
1. Compile and run to see the result!
1. While recommended but not required, Use the NuGet Package Manager to check for any new Updates.

The HelloModule.cs code

```c#
public class HelloModule : NancyModule
{
    public HelloModule()
    {
        Get["/"] = parameters => "Hello World";
    }
}
```
It is important that you declare your module public, otherwise NancyFx is not able to discover your module.
