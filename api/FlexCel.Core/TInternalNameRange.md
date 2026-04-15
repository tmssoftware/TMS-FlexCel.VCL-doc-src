---
uid: TInternalNameRange
description: TInternalNameRange
---

# TInternalNameRange Enumeration

List of internal range names\.
On Excel, internal range names like "Print\_Area" are stored as a 1 character string\.
This is the list of the names and their value\.
You can convert an InternalNameRange into a string by casting it to a char, or by calling [TXlsNamedRange.GetInternalName](TXlsNamedRange/GetInternalName.md)


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Consolidate\_Area|0|Consolidate\_Area|
|Auto\_Open|1|Auto\_Open|
|Auto\_Close|2|Auto\_Close|
|Extract|3|Extract|
|Database|4|Database|
|Criteria|5|Criteria|
|Print\_Area|6|Print\_Area|
|Print\_Titles|7|Print\_Titles|
|Recorder|8|Recorder|
|Data\_Form|9|Data\_Form|
|Auto\_Activate|10|Auto\_Activate|
|Auto\_Deactivate|11|Auto\_Deactivate|
|Sheet\_Title|12|Sheet\_Title|
|Filter\_DataBase|13|Used in AutoFilters\.|


## Examples

To get the print range on the ActiveSheet, use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  printArea := xls.GetNamedRange(TXlsNamedRange.GetInternalName(TInternalNameRange.Print_Area), xls.ActiveSheet);</span></span>
<span class="line"></span></code></pre>



