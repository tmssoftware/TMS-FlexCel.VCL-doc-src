---
uid: TFlexCelReport.Run
description: TFlexCelReport.Run
---

# TFlexCelReport\.Run Method

## Overloads

* [TFlexCelReport\.Run\(TExcelFile\)](#tflexcelreportruntexcelfile)
* [TFlexCelReport\.Run\(string, string\)](#tflexcelreportrunstring-string)
* [TFlexCelReport\.Run\(TStream, TStream\)](#tflexcelreportruntstream-tstream)
* [TFlexCelReport\.Run\(TStream, TStream, TFileFormats\)](#tflexcelreportruntstream-tstream-tfileformats)

# TFlexCelReport\.Run\(TExcelFile\)
Executes the report, reading from an ExcelFile and writing the results to it again\.


## Remarks

Note that [RecalcMode](RecalcMode.md), [SemiAbsoluteReferences](SemiAbsoluteReferences.md)[RecalcVersion](RecalcVersion.md) and [AllowOverwritingFiles](AllowOverwritingFiles.md) values used will be the ones on  aWorkbook, not the ones on this report\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.Run(const aWorkbook: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aWorkbook**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|ExcelFile that contains the template file, and that will contain the generated file once this method runs\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.Run\(string, string\)
Executes the report, reading from a file and writing to a file\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.Run(const templateFileName: string; const outFileName: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**templateFileName**|string|File with the template to use\.|
|const|**outFileName**|string|File to create\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.Run\(TStream, TStream\)
Executes the report, reading from a stream and writing to a stream\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.Run(const templateStream: TStream; const outStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**templateStream**|TStream|Stream with the template\.|
|const|**outStream**|TStream|Stream where the result will be written\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.Run\(TStream, TStream, TFileFormats\)
Executes the report, reading from a stream and writing to a stream\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.Run(const templateStream: TStream; const outStream: TStream; const fileFormat: <a href="../../FlexCel.Core/TFileFormats.md">TFileFormats</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**templateStream**|TStream|Stream with the template\.|
|const|**outStream**|TStream|Stream where the result will be written\.|
|const|**fileFormat**|[TFileFormats](../../FlexCel.Core/TFileFormats.md)|File format in which the resulting file will be saved\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

