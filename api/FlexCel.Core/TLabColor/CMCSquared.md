---
uid: TLabColor.CMCSquared
description: TLabColor.CMCSquared
---

# TLabColor\.CMCSquared Method

Returns the CMC color distance between this color and color2 \(distance returned is squared, so you need to get the sqrt if you want the real CMC value\)\. Note that CMC is not symmetric \(Color1\.CMC\(Color2\) \!= Color2\.CMC\(Color1\), so this color is the one used as reference\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TLabColor/index.md">TLabColor</a>.CMCSquared(const Color2: <a href="../TLabColor/index.md">TLabColor</a>; const l: Integer; const c: Integer): Double;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Color2**|[TLabColor](../TLabColor/index.md)|Color that will be compared against this reference\.|
|const|**l**|Integer|L parameter for CMC calculation\. For acceptability \(CMC2:1\) this is normally 2, and for perceptibility \(CMC1:1\) this should be 1\.|
|const|**c**|Integer|C parameter for CMC calculation\. This is normally 1\.|


## See also

* [TLabColor](../TLabColor/index.md)

