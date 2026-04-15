---
uid: TXlsFile.GroupObjects
description: TXlsFile.GroupObjects
---

# TXlsFile\.GroupObjects Method

Groups two or more objects\. The objects must be at the root level, you can't group objects inside a group\.
But you can group a group with other groups or objects\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.GroupObjects(const groupName: string; const anchorType: <a href="../../FlexCel.Core/TFlxAnchorType.md">TFlxAnchorType</a>; const objectIndexes: TArray&lt;Int32>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**groupName**|string|Name of the group\. You can keep it null to have a group without name\.|
|const|**anchorType**|[TFlxAnchorType](../../FlexCel.Core/TFlxAnchorType.md)|Anchor type for the group\. It defines how the group will behave when you insert, delete or resize cells\.|
|const|**objectIndexes**|TArray\<Int32>|List of objects to group\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

