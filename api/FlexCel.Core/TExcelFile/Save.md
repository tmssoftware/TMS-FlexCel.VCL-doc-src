---
uid: TExcelFile.Save
description: TExcelFile.Save
---

# TExcelFile\.Save Method

## Overloads

* [TExcelFile\.Save\(string\)](#texcelfilesavestring)
* [TExcelFile\.Save\(TStream\)](#texcelfilesavetstream)
* [TExcelFile\.Save\(string, TFileFormats\)](#texcelfilesavestring-tfileformats)
* [TExcelFile\.Save\(TStream, TFileFormats\)](#texcelfilesavetstream-tfileformats)
* [TExcelFile\.Save\(string, TFileFormats, Char\)](#texcelfilesavestring-tfileformats-char)
* [TExcelFile\.Save\(TStream, TFileFormats, Char\)](#texcelfilesavetstream-tfileformats-char)
* [TExcelFile\.Save\(string, TFileFormats, Char, TEncoding\)](#texcelfilesavestring-tfileformats-char-tencoding)
* [TExcelFile\.Save\(TStream, TFileFormats, Char, TEncoding\)](#texcelfilesavetstream-tfileformats-char-tencoding)

# TExcelFile\.Save\(string\)
Saves the file to disk, on native format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const fileName: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to save\. If [AllowOverwritingFiles](AllowOverwritingFiles.md) is false, then fileName MUST NOT exist\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Save\(TStream\)
Saves the file to a stream, on native format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const aStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where to save the file\. Must be a seekable stream\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Save\(string, TFileFormats\)
Saves the file to a disk\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const fileName: string; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to save\. If [AllowOverwritingFiles](AllowOverwritingFiles.md) is false, then fileName MUST NOT exist\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|File format\. If file format is text, a tab will be used as delimiter\.  Automatic will try to guess it from the filename, if present\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Save\(TStream, TFileFormats\)
Saves the file to a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const aStream: TStream; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where to save the file\. Must be a seekable stream\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|File format\. If file format is text, a tab will be used as delimiter\.  Automatic will try to guess it from the filename, if present\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Save\(string, TFileFormats, Char\)
Saves the file to a disk\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const fileName: string; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to save\. If [AllowOverwritingFiles](AllowOverwritingFiles.md) is false, then fileName MUST NOT exist\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|File format\. Automatic will try to guess it from the filename, if present\.|
|const|**delimiter**|Char|Delimiter to use if FileFormat is [TFileFormats.Text](../TFileFormats.md)|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Save\(TStream, TFileFormats, Char\)
Saves the file to a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const aStream: TStream; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where to save the file\. Must be a seekable stream\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|File format\. Automatic will try to guess it from the filename, if present\.|
|const|**delimiter**|Char|Delimiter to use if FileFormat is [TFileFormats.Text](../TFileFormats.md)|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Save\(string, TFileFormats, Char, TEncoding\)
Saves the file to a disk\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const fileName: string; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const fileEncoding: TEncoding); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to save\. If [AllowOverwritingFiles](AllowOverwritingFiles.md) is false, then fileName MUST NOT exist\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|File format\.  Automatic will try to guess it from the filename, if present\.|
|const|**delimiter**|Char|Delimiter to use if FileFormat is [TFileFormats.Text](../TFileFormats.md)|
|const|**fileEncoding**|TEncoding|Encoding for the generated file, when writing a Text\-delimited file \(csv or txt\)\.<br />This parameter has no effect on xls/x files\. If omitted, TUTF8EncodingNoBom\.Instance will be used\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Save\(TStream, TFileFormats, Char, TEncoding\)
Saves the file to a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Save(const aStream: TStream; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const fileEncoding: TEncoding); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where to save the file\. Must be a seekable stream\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|File format\. Automatic will try to guess it from the filename, if present\.|
|const|**delimiter**|Char|Delimiter to use if FileFormat is [TFileFormats.Text](../TFileFormats.md)|
|const|**fileEncoding**|TEncoding|Encoding for the generated file, when writing a Text\-delimited file \(csv or txt\)\.<br />This parameter has no effect on xls files\. If omitted, TUTF8EncodingNoBom\.Instance will be used\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

