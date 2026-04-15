---
uid: TPdfWriter.SetBookmarks
description: TPdfWriter.SetBookmarks
---

# TPdfWriter\.SetBookmarks Method

Replaces the bookmarks on the file with other list\. The new list will be copied, so you can change the old list after setting it and it will not affect the file\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.SetBookmarks(const bookmarks: <a href="../TBookmarkList/index.md">TBookmarkList</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**bookmarks**|[TBookmarkList](../TBookmarkList/index.md)|List to replace\. If null, bookmarks will be cleared\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

