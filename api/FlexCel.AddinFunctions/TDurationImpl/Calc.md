---
uid: TDurationImpl.Calc
description: TDurationImpl.Calc
---

# TDurationImpl\.Calc Method

Duration/MDuration implementation\. You can call this method on its own\.


## Syntax

**Unit:** [FlexCel.AddinFunctions](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDurationImpl/index.md">TDurationImpl</a>.Calc(const Modified: Boolean; const SettlementDate: TDateTime; const MaturityDate: TDateTime; const CouponRate: Double; const Yield: Double; const Frequency: Double; const Basis: <a href="../TDayCountBasis.md">TDayCountBasis</a>): <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Modified**|Boolean|If true, we return MDuration, if not, Duration\.|
|const|**SettlementDate**|TDateTime|See Excel\.|
|const|**MaturityDate**|TDateTime|See Excel\.|
|const|**CouponRate**|Double|See Excel\.|
|const|**Yield**|Double|See Excel\.|
|const|**Frequency**|Double|See Excel\.|
|const|**Basis**|[TDayCountBasis](../TDayCountBasis.md)|See Excel\.|


## See also

* [TDurationImpl](../TDurationImpl/index.md)

