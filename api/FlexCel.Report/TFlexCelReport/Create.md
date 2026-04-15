---
uid: TFlexCelReport.Create
description: TFlexCelReport.Create
---

# TFlexCelReport\.Create Constructor

## Overloads

* [TFlexCelReport\.Create](#tflexcelreportcreate)
* [TFlexCelReport\.Create\(Boolean\)](#tflexcelreportcreateboolean)
* [TFlexCelReport\.Create\(Integer, string, TDataSourceInfoList, TFlexCelReport\)](#tflexcelreportcreateinteger-string-tdatasourceinfolist-tflexcelreport)

# TFlexCelReport\.Create
Creates a new FlexCelReport component\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.Create;</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.Create\(Boolean\)
Creates a new FlexCelReport component and sets the desired Overwrite mode for files\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.Create(const aAllowOverwritingFiles: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aAllowOverwritingFiles**|Boolean|If false, FlexCelReport will never overwrite an existing file, and you have to delete it before creating it again\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)
* [AllowOverwritingFiles](AllowOverwritingFiles.md)

# TFlexCelReport\.Create\(Integer, string, TDataSourceInfoList, TFlexCelReport\)
Creates a new FlexCelReport component to be used on \#include tags\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.Create(const aNestedIncludeLevel: Integer; const tagText: string; const dsInfoList: TDataSourceInfoList; const parentReport: <a href="../TFlexCelReport/index.md">TFlexCelReport</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aNestedIncludeLevel**|Integer||
|const|**tagText**|string||
|const|**dsInfoList**|TDataSourceInfoList||
|const|**parentReport**|[TFlexCelReport](../TFlexCelReport/index.md)||


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

