---
uid: TImageUtils.GetImageType
description: TImageUtils.GetImageType
---

# TImageUtils\.GetImageType Method

## Overloads

* [TImageUtils\.GetImageType\(TBytes\)](#timageutilsgetimagetypetbytes)
* [TImageUtils\.GetImageType\(TStream\)](#timageutilsgetimagetypetstream)
* [TImageUtils\.GetImageType\(TBytes, Integer\)](#timageutilsgetimagetypetbytes-integer)

# TImageUtils\.GetImageType\(TBytes\)
Returns the image type for a byte array\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TImageUtils/index.md">TImageUtils</a>.GetImageType(const data: TBytes): <a href="../TXlsImgType.md">TXlsImgType</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Array with the image\.|


## Returns

Image type

## See also

* [TImageUtils](../TImageUtils/index.md)

# TImageUtils\.GetImageType\(TStream\)
Returns the image type for a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TImageUtils/index.md">TImageUtils</a>.GetImageType(const st: TStream): <a href="../TXlsImgType.md">TXlsImgType</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**st**|TStream|A stream\.|


## Returns

The image type\.

## See also

* [TImageUtils](../TImageUtils/index.md)

# TImageUtils\.GetImageType\(TBytes, Integer\)
Returns the image type for a byte array\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TImageUtils/index.md">TImageUtils</a>.GetImageType(const data: TBytes; const position: Integer): <a href="../TXlsImgType.md">TXlsImgType</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Array with the image\.|
|const|**position**|Integer|Position on data where the image begins\.|


## Returns

Image type

## See also

* [TImageUtils](../TImageUtils/index.md)

