---
uid: TPropertyId
description: TPropertyId
---

# TPropertyId Enumeration

Standard properties of an ole file\. There are two different sets of properties, the standard ones \(properties that exist for any file\) and the extended ones \(properties that exist for Ms Office documents\)

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|This is not a valid property\. It will do nothing\.|
|CoreCodePage|1|The codepage used to save the extended properties themselves\. This value is used by FlexCel to read the other strings in the properties, but shouldn't be of use for normal users\.|
|Title|2|Document Title\. \(Standard property\)|
|Subject|3|Document Subject\. \(Standard property\)|
|Author|4|Author\. \(Standard property\)|
|Keywords|5|Keywords\. \(Standard property\)|
|Comments|6|Comments\. \(Standard property\)|
|Template|7|Template\. \(Standard property\)|
|LastSavedBy|8|Last user to save the file\. \(Standard property\)\.<br />**Note:** Unless you set this property explicitly with XlsFile\.DocumentProperties\.SetStandardProperty, FlexCel will save the creator instead\.<br />This is because you don't normally want to save the last user who modified a template\.|
|RevisionNumber|9|Revision number\. \(Standard property\)\.<br />**Note:**While this is a string and Windows Explorer will allow you to set any value here, Excel will report any file with a revision which is not an integer as invalid\.|
|TotalEditingTime|10|Total editing time\. \(Standard property\)|
|LastPrinted|11|Last printed date\. \(Standard property\)|
|CreateTimeDate|12|Date of created in UTC time\. \(Standard property\)\.<br />**Note:** Unless you set this property explicitly, FlexCel will save the current time as the creation date\. If you are creating a new file this is what you want\. But if you are modifying and existing file and want to preserve the original creation date, you need to explicitly set ths property\.|
|LastSavedTimeDate|13|Date last saved\. \(Standard property\)|
|NumberOfPages|14|Number of pages\. \(Standard property\)|
|NumberOfWords|15|Number of words\. \(Standard property\)|
|NumberOfCharacters|16|Number of characters\. \(Standard property\)|
|Thumbnail|17|Thumbnail image\. \(Standard property\)|
|NameOfCreatingApplication|18|Application that created the file\. \(Standard property\)|
|Security|19|Security\. \(Standard property\)|
|ExtendedCodePage|65536|The codepage used to save the extended properties themselves\. This value is used by FlexCel to read the other strings in the properties, but shouldn't be of use for normal users\.|
|Category|65537|A text string typed by the user that indicates what category the file belongs to \(memo, proposal, and so on\)\. It is useful for finding files of same type\. \(Extended property\)|
|PresentationTarget|65538|Target format for presentation \(35mm, printer, video, and so on\)\. \(Extended property\)|
|Bytes|65539|Number of bytes\. \(Extended property\)|
|Lines|65540|Number of lines\. \(Extended property\)|
|Paragraphs|65541|Number of paragraphs\. \(Extended property\)|
|Slides|65542|Number of slides\. \(Extended property\)|
|Notes|65543|Number of pages that contain notes\. \(Extended property\)|
|HiddenSlides|65544|Number of slides that are hidden\. \(Extended property\)|
|MMClips|65545|Number of sound or video clips\. \(Extended property\)|
|ScaleCrop|65546|Set to True \(\-1\) when scaling of the thumbnail is desired\. If not set, cropping is desired\. \(Extended property\)|
|HeadingPairs|65547|Internally used property indicating the grouping of different document parts and the number of items in each group\. The titles of the document parts are stored in the TitlesofParts property\. The HeadingPairs property is stored as a vector of variants, in repeating pairs of VT\_LPSTR \(or VT\_LPWSTR\) and VT\_I4 values\. The VT\_LPSTR value represents a heading name, and the VT\_I4 value indicates the count of document parts under that heading\. \(Extended property\)|
|TitlesofParts|65548|Names of document parts\. \(Extended property\)|
|Manager|65549|Manager of the project\. \(Extended property\)|
|Company|65550|Company name\. \(Extended property\)|
|LinksUpToDate|65551|Boolean value to indicate whether the custom links are hampered by excessive noise, for all applications\. \(Extended property\)|
|CharacterCountWithSpaces|65552|Estimate of the number of characters in the document including whitespace\.|
|SharedDoc|65554|This property must be false\.|
|LinksBase|65555|Base URL for links\.|
|Hyperlinks|65556|Not saved here\. This property must not be written\.|
|HyperlinksChanged|65557|True if the links were changed outside the application and must be updated\.|
|AppVersion|65558|Version of the application that wrote the file\. The 2 high order bytes are the major version, and the 2 lower bytes the minor version\.|
|DigitalSignature|65559|Data on the VBA digital signature if the file has a macro digitally signed\.|
|ContentType|65561|String that specifies the content type of the file\.|
|Status|65562|Status of the document\.|
|Language|65563|Language of the document\. Should be absent\.|
|Version|65564|Version of the document\. Should be absent\.|


