---
uid: TExcelFile.GroupObjects
description: TExcelFile.GroupObjects
---

# TExcelFile\.GroupObjects Method

## Overloads

* [TExcelFile\.GroupObjects\(Int32Array\)](#texcelfilegroupobjectsint32array)
* [TExcelFile\.GroupObjects\(string, TFlxAnchorType, Int32Array\)](#texcelfilegroupobjectsstring-tflxanchortype-int32array)

# TExcelFile\.GroupObjects\(Int32Array\)
Groups two or more objects\. The objects must be at the root level, you can't group objects inside a group\.
But you can group a group with other groups or objects\.
This overload will group the objects without a group name, and with the the MoveAndResize anchor type\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.GroupObjects(const objectIndexes: TArray&lt;Int32>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndexes**|TArray\<Int32>|List of objects to group\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GroupObjects\(string, TFlxAnchorType, Int32Array\)
Groups two or more objects\. The objects must be at the root level, you can't group objects inside a group\.
But you can group a group with other groups or objects\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.GroupObjects(const groupName: string; const anchorType: <a href="../TFlxAnchorType.md">TFlxAnchorType</a>; const objectIndexes: TArray&lt;Int32>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**groupName**|string|Name of the group\. You can keep it null to have a group without name\.|
|const|**anchorType**|[TFlxAnchorType](../TFlxAnchorType.md)|Anchor type for the group\. It defines how the group will behave when you insert, delete or resize cells\.|
|const|**objectIndexes**|TArray\<Int32>|List of objects to group\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

