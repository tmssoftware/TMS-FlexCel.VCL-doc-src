---
uid: TProtectedRange
description: TProtectedRange
---

# TProtectedRange Record

Specifies a protected range in a sheet\. You can define those ranges in Excel 2007 by going to "Review" tab and selecting "Allow Users to Edit Ranges" In Excel 2003, they are available under "Menu\->Tools\->Protection"\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TProtectedRange = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tprotectedrangecreate)<br />  [Create\(string, string, TXlsCellRangeArray\)](Create.md#tprotectedrangecreatestring-string-txlscellrangearray)<br />|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[Equals](Equals.md)|Returns true if the 2 objects have the same contents\.<br />|
|[GetHashCode](GetHashCode.md)|Return the hashcode of the object|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Password](Password.md)|Password used to protect the range\. Use empty or null to have no password\. **Note:** As this password is not saved in the file, when you open a file this property will be empty\. You can know if a file has a password by looking at [PasswordHash](PasswordHash.md)\.<br />Setting this property will set the [PasswordHash](PasswordHash.md) property using the current [EncryptionAlgorithm](EncryptionAlgorithm.md)\.<br />|
|[PasswordHash](PasswordHash.md)|This is the hash for the password that is stored in the file\. You shouldn't set this property directly unless you are copying the hash from other place\.<br />When you set this property, [Password](Password.md) will be reset\.<br />|
|[EncryptionAlgorithm](EncryptionAlgorithm.md)|Returns the encryption algorithm used to encrypt the password hash\.<br />|
|[Ranges](Ranges.md)|Ranges of cells this protection applies to\. You can specify more than one range of cells for the same ProtectedRange\.<br />|
|[Name](Name.md)|Name of the protected range\.<br />|
|[SecurityDescriptor&#8203;XLSX](SecurityDescriptorXLSX.md)|Returns the security descriptor of the protected range, for XLSX files\. This is a string used if you are giving permissions to some users in the range\.<br />Note that because of the different security descriptor formats, FlexCel won't convert between  security descriptors from xls and xlsx\. Take a look at APIMate to see the descriptor of a particular file\.<br />|
|[SecurityDescriptorXLS](SecurityDescriptorXLS.md)|Returns the security descriptor of the protected range, for XLS files\. This is a byte array encapsulating a Windows Security Descriptor, and it is used if you are giving permissions to some users in the range\.<br />Note that because of the different security descriptor formats, FlexCel won't convert between  security descriptors from xls and xlsx\. Take a look at APIMate to see the descriptor of a particular file\.<br />|


