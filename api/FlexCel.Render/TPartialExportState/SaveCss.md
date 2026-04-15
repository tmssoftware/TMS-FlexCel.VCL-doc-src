---
uid: TPartialExportState.SaveCss
description: TPartialExportState.SaveCss
---

# TPartialExportState\.SaveCss Method

## Overloads

* [TPartialExportState\.SaveCss\(TFlexCelWriter\)](#tpartialexportstatesavecsstflexcelwriter)
* [TPartialExportState\.SaveCss\(TFlexCelWriter, Boolean\)](#tpartialexportstatesavecsstflexcelwriter-boolean)

# TPartialExportState\.SaveCss\(TFlexCelWriter\)
Use this method to output the CSS information on this object to the header of an HTML page\. If you are using en external StyleSheet, this method will output a link to it, or if you are using an internal one it will output the actual classes\.
This overload will write the classes inside a \<style> tag\. To avoid writing the style tags, use the overload [SaveCss\(TFlexCelWriter, Boolean\)](SaveCss.md#tpartialexportstatesavecsstflexcelwriter-boolean)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPartialExportState/index.md">TPartialExportState</a>.SaveCss(const writer: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**writer**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|Writer where you are going to write the information\.|


## See also

* [TPartialExportState](../TPartialExportState/index.md)

# TPartialExportState\.SaveCss\(TFlexCelWriter, Boolean\)
Use this method to output the CSS information on this object to the header of an HTML page\. If you are using en external StyleSheet, this method will output a link to it, or if you are using an internal one it will output the actual classes\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPartialExportState/index.md">TPartialExportState</a>.SaveCss(const writer: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>; const includeStyleDefinition: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**writer**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|Writer where you are going to write the information\.|
|const|**includeStyleDefinition**|Boolean|If true, the css classes will be inside a \<style> tag\. If false, only the actual classes will be written\. This parameter has no effect if the StyleSheet is external\.|


## See also

* [TPartialExportState](../TPartialExportState/index.md)

