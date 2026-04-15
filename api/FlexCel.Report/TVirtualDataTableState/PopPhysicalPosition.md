---
uid: TVirtualDataTableState.PopPhysicalPosition
description: TVirtualDataTableState.PopPhysicalPosition
---

# TVirtualDataTableState\.PopPhysicalPosition Method

This method is called when we need to ensure the position in the dataset is correct\. If the data is stateless \(like an array\), then this method can be empty\. For data with state \(like a TDataSet\) you need to save the position of the physical dataset in\<\#see PushPhysicalPosition> and restore it here\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.PopPhysicalPosition; virtual;</code></pre>

## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

