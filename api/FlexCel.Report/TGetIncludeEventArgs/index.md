---
uid: TGetIncludeEventArgs
description: TGetIncludeEventArgs
---

# TGetIncludeEventArgs Class

Arguments passed on [TFlexCelReport.GetInclude](../TFlexCelReport/GetInclude.md)

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TGetIncludeEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[DataFile](DataFile.md)|The file with the report\.<br />|
|[FileName](FileName.md)|File we are trying to include\. you can modify it to point to other place\.<br />If the including file is a real file \(not an stream\) and FileName is relative, it will be relative to the including file path\.<br />|
|[IncludeData](IncludeData.md)|Here you can return the included file as an array of bytes\.<br />If you return null, the filename will be used to search for a file on the disk\.<br />If the including file is a real file \(not an stream\) and FileName is relative, it will be relative to the including file path\.<br />|


