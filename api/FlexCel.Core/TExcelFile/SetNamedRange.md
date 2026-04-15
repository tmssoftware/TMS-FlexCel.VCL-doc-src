---
uid: TExcelFile.SetNamedRange
description: TExcelFile.SetNamedRange
---

# TExcelFile\.SetNamedRange Method

## Overloads

* [TExcelFile\.SetNamedRange\(TXlsNamedRange\)](#texcelfilesetnamedrangetxlsnamedrange)
* [TExcelFile\.SetNamedRange\(Integer, TXlsNamedRange\)](#texcelfilesetnamedrangeinteger-txlsnamedrange)

# TExcelFile\.SetNamedRange\(TXlsNamedRange\)
Modifies or adds a Named Range\. If the named range exists, it will be modified, else it will be added\.
If the range is not user defined \(like "Print\_Area"\) it will have a one\-char name, and the value is on the enum [TInternalNameRange](../TInternalNameRange.md) Look at the example for more information\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.SetNamedRange(const rangeData: <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**rangeData**|[TXlsNamedRange](../TXlsNamedRange/index.md)|Data of the named range\. You don't need to specify the RPN Array\.|


## Returns

The name index of the inserted or modified range \(1 based\)\.

## Examples

This will create a range for repeating the first 2 columns and rows on each printed page \(on sheet 1\):

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetNamedRange(TXlsNamedRange.Create(TXlsNamedRange.GetInternalName(TInternalNameRange.Print_Titles), SheetIndex, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'=1:2,A:B'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span></code></pre>

Note that in this example in particular \(Print\_Titles\), the range has to have full rows/columns, as this is what Excel expects\.
You should also use "A:B" notation instead of the full "A1:B65536" name, so it will work in Excel 2007 too\.


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetNamedRange\(Integer, TXlsNamedRange\)
Modifies a Named Range in the specified position\. You could normally use [SetNamedRange\(TXlsNamedRange\)](SetNamedRange.md#texcelfilesetnamedrangetxlsnamedrange) to do this, but if you want to modify the name of the named range, then you need to use this overloaded version\. [SetNamedRange\(TXlsNamedRange\)](SetNamedRange.md#texcelfilesetnamedrangetxlsnamedrange) would add a new range instead of modifying the existing one if you change the name\.
Look at the example for more information on how to use it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetNamedRange(const index: Integer; const rangeData: <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the named range we are trying to modify\.|
|const|**rangeData**|[TXlsNamedRange](../TXlsNamedRange/index.md)|Data of the named range\. You don't need to specify the RPN Array\.|


## Examples

This will modify the name of the named range "MyName":

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  printArea: TXlsNamedRange;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  nameIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  range: TXlsNamedRange;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  nameIndex := xls.FindNamedRange(</span><span style="color:#A31515;--shiki-dark:#CE9178">'MyName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Find the name index from the name.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  range := xls.GetNamedRange(nameIndex);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Load the name definition for the name index.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  range.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'MyNewName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Modify the name definition.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetNamedRange(nameIndex, range);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Set the new name definition into the file.</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

