---
uid: TProtection
description: TProtection
---

# TProtection Class

Encryption data for an Excel sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TProtection = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TProtection instance and initializes it\.<br />|


## Methods

|Name|Description|
|---|---|
|[SetModifyPassword](SetModifyPassword.md)|Sets the password for modifying the file\. It won't encrypt the file, it just won't let Excel save the file\. On Excel goto Options\->Security to check it\.<br />Note that you can only set it, there is no way to retrieve an existing password\.<br />|
|[SetWorkbookProtection](SetWorkbookProtection.md)|Protects the workbook\. On Excel goto Protect\->Workbook to check it\.<br />|
|[GetWorkbookProtection&#8203;Options](GetWorkbookProtectionOptions.md)|Reads the Workbook protection options for a file\.<br />|
|[SetWorkbookProtection&#8203;Options](SetWorkbookProtectionOptions.md)|Sets the workbook protection options for a file\.<br />|
|[SetSharedWorkbook&#8203;Protection](SetSharedWorkbookProtection.md)|Protects the change history from being removed\. On Excel goto Protect\->Protect Shared Workbook to check it\.<br />|
|[GetSharedWorkbook&#8203;Protection&#8203;Options](GetSharedWorkbookProtectionOptions.md)|Reads the protection options for the change history\.<br />|
|[SetSharedWorkbook&#8203;Protection&#8203;Options](SetSharedWorkbookProtectionOptions.md)|Sets the change history protection options for a file\.<br />|
|[SetSheetProtection](SetSheetProtection.md)|Protects a sheet\. On Excel goto Protect\->Sheet to check it\.<br />|
|[GetSheetProtection&#8203;Options](GetSheetProtectionOptions.md)|Return the sheet protection options for the file\.<br />|
|[SetSheetProtection&#8203;Options](SetSheetProtectionOptions.md)|Sets the sheet protection options for the file\.<br />|
|[GetProtectedRange](GetProtectedRange.md)|Returns a protected range\.<br />|
|[AddProtectedRange](AddProtectedRange.md)|Adds a protected range to the sheet\.<br />|
|[DeleteProtectedRange](DeleteProtectedRange.md)|Deletes an existing protected range\.<br />|
|[ClearProtectedRanges](ClearProtectedRanges.md)|Removes all protected ranges in the sheet\.<br />|
|[AssignedOnPassword](AssignedOnPassword.md)|Returns true is there is at least one event handler attached to then OnPassword event\.<br />|
|[RemoveAllOnPassword&#8203;Events](RemoveAllOnPasswordEvents.md)|Removes all event handlers attached to OnPassword\.<br />|


## Properties

|Name|Description|
|---|---|
|[EncryptionType](EncryptionType.md)|Encryption mode for xls files \.<br />|
|[EncryptionAlgorithm&#8203;Xlsx](EncryptionAlgorithmXlsx.md)|Encryption algorithm for xlsx files\.<br />|
|[OpenPassword](OpenPassword.md)|Sets the password to open the file\. When set, the file will be encrypted\. On Excel go to Options\->Security to check it\.<br />Set this to null to clear it\.<br />|
|[HasModifyPassword](HasModifyPassword.md)|Returns true if the file has a password to modify\.<br />|
|[RecommendReadOnly](RecommendReadOnly.md)|Returns true if the file is recommended to open read\-only\.<br />|
|[HasWorkbookPassword](HasWorkbookPassword.md)|Returns true if the workbook is protected with a password\.<br />|
|[HasSharedWorkbook&#8203;Password](HasSharedWorkbookPassword.md)|Returns true if the change history is protected with a password\.<br />|
|[HasSheetPassword](HasSheetPassword.md)|Returns true if the active sheet is protected with a password\.<br />|
|[WriteAccess](WriteAccess.md)|Reads or sets the user writing the file\. Useful to know which user opened the file in Excel when you want to save and the file is in use\.<br />|
|[ProtectedRangeCount](ProtectedRangeCount.md)|Returns a the count of protected ranges in the active sheet\.<br />|


## Events

|Name|Description|
|---|---|
|[OnPassword](OnPassword.md)|It is called when opening a password protected file, so you can supply the correct password\.<br />If you know beforehand that the file is protected you do not need this event, just use the [OpenPassword](OpenPassword.md) method on this object\.<br />|


