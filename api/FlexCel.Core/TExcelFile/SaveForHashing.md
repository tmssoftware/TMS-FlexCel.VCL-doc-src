---
uid: TExcelFile.SaveForHashing
description: TExcelFile.SaveForHashing
---

# TExcelFile\.SaveForHashing Method

## Overloads

* [TExcelFile\.SaveForHashing\(TStream\)](#texcelfilesaveforhashingtstream)
* [TExcelFile\.SaveForHashing\(TStream, TExcludedRecordSet\)](#texcelfilesaveforhashingtstream-texcludedrecordset)

# TExcelFile\.SaveForHashing\(TStream\)
This method will save the file in a format that will remain the same if the file is not modified\. Normal xls files contain TimeStamp fields that might be modified when the file is downloaded or just copied\.

While you will not be able to load the file saved, you might use this method to create a hash of a file and compare it to others to know if something changed\.



This overload will not save cell selections or the active sheet, and it is equivalent to calling [SaveForHashing\(TStream, TExcludedRecordSet\)](SaveForHashing.md#texcelfilesaveforhashingtstream-texcludedrecordset) with the excludedRecords parameter set to TExcludedRecords\.All\. Use [SaveForHashing\(TStream, TExcludedRecordSet\)](SaveForHashing.md#texcelfilesaveforhashingtstream-texcludedrecordset) for more control on which records to exclude\.


## Remarks

This method will not save the file in any readable format, and **the file format might change between FlexCel versions\.** The only thing it guarantees is that the hashes for 2 identical xls files will be the same, for the same FlexCel version\. Once you upgrade version, hashes might have to be rebuilt\.


Also note that this method is useful to detect changes when the file is not edited in Excel\. If you open the file in Excel and save it again, Excel will change a lot of reserved bits, and the files will be too different for this method to have the same hashes\. This is only to detect changes when copying or downloading an xls file\. If you want to compare just cell contents, you might compare the files saved as CSV\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SaveForHashing(const aStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where the file will be saved\. You will probably want to hash this stream to store the corresponding hash\.|


## Examples

The following method will calculate the hash for an existing file:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetHash</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">): ByteArray;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ms: TMemoryStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ms := TMemoryStream.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.SaveForHashing(ms);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Save the file in a format without timestamps</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">       //or other data that might change from save to save.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">       //Note that the saved file is invalid, but we only care about its hash.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ms.Position := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ComputeHash(ms));  </span><span style="color:#008000;--shiki-dark:#6A9955">//ComputeHash is some function that computes some hash like an MD5 or SH256 on the data.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ms.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SaveForHashing\(TStream, TExcludedRecordSet\)
This method will save the file in a format that will remain the same if the file is not modified\. Normal xls files contain TimeStamp fields that might be modified when the file is downloaded or just copied\.

While you will not be able to load the file saved, you might use this method to create a hash of a file and compare it to others to know if something changed\.


## Remarks

This method will not save the file in any readable format, and **the file format might change between FlexCel versions\.** The only thing it guarantees is that the hashes for 2 identical xls files will be the same, for the same FlexCel version\. Once you upgrade version, hashes might have to be rebuilt\.


Also note that this method is useful to detect changes when the file is not edited in Excel\. If you open the file in Excel and save it again, Excel will change a lot of reserved bits, and the files will be too different for this method to have the same hashes\. This is only to detect changes when copying or downloading an xls file\. If you want to compare just cell contents, you might compare the files saved as CSV\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SaveForHashing(const aStream: TStream; const excludedRecords: <a href="../TExcludedRecords.md">Set of TExcludedRecords</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where the file will be saved\. You will probably want to hash this stream to store the corresponding hash\.|
|const|**excludedRecords**|[Set of TExcludedRecords](../TExcludedRecords.md)|A list with all the records you don't wish to include in the saved file \(like for example cell selection\)\. You will normally will want to  specify **TExcludedRecords\.All** here, but you can OR different members of the TExcludedRecords enumerations for more control on what is saved\.|


## Examples

The following method will calculate the hash for an existing file:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetHash</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">): ByteArray;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ms: TMemoryStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ms := TMemoryStream.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.SaveForHashing(ms);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Save the file in a format without timestamps</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">       //or other data that might change from save to save.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">       //Note that the saved file is invalid, but we only care about its hash.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ms.Position := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ComputeHash(ms));  </span><span style="color:#008000;--shiki-dark:#6A9955">//ComputeHash is some function that computes some hash like an MD5 or SH256 on the data.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ms.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

