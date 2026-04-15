---
uid: TPrinterDriverSettings
description: TPrinterDriverSettings
---

# TPrinterDriverSettings Record

Printer specific settings\. It is a byte array with a Win32 DEVMODE struct\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TPrinterDriverSettings = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance of a TPrinterDriver&#8203;Settings class, with a COPY of aData|
|[GetData](GetData.md)|The current printer data as a byte stream\. The first 2 bytes are the operating system \(0=windows\) and the rest is a Win32 DEVMODE struct\.<br />|
|[Equals](Equals.md)|Returns true if two instances have the same data\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this instance\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


