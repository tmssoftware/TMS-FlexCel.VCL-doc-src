---
uid: TFlexCelPrintDocument.BeginPrint
description: TFlexCelPrintDocument.BeginPrint
---

# TFlexCelPrintDocument\.BeginPrint Method

Initializes the printing engine\. After calling this method you can call [PrintSheet](PrintSheet.md) to print different xls files, or [PrintAllVisibleSheets](PrintAllVisibleSheets.md)\. You should always end printing with a call to [EndPrint](EndPrint.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPrintDocument/index.md">TFlexCelPrintDocument</a>.BeginPrint(const VPrinter: TAbstractPrinter = nil);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**VPrinter**|TAbstractPrinter|**Optional**: Default value is nil<br /><br />An encapsulation of a TPrinter object\. Normally you will want to not specify this parameter or leave it nil\.<br />|


## See also

* [TFlexCelPrintDocument](../TFlexCelPrintDocument/index.md)

