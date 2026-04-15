---
uid: TClientAnchor.ChildAnchor
description: TClientAnchor.ChildAnchor
---

# TClientAnchor.ChildAnchor Field

Returns the offset on the parent system for the image, when it is grouped\.
For example, if the parent shape on the group is 100 px wide, and ChildAnchor has a dx of 0\.5, the image starts 50px to the right of the parent\. If the shape is not grouped  or it is the shape on top of the group, ChildAnchor is null\. When this member is not null, other values on ClientAnchor have no meaning\.


## Remarks

This offset is relative to the parent shape\. If there are 2 parent shapes before on the hierarchy, this object applies to the parent, not the grandparent\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs"><a href="../TClientAnchor/index.md">TClientAnchor</a>.ChildAnchor: <a href="../TChildAnchor/index.md">TChildAnchor</a>;</code></pre>

## See also

* [TClientAnchor](../TClientAnchor/index.md)

