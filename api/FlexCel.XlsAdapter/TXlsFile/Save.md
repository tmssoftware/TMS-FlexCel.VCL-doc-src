---
uid: TXlsFile.Save
description: TXlsFile.Save
---

# TXlsFile\.Save Method

## Overloads

* [TXlsFile\.Save\(string, TFileFormats, Char, TEncoding\)](#txlsfilesavestring-tfileformats-char-tencoding)
* [TXlsFile\.Save\(TStream, TFileFormats, Char, TEncoding\)](#txlsfilesavetstream-tfileformats-char-tencoding)

# TXlsFile\.Save\(string, TFileFormats, Char, TEncoding\)
Saves the file to a disk\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.Save(const fileName: string; const fileFormat: <a href="../../FlexCel.Core/TFileFormats.md">TFileFormats</a>; const delimiter: Char; const fileEncoding: TEncoding); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to save\. If [TExcelFile.AllowOverwritingFiles](../../FlexCel.Core/TExcelFile/AllowOverwritingFiles.md) is false, then fileName MUST NOT exist\.|
|const|**fileFormat**|[TFileFormats](../../FlexCel.Core/TFileFormats.md)|File format\.  Automatic will try to guess it from the filename, if present\.|
|const|**delimiter**|Char|Delimiter to use if FileFormat is [TFileFormats.Text](../../FlexCel.Core/TFileFormats.md)|
|const|**fileEncoding**|TEncoding|Encoding for the generated file, when writing a Text\-delimited file \(csv or txt\)\.<br />This parameter has no effect on xls/x files\. If omitted, TUTF8EncodingNoBom\.Instance will be used\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Save\(TStream, TFileFormats, Char, TEncoding\)
Saves the file to a stream\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.Save(const aStream: TStream; const fileFormat: <a href="../../FlexCel.Core/TFileFormats.md">TFileFormats</a>; const delimiter: Char; const fileEncoding: TEncoding); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where to save the file\. Must be a seekable stream\.|
|const|**fileFormat**|[TFileFormats](../../FlexCel.Core/TFileFormats.md)|File format\. Automatic will try to guess it from the filename, if present\.|
|const|**delimiter**|Char|Delimiter to use if FileFormat is [TFileFormats.Text](../../FlexCel.Core/TFileFormats.md)|
|const|**fileEncoding**|TEncoding|Encoding for the generated file, when writing a Text\-delimited file \(csv or txt\)\.<br />This parameter has no effect on xls files\. If omitted, TUTF8EncodingNoBom\.Instance will be used\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

