---
uid: TProtectedRange.Password
description: TProtectedRange.Password
---

# TProtectedRange.Password Property

Password used to protect the range\. Use empty or null to have no password\. **Note:** As this password is not saved in the file, when you open a file this property will be empty\. You can know if a file has a password by looking at [PasswordHash](PasswordHash.md)\.
Setting this property will set the [PasswordHash](PasswordHash.md) property using the current [EncryptionAlgorithm](EncryptionAlgorithm.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TProtectedRange/index.md">TProtectedRange</a>.Password: string</code></pre>

## See also

* [TProtectedRange](../TProtectedRange/index.md)

