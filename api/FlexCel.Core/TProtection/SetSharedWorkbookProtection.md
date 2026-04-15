---
uid: TProtection.SetSharedWorkbookProtection
description: TProtection.SetSharedWorkbookProtection
---

# TProtection\.SetSharedWorkbookProtection Method

Protects the change history from being removed\. On Excel goto Protect\->Protect Shared Workbook to check it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TProtection/index.md">TProtection</a>.SetSharedWorkbookProtection(const sharedWorkbookPassword: string; const sharedWorkbookProtectionOptions: <a href="../TSharedWorkbookProtectionOptions/index.md">TSharedWorkbookProtectionOptions</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sharedWorkbookPassword**|string|Password to protect this setting\. You can set it to null to clear it\.|
|const|**sharedWorkbookProtectionOptions**|[TSharedWorkbook&#8203;Protection&#8203;Options](../TSharedWorkbookProtectionOptions/index.md)|The options to protect\.|


## See also

* [TProtection](../TProtection/index.md)

