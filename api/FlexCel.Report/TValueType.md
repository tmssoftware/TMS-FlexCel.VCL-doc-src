---
uid: TValueType
description: TValueType
---

# TValueType Enumeration

All the things we can find on a cell\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Const|0|A constant value, like 2 or "a"\.<br />|
|DataSet|1|A value from a Dataset\. This tag is written as "\<\#DataTable\.Column>|
|Property|2|A report variable, like \<\#Variable>|
|FullDataSet|3|A dataset with "\*"|
|FullDataSetCaptions|4|Captions for a full dataset\.<br />|
|IF|5|An \#IF construct|
|IFS|6|An \#IFS construct|
|SWITCH|7|A \#SWITCH construct|
|Include|8|An include Tag\.<br />|
|Equal|9|A \#= tag|
|DeleteSheet|10|A \#Delete sheet|
|SheetVisible|11|A \#Sheet visible tag\.<br />|
|ConfigSheet|12|\#Config|
|DeleteRange|13|\#Delete Range|
|DeleteRow|14|\#Delete row|
|DeleteCol|15|Delete Column|
|FormatCell|16|Format cell|
|FormatRow|17|Format row|
|FormatCol|18|Format column|
|FormatRange|19|Format range|
|HPageBreak|20|Horizontal page break|
|VPageBreak|21|Vertical page break|
|Comment|22|This one will not really be stored\.<br />|
|Evaluate|23|An expression that will be evaluated|
|ImgSize|24|Only used inside images, to specify its zoom in %% and its aspect ratio\.<br />|
|ImgPos|25|Only used inside images, to specify its position inside the cell\.<br />|
|ImgFit|26|Only used inside images, to specify how to modify the containing cells to hold the image\.<br />|
|ImgDelete|27|Only used inside images, to delete an image\.<br />|
|Lookup|28|A lookup field\. Parameters are: DataBase, KeyFields, KeyValues, ResultField\.<br />|
|Array|29|An array of values\. Useful for example as the KeyValues argument of the Lookup field\.<br />|
|Regex|30|A regular expression replace\.<br />|
|MergeRange|31|A cell that will be merged\.<br />|
|Formula|32|The contents of this cell should be entered as formula\.<br />|
|ColumnWidth|33|Adjusts the column width to a specified value\.<br />|
|RowHeight|34|Adjusts the row height to a specified value\.<br />|
|Html|35|Defines if the cell has HTML formatted data or not\.<br />|
|Ref|36|The parameter is considered a reference and will be changed when copying the ranges\.<br />|
|AutofitSettings|37|Sets autofit settings for the whole sheet\.<br />|
|Defined|38|Returns true if the expression is defined\.<br />|
|DefinedFormat|39|Returns true if the format is defined\.<br />|
|Preprocess|40|An expression that will be pre evaluated and used to modify the template\.<br />|
|AutoPageBreaks|41|FlexCel should automatically calculate the page breaks in this sheet\.<br />|
|Aggregate|42|Does an operation like sum or average over a dataset\.<br />|
|List|43|Concatenates all values in a dataset as a list\.<br />|
|DbValue|44|Gets the value of a dataset given a row or a column\.<br />|
|Hyperlink|45|Creates a link for the cell\.<br />|
|SwapChartSeries|46|Swaps rows and columns in the chart data definition\.<br />|


