---
uid: TExcelFile.CheckDataValidation
description: TExcelFile.CheckDataValidation
---

# TExcelFile\.CheckDataValidation Method

## Overloads

* [TExcelFile\.CheckDataValidation\(Integer, Integer\)](#texcelfilecheckdatavalidationinteger-integer)
* [TExcelFile\.CheckDataValidation\(Integer, Integer, TCellValue, Boolean\)](#texcelfilecheckdatavalidationinteger-integer-tcellvalue-boolean)

# TExcelFile\.CheckDataValidation\(Integer, Integer\)
Checks if the data in the cells where the data validation applies conforms to the data validation specifications\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CheckDataValidation(const index: Integer; const maxErrors: Integer): <a href="../TCellAddress/index.md">TArray&lt;TCellAddress></a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position in the list of data validations\. \(1 based\)|
|const|**maxErrors**|Integer|The maximum number of errors reported by this method\. To avoid getting a too big list, set it to a number like 100\. If set to 0 or a negative number, the full list of errors will be returned, which can be very big\.|


## Returns

An array with the first maxErrors cells that do not conform to the data validation\. And empty array if all the cells conform\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.CheckDataValidation\(Integer, Integer, TCellValue, Boolean\)
Returns \-1 if the value complies with all the data validations at the cell in row, col, or the position of the data validation that causes the error if the value is not valid\. The position returned is 1 based, and you can use  [GetDataValidationInfo](GetDataValidationInfo.md) to get all information of the data validation\.


When the parameter setIsValid is true and the data is valid, then this will also set the cell to value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CheckDataValidation(const row: Integer; const col: Integer; const value: <a href="../TCellValue/index.md">TCellValue</a>; const setIfValid: Boolean): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row for the cell where we would like to enter the value\. \(1 based\)|
|const|**col**|Integer|Column for the cell where we would like to enter the value\. \(1 based\)|
|const|**value**|[TCellValue](../TCellValue/index.md)|Value that we want to check if valid\.|
|const|**setIfValid**|Boolean|When true, the we will also set the cell value if the condition is valid\. When false,  we will only check if the value is valid, but keep the old value on the cell\.|


## Returns

\-1 if the value is valid for the cell according with the data validations on it, the position of the data validation causing the error otherwise\. The position returned is 1 based, and you can use  [GetDataValidationInfo](GetDataValidationInfo.md) to get all information of the data validation\.

## Examples

To set a value in a cell if valid, and if not show the error associated to this data validation, you could use code like:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(sourceFileName, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.ActiveSheetByName := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Sheet With Data'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    dv := xls.CheckDataValidation(row, col, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$B</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//We will try to enter the number 11 at cell (row, col).</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> dv > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#008000;--shiki-dark:#6A9955">  //There was an error. The cell value is not modified</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      dvInfo := xls.GetDataValidationInfo(dv);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      LogMessage(dvInfo.ErrorBoxText);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

