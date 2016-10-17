---
sectionclass: h3
sectionid: defining-pattern
parent-id: defining-routes
is-parent: no
number: 3120
title: Pattern
---

A route also needs a Pattern which declares the application-relative URL that the route answers to. The syntax of the Pattern is customizable but the default implementation that ships with Nancy supports capturing combinations of the following:

**Note:** Each pattern has a _score_, shown in parentheses - see "Pattern Scoring" below for what these mean.

1. **Literal segments** - (10,000) - `/some/literal/segments` which require an exact match.
2. **Capture segments** - (1,000) - `/{name}` which captures whatever is passed into the given segment of the requested URL and then passes it into the Action of the route.
3. **Capture segments *(optional)*** - (1,000) - `/{name?}` by adding the question mark at the end of the segment name the segment can be made optional.
4. **Capture Segments *(optional/default)*** - (1,000) - `/{name?unnamed}/` by adding a value after the question mark we can turn an optional segment into a segment with a default value, should the pattern be the most suited but the segment missing, the value returned will be what comes after the question mark.
5. **RegEx Segment** - (1,000) - `/(?<age>[\d]{1,2})` using [Named Capture Grouped](http://www.regular-expressions.info/named.html) Regular Expressions, you can get a little more control out of the segment pattern. If you don't need to capture anything then you can use a non-capturing group like `(?:regex-goes-here)`
6. **Greedy Segment** - (0) - `/{name*}` by adding a star/asterisk to the end of the segment name, the pattern will match any value from the current forward slash onward.
7. **Greedy RegEx Segment** - (100) - `^(?<name>[a-z]{3,10}(?:/{1})(?<action>[a-z]{5,10}))$` a segment composed of a RegEx and Greedy segment, this captures the entire path after the forward slash, The segment must start with `^` and end with `$` so we know the start/finish of the greedy regular expression segment.
7. **Multiple Captures Segment** - (100) - `/{file}.{extension}` or `/{file}.ext` a segment containing a mix of captures and literals.

Pattern segments can be combined, in any order, to create a complex Pattern for a route. It’s worth noting that capture segments are greedy, meaning they will match anything in the requested URL until another segment matches or until the end of the URL is reached.
