---
uid: TDataConnectionTextImportProperties
description: TDataConnectionTextImportProperties
---

# TDataConnectionTextImportProperties Class

This element contains all of the text import settings\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnectionTextImportProperties = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[TextFields](TextFields.md)|Field definitions\. This property is never null, and by modifying it you modify the parent TextImportProperties too\.<br />|
|[PromptForFileName](PromptForFileName.md)|Flag indicating whether the user wants to be prompted for the file name on refresh\. If false, then the user is not prompted\.If true or not present, then the user is prompted\.<br />|
|[FileType](FileType.md)|Ignorable attribute\. Determines the kind of character set to use during import\.<br />Only one of FileType and CharacterSet or CodePage shall be specified\.<br />|
|[CharacterSet](CharacterSet.md)|Name of the character set associated with the text file\. Values for this attribute are restricted to the names and aliases listed in the IANA CHARACTER SETS listing found at http:&#8203;//&#8203;www\.&#8203;iana\.&#8203;org/&#8203;assignments/&#8203;character\-&#8203;sets\.&#8203;<br /><br /><br /><br />If this attribute is not present then the CodePage attribute is used\.<br /><br /><br />|
|[FirstRow](FirstRow.md)|Indicates at what row of the file to start the data import\. All unsignedInt values are permitted, although it's possible that firstRow is higher than the number of rows in the text file, in which case no data is imported\.<br />|
|[SourceFile](SourceFile.md)|Path to the text file to use to import external data\. Can be expressed in URI or systemspecific file path notation\.<br />|
|[IsDelimited](IsDelimited.md)|True if the file is Tab or character delimited\. false if the file should be parsed according to fixed length fields\.<br />|
|[DecimalSeparator](DecimalSeparator.md)|The decimal separator character\. This and the thousands attribute are used only when data in the text file contains decimal and thousands separators that are different from those used on the computer, due to a different language setting being used\.<br />|
|[ThousandsSeparator](ThousandsSeparator.md)|The thousands separator character\. This and the decimal attribute are used only when data in the text file contains decimal and thousands separators that are different from those used on the computer, due to a different language setting being used\.Please refer to the decimal attribute description above for a Table describing the behavior\.<br />Strings values of this attribute are expected to be one character in length\.<br />|
|[TabIsDelimiter](TabIsDelimiter.md)|Flag indicating whether to treat tab characters as field delimiters\. If false, then tabs will not be used as delimiters\.If true or not present, then they are used as delimiters\.<br />|
|[SpaceIsDelimiter](SpaceIsDelimiter.md)|Flag indicating whether to treat space characters as field delimiters\.<br />|
|[CommaIsDelimiter](CommaIsDelimiter.md)|Flag indicating whether to treat comma characters as field delimiters\.<br />|
|[SemicolonIsDelimiter](SemicolonIsDelimiter.md)|Flag indicating whether to treat semicolon characters as field delimiters\.<br />|
|[ConsecutiveDelimiters](ConsecutiveDelimiters.md)|Flag indicating whether consecutive delimiters should be treated as just one delimiter\. If this flag is true than it's possible or even likely that some rows will return more fields than others, and these fields will always fill cells in the worksheet from left to right\.<br />|
|[Qualifier](Qualifier.md)|Character used as the text string qualifier\.<br />|
|[Delimiter](Delimiter.md)|User\-specified character to be treated as a field delimiter\. Only single characters are supported\.<br />|


