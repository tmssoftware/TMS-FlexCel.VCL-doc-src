---
uid: TProtectedRange.SecurityDescriptorXLS
description: TProtectedRange.SecurityDescriptorXLS
---

# TProtectedRange.SecurityDescriptorXLS Property

Returns the security descriptor of the protected range, for XLS files\. This is a byte array encapsulating a Windows Security Descriptor, and it is used if you are giving permissions to some users in the range\.
Note that because of the different security descriptor formats, FlexCel won't convert between  security descriptors from xls and xlsx\. Take a look at APIMate to see the descriptor of a particular file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TProtectedRange/index.md">TProtectedRange</a>.SecurityDescriptorXLS: TArray&lt;Byte&gt;</code></pre>

## See also

* [TProtectedRange](../TProtectedRange/index.md)

