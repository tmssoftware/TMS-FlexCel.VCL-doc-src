---
uid: TProtection.SetModifyPassword
description: TProtection.SetModifyPassword
---

# TProtection\.SetModifyPassword Method

Sets the password for modifying the file\. It won't encrypt the file, it just won't let Excel save the file\. On Excel goto Options\->Security to check it\.
Note that you can only set it, there is no way to retrieve an existing password\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TProtection/index.md">TProtection</a>.SetModifyPassword(const modifyPassword: string; const recommendReadOnly: Boolean; const reservingUser: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**modifyPassword**|string|The new password\. Set it to null to clear it\.|
|const|**recommendReadOnly**|Boolean|When true, Excel will recommend read only when opening a file\.|
|const|**reservingUser**|string|The user that reserves the file\. It will appear on the password dialog on Excel\.|


## See also

* [TProtection](../TProtection/index.md)

