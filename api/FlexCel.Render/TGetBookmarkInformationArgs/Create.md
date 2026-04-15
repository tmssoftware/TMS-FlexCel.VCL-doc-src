---
uid: TGetBookmarkInformationArgs.Create
description: TGetBookmarkInformationArgs.Create
---

# TGetBookmarkInformationArgs\.Create Constructor

Creates a new Argument\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TGetBookmarkInformationArgs/index.md">TGetBookmarkInformationArgs</a>.Create(const aPdfWriter: <a href="../../FlexCel.Pdf/TPdfWriter/index.md">TPdfWriter</a>; const aCurrentPage: Integer; const aCurrentPageInSheet: Integer; const aBookmark: <a href="../../FlexCel.Pdf/TBookmark/index.md">TBookmark</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPdfWriter**|[TPdfWriter](../../FlexCel.Pdf/TPdfWriter/index.md)|The file we are processing\.|
|const|**aCurrentPage**|Integer|The page that is being generated\. 0 means the global bookmark parent of all the sheets\.|
|const|**aCurrentPageInSheet**|Integer|The page that is being generated, relative to the sheet\.|
|const|**aBookmark**|[TBookmark](../../FlexCel.Pdf/TBookmark/index.md)|Bookmark that we are about to include\. you can customize it on this event\.|


## See also

* [TGetBookmarkInformationArgs](../TGetBookmarkInformationArgs/index.md)

