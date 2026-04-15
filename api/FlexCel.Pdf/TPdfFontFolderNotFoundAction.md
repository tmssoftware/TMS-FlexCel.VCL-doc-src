---
uid: TPdfFontFolderNotFoundAction
description: TPdfFontFolderNotFoundAction
---

# TPdfFontFolderNotFoundAction Enumeration

Determines what FlexCel should do when a font folder doesn't exist\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|DefaultBehavior|0|This event won't change how the action is handled\. If you set for example a static property to "Error" and an instance property to "DefaultBehavior", the final result will be "Error"\. If all properties are set to DefaultBehavior, this property will work as "Ignore"|
|Ignore|1|FlexCel will ignore the folders that don't exist, and keep searching the other font folders you specified\.<br />Note that at least one folder in the list of folders must exist, or FlexCel will raise an error anyway\.<br />|
|Error|2|FlexCel will throw an exception if any folder doesn't exist\.<br />|


