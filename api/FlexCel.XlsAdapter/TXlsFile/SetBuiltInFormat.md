---
uid: TXlsFile.SetBuiltInFormat
description: TXlsFile.SetBuiltInFormat
---

# TXlsFile\.SetBuiltInFormat Method

Excel has 49 predefined formats which aren't stored in the xls/x file, only the format id is stored\.

When opening the file in Excel, the cells formatted with those internal formats will be formatted according to the language and version of Excel, not all of them return the same\. For example, some Excel versions will display format 38 as `"#,##0 ;[Red](#,##0) "` \(negative numbers in parenthesis\) while others will display the same format 38 as `"#,##0 _$;[Red]-#,##0 _$"` \(negative numbers have "\-" sign\)\.


FlexCel by default comes with the following formats defined, which correspond to an English Excel 2010:
|ID|Format code|
|---|---|
|1|0|
|2|0\.00|
|3|\#,\#\#0|
|4|\#,\#\#0\.00|
|9|0%%|
|10|0\.00%%|
|11|0\.00E\+00|
|12|\# ?/?|
|13|\# ??/??|
|14|Value read from the Windows Settings, and corresponds to formats marked with an "\*" in Excel\. It is something like "mm/dd/yyyy" or "dd/mm/yyyy" depending on your Windows locale\.<br />You can't change this value from here, as it is automatically generated from your Windows settings\. If you want to change it, change the Locale of your app instead\.|
|15|d\-mmm\-yy|
|16|d\-mmm|
|17|mmm\-yy|
|18|h:mm AM/PM|
|19|h:mm:ss AM/PM|
|20|h:mm|
|21|h:mm:ss|
|22|Value read from the Windows Settings, and corresponds to formats marked with an "\*" in Excel\. It is something like "mm/dd/yyyy h:mm" or "dd/mm/yyyy h:mm" depending on your Windows locale\.<br />You can't change this value from here, as it is automatically generated from your Windows settings\. If you want to change it, change the Locale of your app instead\.|
|37|\#,\#\#0 \_$;\-\#,\#\#0 \_$|
|38|\#,\#\#0 \_$;\[Red\]\-\#,\#\#0 \_$|
|39|\#,\#\#0\.00 \_$;\-\#,\#\#0\.00 \_$|
|40|\#,\#\#0\.00 \_$;\[Red\]\-\#,\#\#0\.00 \_$|
|45|mm:ss|
|46|\[h\]:mm:ss|
|47|mmss\.0|
|48|\#\#0\.0E\+0|

When you export to pdf/html, print, or render the spreadsheet in any way, FlexCel will use the formats above to display the cells with those built in ids\. If you want to make FlexCel behave like a different Excel version or language, you might change those values\.


Note that in general, if you care about the cell formats looking the same in all Excel versions, you should avoid using built in formats\. While changing this array will change how FlexCel renders those formats, a user with a different Excel version will still see whatever that Excel version defines for  the format id\.


This method doesn't change anything in the generated xls/x files, it will only change how the generated pdf/html files look\.
This method also affects all threads and XlsFile objects, it is a global setting which you probably shouldn't change; but if you want to change it, you should do so when starting your application\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">class procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetBuiltInFormat(const formatIndex: Integer; const format: string); static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**formatIndex**|Integer|Format index to modify\. Must be one of the formats in the table above\.|
|const|**format**|string|String specifying the format you want to use with the built in format index\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

