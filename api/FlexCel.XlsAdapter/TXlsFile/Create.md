---
uid: TXlsFile.Create
description: TXlsFile.Create
---

# TXlsFile\.Create Constructor

## Overloads

* [TXlsFile\.Create](#txlsfilecreate)
* [TXlsFile\.Create\(Boolean\)](#txlsfilecreateboolean)
* [TXlsFile\.Create\(string\)](#txlsfilecreatestring)
* [TXlsFile\.Create\(string, Boolean\)](#txlsfilecreatestring-boolean)
* [TXlsFile\.Create\(Integer, Boolean\)](#txlsfilecreateinteger-boolean)
* [TXlsFile\.Create\(TStream, Boolean\)](#txlsfilecreatetstream-boolean)
* [TXlsFile\.Create\(Integer, TExcelFileFormat, Boolean\)](#txlsfilecreateinteger-texcelfileformat-boolean)

# TXlsFile\.Create
Creates a new XlsFile\. After creating an XlsFile with this constructor, you need to either open or create a new file\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TXlsFile/index.md">TXlsFile</a>.Create;</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Create\(Boolean\)
Creates a new XlsFile and sets the desired Overwriting mode for files\. After creating an XlsFile with this constructor, you need to either open or create a new file\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TXlsFile/index.md">TXlsFile</a>.Create(const aAllowOverwritingFiles: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aAllowOverwritingFiles**|Boolean|When true calling "Save" will overwrite existing files\. See [TExcelFile.AllowOverwritingFiles](../../FlexCel.Core/TExcelFile/AllowOverwritingFiles.md)|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Create\(string\)
Creates a new XlsFile and opens the desired file\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TXlsFile/index.md">TXlsFile</a>.Create(const aFileName: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFileName**|string|Name of the file to open\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Create\(string, Boolean\)
Creates a new XlsFile and opens the desired file\. Sets the desired Overwriting mode for files\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TXlsFile/index.md">TXlsFile</a>.Create(const aFileName: string; const aAllowOverwritingFiles: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFileName**|string|Name of the file to open\.|
|const|**aAllowOverwritingFiles**|Boolean|When true calling "Save" will overwrite existing files\. See [TExcelFile.AllowOverwritingFiles](../../FlexCel.Core/TExcelFile/AllowOverwritingFiles.md)|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Create\(Integer, Boolean\)
Creates a new XlsFile and creates a new empty file with the desired number of sheets\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TXlsFile/index.md">TXlsFile</a>.Create(const aSheetCount: Integer; const aAllowOverwritingFiles: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetCount**|Integer|Number of sheets for the new empty file\.|
|const|**aAllowOverwritingFiles**|Boolean|When true calling "Save" will overwrite existing files\. See [TExcelFile.AllowOverwritingFiles](../../FlexCel.Core/TExcelFile/AllowOverwritingFiles.md)|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Create\(TStream, Boolean\)
Creates a new XlsFile and opens the desired file from a stream\. Sets the desired Overwriting mode for files\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TXlsFile/index.md">TXlsFile</a>.Create(const aStream: TStream; const aAllowOverwritingFiles: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream with the file to open\.|
|const|**aAllowOverwritingFiles**|Boolean|When true calling "Save" will overwrite existing files\. See [TExcelFile.AllowOverwritingFiles](../../FlexCel.Core/TExcelFile/AllowOverwritingFiles.md)|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Create\(Integer, TExcelFileFormat, Boolean\)
Creates a new XlsFile and creates a new empty file with the desired number of sheets and file format\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TXlsFile/index.md">TXlsFile</a>.Create(const aSheetCount: Integer; const aFileFormat: <a href="../../FlexCel.Core/TExcelFileFormat.md">TExcelFileFormat</a>; const aAllowOverwritingFiles: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetCount**|Integer|Number of sheets for the new empty file\.|
|const|**aFileFormat**|[TExcelFileFormat](../../FlexCel.Core/TExcelFileFormat.md)|Version of Excel used to create the new file\. Different version can have different default fonts, column widths, etc\.|
|const|**aAllowOverwritingFiles**|Boolean|When true calling "Save" will overwrite existing files\. See [TExcelFile.AllowOverwritingFiles](../../FlexCel.Core/TExcelFile/AllowOverwritingFiles.md)|


## See also

* [TXlsFile](../TXlsFile/index.md)

