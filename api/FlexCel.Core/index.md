---
uid: FlexCel.Core
description: FlexCel.Core
---

# FlexCel.Core Namespace

Core types and utilities used by FlexCel\.


## Classes

|Name|Description|
|---|---|
|[EFlexCelCore&#8203;Exception](EFlexCelCoreException/index.md)|Exception thrown when an exception on the core engine happens\.<br />|
|[EFlexCelException](EFlexCelException/index.md)|Exception thrown when a specific FlexCel error happens\. Base of all FlexCel hierarchy list\.<br />|
|[TAlphaModFix&#8203;Blip&#8203;Transform](TAlphaModFixBlipTransform/index.md)|Represents a transform that changes the opacity of the image\.<br />|
|[TAxisLineOptions](TAxisLineOptions/index.md)|Line options for an Axis\.<br />|
|[TAxisRangeOptions](TAxisRangeOptions/index.md)|Properties for the ranges of an axis\.<br />|
|[TAxisTickOptions](TAxisTickOptions/index.md)|Properties for the ticks and labels of an axis\.<br />|
|[TBaseAxis](TBaseAxis/index.md)|Common ancestor for all Axis types\.<br />|
|[TBlipFillMode](TBlipFillMode/index.md)|This class is designed to store tiling or stretching fill mode information\.<br />You need to use any of its descendants, [TBlipFillStretch](TBlipFillStretch/index.md) or [TBlipFillTile](TBlipFillTile/index.md)|
|[TBlipFillStretch](TBlipFillStretch/index.md)|This element specifies that a BLIP should be stretched to fill the target rectangle\. The other option is a tile where  a BLIP is tiled to fill the available area\.<br />|
|[TBlipFillTile](TBlipFillTile/index.md)|This element specifies that a BLIP should be tiled to fill the available space\.  This element defines a "tile"  rectangle within the bounding box\.  The image is encompassed within the tile rectangle, and the tile rectangle is  tiled across the bounding box to fill the entire area\.<br />|
|[TBlipTransform](TBlipTransform/index.md)|Represents a simple transformation applied to an image\. You should use the descendants of this class, not this class directly\.<br />|
|[TBlipTransformList](TBlipTransformList/index.md)|A list with TBlipTransforms\.<br />|
|[TBlurEffect](TBlurEffect/index.md)|A blur effect applied to the whole shape\.<br />|
|[TCategoryAxis](TCategoryAxis/index.md)|Information about an Axis of categories\. \(normally the x axis\)|
|[TChartDropBars](TChartDropBars/index.md)|Information about a Drop Bar\.<br />|
|[TChartErrorBars](TChartErrorBars/index.md)|Information about an Error Bar\.<br />|
|[TChartOneDropBar](TChartOneDropBar/index.md)|Information about one specific drop bar\.<br />|
|[TChartSeries&#8203;Marker&#8203;Options](TChartSeriesMarkerOptions/index.md)|Marker options for the whole series or a point in the series when the chart is line or scatter\.<br />|
|[TChartSeries&#8203;Misc&#8203;Options](TChartSeriesMiscOptions/index.md)|Misc options for the whole series or a point in the series that do no enter in any other category\.<br />|
|[TChartSeriesOptions](TChartSeriesOptions/index.md)|Options for the whole series or for a data point inside it\.<br />|
|[TChartSeries&#8203;PieOptions](TChartSeriesPieOptions/index.md)|Pie options for a series or a slice of the series when the chart is a pie chart\.<br />|
|[TChartTitle](TChartTitle/index.md)|Represents the title of the chart\.<br />|
|[TChartWallOptions](TChartWallOptions/index.md)|Fill and Line options for the walls and floor of a 3D chart\.<br />|
|[TCmsSigner](TCmsSigner/index.md)|Represents an abstract class to create a pdf PKCS7 DER encoded signature\.<br />Descend from this class to create your own SignerFactory implementations\.<br />|
|[TColorChange&#8203;Blip&#8203;Transform](TColorChangeBlipTransform/index.md)|Represents a color transformation from one color to another\. This transform can be used to make a color transparent\.<br />|
|[TConditional&#8203;Format&#8203;Color&#8203;List](TConditionalFormatColorList/index.md)|A list of conditional value colors\.<br />|
|[TConditional&#8203;FormatDef](TConditionalFormatDef/index.md)|The format to apply when a [IConditional&#8203;Format&#8203;Rule](IConditionalFormatRule/index.md) is applied\.<br />|
|[TConditional&#8203;Format&#8203;DefColor&#8203;Scale](TConditionalFormatDefColorScale/index.md)|Defines a format of the color scales in a conditional format\.<br />|
|[TConditional&#8203;Format&#8203;DefDataBar](TConditionalFormatDefDataBar/index.md)|Defines a format of the databars in a conditional format\.<br />|
|[TConditional&#8203;Format&#8203;DefIconSet](TConditionalFormatDefIconSet/index.md)|Defines a format of the color scales in a conditional format\.<br />|
|[TConditional&#8203;Format&#8203;DefStandard](TConditionalFormatDefStandard/index.md)|Defines a format to apply for cells when a rule evaluates to true\.<br />|
|[TConditional&#8203;Format&#8203;Value&#8203;AndColor&#8203;List](TConditionalFormatValueAndColorList/index.md)|A list of conditional value objects with their corresponding colors\.<br />|
|[TConditional&#8203;Format&#8203;Value&#8203;List](TConditionalFormatValueList/index.md)|A list of conditional value objects\.<br />|
|[TConditional&#8203;Format&#8203;Value&#8203;Object](TConditionalFormatValueObject/index.md)|Describes an interpolation point in a gradient scale\.<br />|
|[TCultureCreating&#8203;Event&#8203;Args](TCultureCreatingEventArgs/index.md)|Event when creating a culture\.<br />|
|[TCustomTable&#8203;Style&#8203;Section](TCustomTableStyleSection/index.md)|Represents the format of a table section \(header, totals, etc\)\.<br />|
|[TDataBarColors](TDataBarColors/index.md)|Colors which define the databar\.<br />|
|[TDataConnection](TDataConnection/index.md)|This class represents one data connection on the workbook\.<br />|
|[TDataConnection&#8203;DbProperties](TDataConnectionDbProperties/index.md)|This element stores all properties associated with an ODBC or OLE DB external data connection\.<br />|
|[TDataConnection&#8203;Olap&#8203;Properties](TDataConnectionOlapProperties/index.md)|This element contains all the properties needed for an OLAP data connection\. OLAP connections contain both the [TDataConnection&#8203;DbProperties](TDataConnectionDbProperties/index.md) and TDataConnection&#8203;Olap&#8203;Properties child elements\.<br />|
|[TDataConnection&#8203;Parameter](TDataConnectionParameter/index.md)|This element stores properties about any parameters used with external data connections\. Parameters are used to change the query executed externally and cause different data to be retrieved into the workbook\.The type of parameter used determines whether the user is prompted for a value before data is refreshed, or the value is pulled from a cell in the workbook, or whether the same value should be used until explicitly changed in the data connection\. Parameters are permitted for ODBC and web queries\.<br />|
|[TDataConnection&#8203;Parameters](TDataConnectionParameters/index.md)|A list of [TDataConnection&#8203;Parameter](TDataConnectionParameter/index.md)\.<br />|
|[TDataConnectionTable](TDataConnectionTable/index.md)|Specifies the HTML table to import\.<br />|
|[TDataConnection&#8203;Tables](TDataConnectionTables/index.md)|Collection of HTML tables in a web query connection\.<br />|
|[TDataConnection&#8203;Text&#8203;Field](TDataConnectionTextField/index.md)|This element specifies field settings for text import\.<br />|
|[TDataConnection&#8203;Text&#8203;Fields](TDataConnectionTextFields/index.md)|Collection of fields in the Text connection\.<br />|
|[TDataConnection&#8203;Text&#8203;Import&#8203;Properties](TDataConnectionTextImportProperties/index.md)|This element contains all of the text import settings\.<br />|
|[TDataConnection&#8203;WebQuery&#8203;Properties](TDataConnectionWebQueryProperties/index.md)|This element specifies the properties for a web query source\. A web query will retrieve data from HTML tables, and can also supply HTTP "Get" parameters to be processed by the web server in generating the HTML by including the parameters and parameter elements\.<br />|
|[TDataLabelOptions](TDataLabelOptions/index.md)|Options for a data label\.<br />|
|[TDocumentProperties](TDocumentProperties/index.md)|Properties for an Excel sheet\.<br />|
|[TDrawingEffect](TDrawingEffect/index.md)|Base class for all drawing effects, like [TBlurEffect](TBlurEffect/index.md) or [TGlowEffect](TGlowEffect/index.md)|
|[TDrawingGradientDef](TDrawingGradientDef/index.md)|A base class for storing gradient definitions, be them Linear or Path gradients\.<br />|
|[TDrawingLinear&#8203;Gradient](TDrawingLinearGradient/index.md)|This class holds a linear gradient definition\.<br />|
|[TDrawingPathGradient](TDrawingPathGradient/index.md)|Holds a Path gradient definition\.<br />|
|[TEffectContainer](TEffectContainer/index.md)|This class encapsulates a node of the effect DAC\.<br />|
|[TEffectList](TEffectList/index.md)|This class holds a list of effects that are applied to a drawing\.<br />|
|[TEffectStyleList](TEffectStyleList/index.md)|A list with all the effects for subtle, moderate and intense formatting types\.<br />|
|[TEncryptionFactory](TEncryptionFactory/index.md)|This class encapsulates what we need to support encryption routines\. You can derive from this class and override the methods to return your own encryption classes\. then you need to assign the static variable EncryptionFactory to your descendant class, and FlexCel will then use the new classes\.<br />|
|[TExcelFile](TExcelFile/index.md)|Interface a FlexCel engine has to implement to be used by the other components in the suite like [TFlexCelReport](../FlexCel.Report/TFlexCelReport/index.md) or [TFlexCelPdfExport](../FlexCel.Render/TFlexCelPdfExport/index.md)\.<br />|
|[TExcelObjectList](TExcelObjectList/index.md)|A list that contains the Ids and positions of the Excel objects|
|[TFillOverlayEffect](TFillOverlayEffect/index.md)|A fill overlay effect\.<br />|
|[TFillStyleList](TFillStyleList/index.md)|Represents the fill style characteristics for an autoshape\.<br />|
|[TFlexCelErrorInfo](TFlexCelErrorInfo/index.md)|This class contains generic information about a non fatal error that happened in FlexCel\.<br />Children classes might contain more information specific to the error type\.<br />|
|[TFlexCelFormat&#8203;Settings](TFlexCelFormatSettings/index.md)|This class allows customization of the numeric formats FlexCel uses to display, either globally for all instances or by thread\.<br />|
|[TFontCreated&#8203;Event&#8203;Args](TFontCreatedEventArgs/index.md)|Arguments passed in FontCreated events\.<br />|
|[TFontCreating&#8203;Event&#8203;Args](TFontCreatingEventArgs/index.md)|Arguments passed in FontCreating events\.<br />|
|[TFontCreation&#8203;Event&#8203;Args](TFontCreationEventArgs/index.md)|Base class for font creation events\.<br />|
|[TGlowEffect](TGlowEffect/index.md)|A glow effect\.<br />|
|[THtmlFontEventArgs](THtmlFontEventArgs/index.md)|Arguments passed on FlexCel\.&#8203;Render\.&#8203;FlexCel&#8203;Html&#8203;Export\.&#8203;OnHtml&#8203;Font\.<br />|
|[THtmlParsedString](THtmlParsedString/index.md)|An Html string parsed into a C\# string and tags\.<br />|
|[THtmlSaveSharing&#8203;Violation&#8203;Error](THtmlSaveSharingViolationError/index.md)|This class has information for a [TFlexCelError.&#8203;Html&#8203;Save&#8203;Sharing&#8203;Violation](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Html&#8203;Save&#8203;Sharing&#8203;Violation](TFlexCelError.md) for more information\.<br />|
|[TImplementedFunction](TImplementedFunction/index.md)|Data of an implemented formula function\.<br />|
|[TImplemented&#8203;Function&#8203;List](TImplementedFunctionList/index.md)|Holds a list of currently implemented formula functions on FlexCel\.<br />|
|[TInnerShadowEffect](TInnerShadowEffect/index.md)|An inner shadow effect\.<br />|
|[TLegendEntryOptions](TLegendEntryOptions/index.md)|Description of one particular entry on the Legend box\.<br />|
|[TLegendOptionsList](TLegendOptionsList/index.md)|A list of options for the legend on the whole series and for specific data points inside these series\.<br />|
|[TLineStyleList](TLineStyleList/index.md)|Represents the line style characteristics\.<br />|
|[TLoadLinkedFile&#8203;Event&#8203;Args](TLoadLinkedFileEventArgs/index.md)|Arguments passed on [TWorkspace.&#8203;Load&#8203;Linked&#8203;File](TWorkspace/LoadLinkedFile.md)|
|[TLoopOverUsed&#8203;Range&#8203;Parameters](TLoopOverUsedRangeParameters/index.md)|This class contains the parameters passed in [TExcelFile.&#8203;Loop&#8203;Over&#8203;Used&#8203;Range](TExcelFile/LoopOverUsedRange.md)|
|[TMalformedUrlError](TMalformedUrlError/index.md)|This class has information for a [TFlexCelError.&#8203;MalformedUrl](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;MalformedUrl](TFlexCelError.md) for more information\.<br />|
|[TMimeWriter](TMimeWriter/index.md)|A simple class used to create MIME formatted messages\. While it does not provide much functionality, it gives enough to create simple multipart archives\.<br />|
|[TObjectTextProperties](TObjectTextProperties/index.md)|Specifies properties for the text in an autoshape or object\.<br />|
|[TOnPasswordEventArgs](TOnPasswordEventArgs/index.md)|Use this class to supply a password to open an encrypted file\.<br />|
|[TOnSheetName&#8203;Event&#8203;Args](TOnSheetNameEventArgs/index.md)|Arguments passed on a OnSheetName event\.<br />|
|[TOuterShadowEffect](TOuterShadowEffect/index.md)|An outer shadow effect\.<br />|
|[TPdfCorruptFont&#8203;InFont&#8203;Folder&#8203;Error](TPdfCorruptFontInFontFolderError/index.md)|This class has information for a [TFlexCelError.&#8203;Pdf&#8203;Corrupt&#8203;Font&#8203;InFont&#8203;Folder](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Pdf&#8203;Corrupt&#8203;Font&#8203;InFont&#8203;Folder](TFlexCelError.md) for more information\.<br />|
|[TPdfFauxBold&#8203;OrItalics&#8203;Error](TPdfFauxBoldOrItalicsError/index.md)|This class has information for a [TFlexCelError.&#8203;Pdf&#8203;Faux&#8203;Bold&#8203;OrItalics](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Pdf&#8203;Faux&#8203;Bold&#8203;OrItalics](TFlexCelError.md) for more information\.<br />|
|[TPdfFontLicense&#8203;Doesnt&#8203;Allow&#8203;Embedding&#8203;Error](TPdfFontLicenseDoesntAllowEmbeddingError/index.md)|This class has information for a [TFlexCelError.&#8203;Pdf&#8203;Font&#8203;License&#8203;Doesnt&#8203;Allow&#8203;Embedding](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Pdf&#8203;Font&#8203;License&#8203;Doesnt&#8203;Allow&#8203;Embedding](TFlexCelError.md) for more information\.<br />|
|[TPdfFontNotFound&#8203;Error](TPdfFontNotFoundError/index.md)|This class has information for a [TFlexCelError.&#8203;Pdf&#8203;Font&#8203;NotFound](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Pdf&#8203;Font&#8203;NotFound](TFlexCelError.md) for more information\.<br />|
|[TPdfGlyphNot&#8203;InFont&#8203;Error](TPdfGlyphNotInFontError/index.md)|This class has information for a [TFlexCelError.&#8203;Pdf&#8203;Glyph&#8203;NotIn&#8203;Font](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Pdf&#8203;Glyph&#8203;NotIn&#8203;Font](TFlexCelError.md) for more information\.<br />|
|[TPdfUsedFallback&#8203;Font&#8203;Error](TPdfUsedFallbackFontError/index.md)|This class has information for a [TFlexCelError.&#8203;Pdf&#8203;Used&#8203;Fallback&#8203;Font](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Pdf&#8203;Used&#8203;Fallback&#8203;Font](TFlexCelError.md) for more information\.<br />|
|[TPresetShadowEffect](TPresetShadowEffect/index.md)|Applies a preset shadow effect\.<br />|
|[TProtection](TProtection/index.md)|Encryption data for an Excel sheet\.<br />|
|[TRecoveryInvalid&#8203;Format](TRecoveryInvalidFormat/index.md)|This error happens when in recovery mode and a format has invalid data\.<br />|
|[TRecoveryInvalid&#8203;Formula&#8203;Tokens](TRecoveryInvalidFormulaTokens/index.md)|This error happens when in recovery mode and a formula has invalid data\.<br />|
|[TRecoveryInvalid&#8203;Name&#8203;Error](TRecoveryInvalidNameError/index.md)|This error happens when in recovery mode and a name has to be ignored because it can't be read\.<br />|
|[TReflectionEffect](TReflectionEffect/index.md)|Applies a reflection effect\.<br />|
|[TRenderCorrupt&#8203;Image&#8203;Error](TRenderCorruptImageError/index.md)|This class has information for a [TFlexCelError.&#8203;Render&#8203;Corrupt&#8203;Image](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Render&#8203;Corrupt&#8203;Image](TFlexCelError.md) for more information\.<br />|
|[TRenderError&#8203;Drawing&#8203;Image&#8203;Error](TRenderErrorDrawingImageError/index.md)|This class has information for a [TFlexCelError.&#8203;Render&#8203;Error&#8203;Drawing&#8203;Image](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Render&#8203;Error&#8203;Drawing&#8203;Image](TFlexCelError.md) for more information\.<br />|
|[TRenderGeneric&#8203;Preview&#8203;Error](TRenderGenericPreviewError/index.md)|This class has information for a [TFlexCelError.&#8203;Render&#8203;Generic&#8203;Preview](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Render&#8203;Generic&#8203;Preview](TFlexCelError.md) for more information\.<br />|
|[TRenderMetafileError](TRenderMetafileError/index.md)|This class has information for a [TFlexCelError.&#8203;Render&#8203;Metafile](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Render&#8203;Metafile](TFlexCelError.md) for more information\.<br />|
|[TReplaceAction](TReplaceAction/index.md)|Specifies actions to do in every replacement\.<br />|
|[TSeriesOptionsList](TSeriesOptionsList/index.md)|A list of options for the whole series and for specific data points inside these series\.<br />|
|[TSoftEdgesEffect](TSoftEdgesEffect/index.md)|Applies a soft edges effect\.<br />|
|[TTableFormat](TTableFormat/index.md)|Defines a custom format for a table\.<br />|
|[TThemeFont](TThemeFont/index.md)|Represents either a major or a minor font for the theme\.<br />|
|[TToken](TToken/index.md)|This class and all its descendants represent a token in a formula\. You can use these classes to modify formulas without having to parse the text in them, which can be a difficult task\.<br />|
|[TTokenCellAddress](TTokenCellAddress/index.md)|A single cell address in the same sheet or to other sheet\. See also TTokenCellRange, TTokenRelative&#8203;Cell&#8203;Address, TTokenRelative&#8203;Cell&#8203;Range for other tokens that can contain addresses\.<br />|
|[TTokenCellRange](TTokenCellRange/index.md)|A range of cells\. See TTokenCellAddress for single cell references\.<br />|
|[TTokenData](TTokenData/index.md)|Constant data, like "Hello" and 1 in the formula: "=IF\(A1 = 1,,"Hello"\)"|
|[TTokenDataArray](TTokenDataArray/index.md)|Array of Constant data, like "Hello" and 1 in the formula: "=IF\(A1 = 1,,"Hello"\)"|
|[TTokenFunction](TTokenFunction/index.md)|A function like "Sum" or "If"\.<br />Note that this token doesn't have arguments\. The arguments are stored in the TTokenList that contains this token, in the order they appear in the formula\.<br />So, for example, the formula "=Sum\(A1,B2\)" would return the following token list:[...[more]](TTokenFunction/index.md)|
|[TTokenLambdaCallName](TTokenLambdaCallName/index.md)|This token is used when you call a name like "=MyName\(5\)" and MyName has a lambda function\.<br />Note that if a cell has the expression like "=Lambda\(x,x\)" then you will just get a simple [TTokenFunction](TTokenFunction/index.md) with a name of "Lambda"\. This token only appears when using a name as a user\-defined function\.<br />|
|[TTokenLambda&#8203;Parameter&#8203;Definition](TTokenLambdaParameterDefinition/index.md)|A parameter definition in the expression of a =LET or =LAMBDA function, like the first x in the formula: "=LET\(x,3,x\+3\)"|
|[TTokenLambda&#8203;Parameter&#8203;Reference](TTokenLambdaParameterReference/index.md)|A parameter reference in the expression of a =LET or =LAMBDA function, like the second x in the formula: "=LET\(x,3,x\+3\)"|
|[TTokenMissing&#8203;Argument](TTokenMissingArgument/index.md)|A missing argument for a function\. For example the second parameter in the formula: "=IF\(A1 = 1,,"Hello"\)"|
|[TTokenName](TTokenName/index.md)|A named range\. Might refer to a name in a different file\.<br />|
|[TTokenOperator](TTokenOperator/index.md)|An operator like "\+" or "\-"|
|[TTokenParenthesis](TTokenParenthesis/index.md)|A parenthesis surrounding the last token\. Note that this token is not used in the formula \(since RPN doesn't need parenthesis\) but it is there so Excel can display them\.<br />|
|[TTokenRangeOp](TTokenRangeOp/index.md)|An operator that operates in ranges, like union or intersection\.<br />|
|[TTokenReferenceError](TTokenReferenceError/index.md)|This token represents an error like \#REF\!|
|[TTokenRelative&#8203;Cell&#8203;Address](TTokenRelativeCellAddress/index.md)|A single cell address in the same sheet or to other sheet\. It handles a reference relative to the current cell\. So a reference in Cell A4 of RowOffset = \-1 and ColOffset = 3 would mean the cell D3\.<br />|
|[TTokenRelative&#8203;Cell&#8203;Range](TTokenRelativeCellRange/index.md)|A range of cells with relative references\. This is used mostly in named ranges\.<br />|
|[TTokenStructured&#8203;Reference](TTokenStructuredReference/index.md)|A reference for a cell in a table\. For example the reference in the formula =SUM\(&#8203;Table1\[&#8203;\[&#8203;\#&#8203;All\]&#8203;,\[&#8203;Some&#8203;Column\]&#8203;\]&#8203;\)|
|[TTokenUnsupported](TTokenUnsupported/index.md)|This token is not supported by FlexCel\.<br />|
|[TTokenWhitespace](TTokenWhitespace/index.md)|Whitespace like " "\. This is not used in calculation, but it is use by Excel to show the formula as it was entered\.<br />|
|[TUdfEventArgs](TUdfEventArgs/index.md)|Encapsulates the parameters to send to a user Defined Function for evaluation\.<br />|
|[TUIBrush](TUIBrush/index.md)|A base brush for painting\.<br />|
|[TUIColorBlend](TUIColorBlend/index.md)|Defines a complex gradient by using an array of [TUIGradientStop](TUIGradientStop/index.md)|
|[TUIFont](TUIFont/index.md)|Represents a font used for drawing in a pdf/gdi\+/wpf/winrt canvas\. This class might hold resources which need disposing\.<br />|
|[TUIGraphics](TUIGraphics/index.md)|This class represents a native canvas for drawing\.<br />|
|[TUIHatchBrush](TUIHatchBrush/index.md)|A class representing a platform independent hatch brush\.<br />|
|[TUIImage](TUIImage/index.md)|A platform independent image\.<br />|
|[TUIImageAttributes](TUIImageAttributes/index.md)|Platform independent image attributes\.<br />|
|[TUILinearGradient&#8203;Brush](TUILinearGradientBrush/index.md)|Represents a platform independent linear gradient\.<br />|
|[TUIMultiPageSaver](TUIMultiPageSaver/index.md)|This class is used to carry information when saving multi page images, like for example a multipage tiff\.<br />|
|[TUIPathGradientBrush](TUIPathGradientBrush/index.md)|A platform\-&#8203;independent Path gradient implementation\.<br />|
|[TUIPen](TUIPen/index.md)|A pen used to draw into a canvas\.<br />|
|[TUISolidBrush](TUISolidBrush/index.md)|A solid brush with a single color\.<br />|
|[TUITextureBrush](TUITextureBrush/index.md)|A brush using an image as a pattern\.<br />|
|[TUnknownBlip&#8203;Transform](TUnknownBlipTransform/index.md)|Represents a color transform that FlexCel currently doesn't know about\.<br />|
|[TUnsupportedFormula](TUnsupportedFormula/index.md)|An unsupported formula, the cell it is in, and the reason why it is not supported\.<br />|
|[TUnsupported&#8203;Formula&#8203;List](TUnsupportedFormulaList/index.md)|A list of unsupported formulas on a sheet\.<br />|
|[TUserDefinedFunction](TUserDefinedFunction/index.md)|Inherit from this class to create your own user defined functions\. Make sure you read ['Using Excel's user defined functions (UDF)' in the Api Developer Guide](xref:ApiDeveloperGuide#using-excels-user-defined-functions-udf) to get more information on what user defined functions are and how they are created\.<br />|
|[TValueAxis](TValueAxis/index.md)|Information about an Axis of values\. \(normally the y axis\)|
|[TVirtualCell&#8203;EndReading&#8203;Event&#8203;Args](TVirtualCellEndReadingEventArgs/index.md)|Arguments passed in the event\.<br />|
|[TVirtualCell&#8203;Read&#8203;Event&#8203;Args](TVirtualCellReadEventArgs/index.md)|Arguments passed in the event\.<br />|
|[TVirtualCell&#8203;Start&#8203;Reading&#8203;Event&#8203;Args](TVirtualCellStartReadingEventArgs/index.md)|Arguments passed in the event\.<br />|
|[TWorkspace](TWorkspace/index.md)|This class links together a group of spreadsheets, so you can recalculate among linked spreadsheets\.<br />In order to use it, just define an object of this class and add all the files you need for the linked recalculation\.<br />If you don't know in advance which files you will need, you can use the [TWorkspace.&#8203;Load&#8203;Linked&#8203;File](TWorkspace/LoadLinkedFile.md) event\.<br /><br />Note that whenever you recalculate any file in the workspace, all files will be recalculated, so you don't need to calculate them twice\.<br />|
|[TX509Certificate2](TX509Certificate2/index.md)|Represents an abstract class to hold a certificate\.<br />Descend from this class to create your own SignerFactory implementations\.<br />|
|[TXlsTooManyPage&#8203;Breaks&#8203;Error](TXlsTooManyPageBreaksError/index.md)|This class has information for a [TFlexCelError.&#8203;Xls&#8203;TooMany&#8203;Page&#8203;Breaks](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Xls&#8203;TooMany&#8203;Page&#8203;Breaks](TFlexCelError.md) for more information\.<br />|
|[TXlsxInvalid&#8203;Name&#8203;Error](TXlsxInvalidNameError/index.md)|This class has information for a [TFlexCelError.&#8203;Xlsx&#8203;Invalid&#8203;Name](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Xlsx&#8203;Invalid&#8203;Name](TFlexCelError.md) for more information\.<br />|
|[TXlsxMissing&#8203;Part&#8203;Error](TXlsxMissingPartError/index.md)|This class has information for a [TFlexCelError.&#8203;Xlsx&#8203;Missing&#8203;Part](TFlexCelError.md) error\. Look at [TFlexCelError.&#8203;Xlsx&#8203;Missing&#8203;Part](TFlexCelError.md) for more information\.<br />|
|[TXmlMapDataBinding](TXmlMapDataBinding/index.md)|Specifies how the XML binding works\.<br />|
|[TXmlMapMap](TXmlMapMap/index.md)|Defines the XML Map\.<br />|
|[TXmlMapSchema](TXmlMapSchema/index.md)|Stores the schemas for a particular XML map object\. There can be multiple Schema elements in a workbook, one for each XML map\.<br />|


## Records

|Name|Description|
|---|---|
|[ARGB](ARGB/index.md)|Represents a color used to draw in a canvas \(gdi\+, wpf, etc\) in a way that is independent of the drawing framework\.<br />|
|[Colors](Colors/index.md)|A list of standard colors\.<br />|
|[TAdaptativeFormats](TAdaptativeFormats/index.md)|Information about characters in a numeric format that need to be adapted when rendering\. For example, if the cell A1 has value 1 and format "\*\_0" it will print as "\_\_\_\_\_\_1" when the cell is wide, and as "\_1" when the cell is shorter\.<br />|
|[TAddress](TAddress/index.md)|Used to summarize a range of cells\. This class is for internal use\.<br />|
|[TAverageValue](TAverageValue/index.md)|This class is for internal use\. It is used to calculate an average over a range of cells\.<br />|
|[TCachedFontWidth](TCachedFontWidth/index.md)|A font size cached for speed\.<br />|
|[TCellAddress](TCellAddress/index.md)|Small class that can convert between a string reference \("A1"\) into row and col integers \(1,1\)\.<br />|
|[TCellAddressRange](TCellAddressRange/index.md)|A class with 2 TCellAddress objects marking the start and end of a cell range\.<br />|
|[TCellAddress&#8203;With&#8203;File&#8203;Name](TCellAddressWithFileName/index.md)|Encapsulates a cell address and the file where the cell is stored\.<br />|
|[TCellMergedState](TCellMergedState/index.md)|This struct is used in [TExcelFile.&#8203;Cell&#8203;Merged&#8203;Next](TExcelFile/CellMergedNext.md) to keep track of the next merged cell that will be iterated\.<br />|
|[TCellValue](TCellValue/index.md)|Represents a value inside a cell\.<br />|
|[TCharAndPos](TCharAndPos/index.md)|A simple structure containing a position and a character\.<br />|
|[TChartPlotArea&#8203;Position](TChartPlotAreaPosition/index.md)|Defines the rectangle where a chart element is positioned\.<br />|
|[TChartRelative&#8203;Rectangle](TChartRelativeRectangle/index.md)|A rectangle used in charts that is relative to a parent rectangle\. The coordinates of the rectangle go between 0 and 1 where 0 means 0%% of the coordinate of the parent, and 1 means 100%%\.<br />|
|[TChartStyle](TChartStyle/index.md)|This structure defines the default style of a chart\. Excel defines 48 default styles\.<br />|
|[TChartTrendlineLabel](TChartTrendlineLabel/index.md)|Properties for a label in a trendline\.<br />|
|[TChildAnchor](TChildAnchor/index.md)|A class to hold the offsets relative to the parent on grouped shapes\.<br />|
|[TClientAnchor](TClientAnchor/index.md)|Image Anchor information\.<br />|
|[TColorTransform](TColorTransform/index.md)|Specifies a color transformation to be applied to a color\.<br />|
|[TColumnBlock](TColumnBlock/index.md)|This class represents a block of columns with the same formatting, options and width\.<br />|
|[TCondFmtApplyBorders](TCondFmtApplyBorders/index.md)|Determines which parts of the borders will be applied in the conditional format\.<br />|
|[TCondFmtApplyFill](TCondFmtApplyFill/index.md)|Determines which parts of the pattern will be applied in the conditional format\.<br />|
|[TCondFmtApplyFont](TCondFmtApplyFont/index.md)|Determines which parts of the font will be applied in the conditional format\.<br />|
|[TCondFmtBorders](TCondFmtBorders/index.md)|Determines which parts of the borders will be applied in the conditional format\.<br />|
|[TCondFmtFont](TCondFmtFont/index.md)|Determines which parts of the font will be applied in the conditional format\.<br />|
|[TConditionalFormat](TConditionalFormat/index.md)|This class encapsulates a list of conditional formats for a range of cells\.<br />|
|[TConditional&#8203;Format&#8203;Custom&#8203;IconDef](TConditionalFormatCustomIconDef/index.md)|This structure holds a single icon from a specific icon set\.<br />|
|[TCropArea](TCropArea/index.md)|Defines a cropping area for an image\. If the values are not zero, only a part of the image will display on Excel\.<br />|
|[TCustomXmlPart](TCustomXmlPart/index.md)|Implements a custom XML part as described in [https:&#8203;//&#8203;msdn.&#8203;microsoft.&#8203;com/&#8203;en-&#8203;us/&#8203;library/&#8203;bb608618.&#8203;aspx](https://msdn.microsoft.com/en-us/library/bb608618.aspx)|
|[TDataLabelsRange](TDataLabelsRange/index.md)|Encapsulates the data for a range of text used in labels|
|[TDataValidationInfo](TDataValidationInfo/index.md)|Contains the information to define a data validation in a range of cells\.<br />|
|[TDefaultShapeOptions](TDefaultShapeOptions/index.md)|Helper class to know which shape options default to true when not specified\.<br />|
|[TDocumentCustom&#8203;Property](TDocumentCustomProperty/index.md)|Encapsulates a custom property of an Excel file\.<br />|
|[TDrawingColor](TDrawingColor/index.md)|Represents a Color for a drawing or a theme\. Different from TExcelColor, this structure is defined in terms of DrawingML, not SpreadsheetML\.<br />|
|[TDrawingConditional&#8203;Format&#8203;DataBar](TDrawingConditionalFormatDataBar/index.md)|Defines the characteristics of a conditional format data bar which is going to be rendered on the screen or to a file\.<br />It is used for exporting xls/x files to drawings or pdf\.<br />|
|[TDrawingConditional&#8203;Format&#8203;IconSet](TDrawingConditionalFormatIconSet/index.md)|Defines the characteristics of a conditional format icon which is going to be rendered on the screen or to a file\.<br />It is used for exporting xls/x files to drawings or pdf\.<br />|
|[TDrawingCoordinate](TDrawingCoordinate/index.md)|A coordinate in a drawing\.<br />|
|[TDrawingGradientStop](TDrawingGradientStop/index.md)|Represents one of the points in a Gradient definition for a drawing \(autoshapes, charts, etc\)\. Note that Excel cells use a different Gradient definition: [TGradientStop](TGradientStop/index.md)|
|[TDrawingHyperlink](TDrawingHyperlink/index.md)|Specifies an hyperlink in a drawing\. While this class is similar to THyperlink for links in cells, it has some differences\.<br />|
|[TDrawingParagraph&#8203;Properties](TDrawingParagraphProperties/index.md)|Properties of a text paragraph inside a drawing\.<br />|
|[TDrawingPoint](TDrawingPoint/index.md)|A point with x and y coordinates\.<br />|
|[TDrawingRelativeRect](TDrawingRelativeRect/index.md)|A rectangle with coordinates used in a drawing\.<br />|
|[TDrawingRichString](TDrawingRichString/index.md)|A rich string used in drawings\. It is similar to [TRichString](TRichString/index.md) but it has more  properties like for example wordart properties\. Similar to a string, this class is immutable\.<br />|
|[TDrawingText&#8203;Attributes](TDrawingTextAttributes/index.md)|Group of simple attributes for text properties\.<br />|
|[TDrawingText&#8203;Paragraph](TDrawingTextParagraph/index.md)|A paragraph in the text inside a drawing\. This struct is immutable\.<br />|
|[TDrawingText&#8203;Properties](TDrawingTextProperties/index.md)|Properties of a text run inside a drawing\.<br />|
|[TDrawingTextRun](TDrawingTextRun/index.md)|A rich formatting run used in text inside of a drawing\. This struct is immutable\.<br />|
|[TDrawingUnderline](TDrawingUnderline/index.md)|Specifies the Fill style and line style of underlined text, when it is underlined\.<br />|
|[TDrawingValue](TDrawingValue/index.md)|Represents a value inside a cell\.<br />|
|[TExcelColor](TExcelColor/index.md)|Represents an Excel color\. Colors in Excel can be defined in four ways: Automatic Colors, Indexed Colors \(for compatibility with Excel 2003 or older\), Palette colors, and RGB colors\. This Structure is immutable, once you create it you cannot change its members\. You need to create a new struct to modify it\.<br />|
|[TExcelFont](TExcelFont/index.md)|Utility methods to create normal fonts from Excel ones\.<br />|
|[TExcelMetrics](TExcelMetrics/index.md)|Returns Information to convert between standard units and Excel units\.<br />|
|[TExcelTypes](TExcelTypes/index.md)|Manages converting from/to objects/Native excel types\.<br />|
|[TFlexCelConfig](TFlexCelConfig/index.md)|A central point of for configuring FlexCel parameters\.<br />|
|[TFlexCelDataFormats](TFlexCelDataFormats/index.md)|Excel formats to copy/paste to/from the clipboard|
|[TFlexCelTrace](TFlexCelTrace/index.md)|This class reports al FlexCel non\-fatal errors\. Use it to diagnose when something is going wrong\.<br />|
|[TFlexCelWriter](TFlexCelWriter/index.md)|Encapsulates a generic writer\. This record converts automatically from a TStreamWriter or a TFlexCelStream&#8203;Writer, so you can use both when a FlexCel method requires a TFlexCelWriter\.<br />|
|[TFlxApplyBorders](TFlxApplyBorders/index.md)|Border style for a cell\.<br />|
|[TFlxApplyFillPattern](TFlxApplyFillPattern/index.md)|Fill pattern and color for the background of a cell\.<br />|
|[TFlxApplyFont](TFlxApplyFont/index.md)|Encapsulation of an Excel Font\.<br />|
|[TFlxApplyFormat](TFlxApplyFormat/index.md)|Defines which attributes of a [TFlxFormat](TFlxFormat/index.md) will be applied for one cell\.<br />Whatever member is set to false, it will not apply this member property to the cell\.<br />|
|[TFlxBorders](TFlxBorders/index.md)|Border style for a cell\.<br />|
|[TFlxChartFont](TFlxChartFont/index.md)|A TFlxFont with Scaling factor\. Scaling factor might be different than 1 if the chart has Autosize Fonts\. To get the real value of the font, you need to multiply by the factor\.<br />|
|[TFlxConsts](TFlxConsts/index.md)|Utility methods and constants usable anywhere\.<br />|
|[TFlxDateTime](TFlxDateTime/index.md)|Use this class to convert between a Date expressed on Excel format \(a double\) and a TDateTime\.<br />|
|[TFlxFillPattern](TFlxFillPattern/index.md)|Fill pattern and color for the background of a cell\.<br />|
|[TFlxFont](TFlxFont/index.md)|Encapsulation of an Excel Font\.<br />|
|[TFlxFormat](TFlxFormat/index.md)|Format for one cell or named style\.<br />Cell formats are used to format cells, Named styles to create styles\. A Cell format can have a parent style format, even when normally this is null \(parent is normal format\)\.<br />Named styles will have a non\-null Style property\. Cell formats will have style = null\.<br />|
|[TFlxMessages](TFlxMessages/index.md)|FlexCel Native string Constants\. It reads the resources from the active locale, and returns the correct string\.<br />If your language is not supported and you feel like translating the messages, please send us a copy\. We will include it on the next FlexCel version\.<br /><br /><br />To add a new language:[...[more]](TFlxMessages/index.md)<br /><br />|
|[TFlxNumberFormat](TFlxNumberFormat/index.md)|Static class to convert cells to formatted strings\. It uses format strings from Excel, that are different to those on \.net, so we have to try to reconcile the diffs\.<br />|
|[TFlxOneBorder](TFlxOneBorder/index.md)|Border style and color for one of the 4 sides of a cell\.<br />|
|[TFlxPartialFormat](TFlxPartialFormat/index.md)|This structure holds together the format definition for a cell, and which parts of that format definition should be applied\. With this you can apply only parts of the format to a cell\.<br />|
|[TFormula](TFormula/index.md)|An Excel formula\. Use this class to pass a formula to an Excel sheet\.<br />|
|[TFormulaMessages](TFormulaMessages/index.md)|Tokens that can be used on a formula\.<br />|
|[TFormulaSpan](TFormulaSpan/index.md)|This structure is used in formulas that span more than one cell, like some array formulas, or "what\-if" table formulas\.<br />|
|[TFormulaValue](TFormulaValue/index.md)|Represents a value inside a formula\. it might be an array of values in case it is an array formula\.<br />|
|[TGradientStop](TGradientStop/index.md)|Represents one of the points in a Gradient definition for an Excel cell\. Note that drawings \(autoshapes, charts, etc\) use a different Gradient definition: [TDrawingGradientStop](TDrawingGradientStop/index.md)|
|[THeaderAndFooter](THeaderAndFooter/index.md)|Contains all information about headers and footers in an Excel sheet\.<br />|
|[THeaderOrFooter&#8203;Anchor](THeaderOrFooterAnchor/index.md)|Image information for an image inside a header or footer\.<br />|
|[THSLColor](THSLColor/index.md)|Implements a simple representation of a color in Hue/Saturation/Lum colorspace\.<br />|
|[THtmlColors](THtmlColors/index.md)|Converts between Color structs and HTML values\.<br />|
|[THtmlDataUri](THtmlDataUri/index.md)|Provides functionality to create a data uri from data\.<br />|
|[THtmlEntities](THtmlEntities/index.md)|Contains a list of HTML entities and their values|
|[THtmlFixes](THtmlFixes/index.md)|Defines special fixes to the generated files to workaround browser bugs\.<br />|
|[THtmlTag](THtmlTag/index.md)|Contains an HTML tag and its position on the string\.<br />|
|[THtmlTagCreator](THtmlTagCreator/index.md)|Creates html tags for different actions, and depending on the HTML style\.<br />|
|[THyperLink](THyperLink/index.md)|An encapsulation of an Excel hyperlink\.<br />|
|[TImageUtils](TImageUtils/index.md)|Utilities for manipulating images\.<br />|
|[TLabColor](TLabColor/index.md)|Implements a simple representation of a color in CIE\-L\*a\*b\* colorspace\. This colorspace is mostly used for finding distances between colors\.<br />|
|[TLineArrow](TLineArrow/index.md)|Describes an arrow at the end of a line\. This struct is immutable\.<br />|
|[TLinkedStyle](TLinkedStyle/index.md)|This class is used as a part of a [TFlxFormat](TFlxFormat/index.md) class, and stores how a cell format is linked to a style\.<br />|
|[TPaperDimensions](TPaperDimensions/index.md)|Dimensions of an Excel paper|
|[TPrinterDriver&#8203;Settings](TPrinterDriverSettings/index.md)|Printer specific settings\. It is a byte array with a Win32 DEVMODE struct\.<br />|
|[TProtectedRange](TProtectedRange/index.md)|Specifies a protected range in a sheet\. You can define those ranges in Excel 2007 by going to "Review" tab and selecting "Allow Users to Edit Ranges" In Excel 2003, they are available under "Menu\-&#8203;>Tools\-&#8203;>Protection"&#8203;\.&#8203;<br />|
|[TRichString](TRichString/index.md)|A string cell value with its rich text information\.<br />RTFRuns is an array of TRTFRun structures, where each struct identifies a font style for a portion of text\.<br />For example, if you have: Value = "Hello" RTFRuns = \{FirstChar:1 Font:Font1, FirstChar:3, Font:Font2\}<br />"H" \(char 0\) will be formatted with the specific cell format\.<br /><br />"el" \(chars 1 and 2\) will have Font1<br />"lo" \(chars 3 and 4\) will have Font2<br />|
|[TRTFRun](TRTFRun/index.md)|One RTF run for the text in a cell\. FirstChar is the first \(base 0\) character to apply the format, and Font is the font definition for the text|
|[TScRGBColor](TScRGBColor/index.md)|Implements a simple representation of a color in scRGB colorspace\. Components are doubles going from 0 to 1\.<br />|
|[TShapeConnector](TShapeConnector/index.md)|Used to link two different shapes with a connector\.<br />|
|[TSharedWorkbook&#8203;Protection&#8203;Options](TSharedWorkbookProtectionOptions/index.md)|Options for protecting the change list in a shared workbook\. In Excel you can change this settings in Protection\->Protect Shared Workbook\.<br />|
|[TSheetProtection&#8203;Options](TSheetProtectionOptions/index.md)|Options for protecting a sheet\.<br />|
|[TSheetView](TSheetView/index.md)|This class has the different "Page View" modes that you can choose in Excel, ad properties of each mode\.<br />|
|[TSingleFormulaValue](TSingleFormulaValue/index.md)|Represents a single value inside a formula\.<br />|
|[TSpinProperties](TSpinProperties/index.md)|Spin properties of a scrollbar, spinner, listbox or combobox\.<br />|
|[TStandardMimeType](TStandardMimeType/index.md)|Mime types for common file types\.<br />|
|[TSVGAttribute](TSVGAttribute/index.md)|Represents an attribute for using in SVG\.<br />|
|[TSVGBlip](TSVGBlip/index.md)|Contains the data of an SVG image, when the blip is of SVG type\.<br />|
|[TTableApplyBorders](TTableApplyBorders/index.md)|Determines which parts of the borders will be applied in the Table\.<br />|
|[TTableApplyFill](TTableApplyFill/index.md)|Determines which parts of the pattern will be applied in the table\.<br />|
|[TTableApplyFont](TTableApplyFont/index.md)|Determines which parts of the font will be applied in the Table\.<br />|
|[TTableBorders](TTableBorders/index.md)|Determines which parts of the borders will be applied in the Table\.<br />|
|[TTableColumn&#8203;Definition](TTableColumnDefinition/index.md)|Contains the definition for a column in an Excel table\. This is mostly useful if the table doesn't have headers; since when the table has headers, the columns are inferred from the cells where the header is\.<br />|
|[TTableFont](TTableFont/index.md)|Determines which parts of the font will be applied in the Table\.<br />|
|[TTableFormula](TTableFormula/index.md)|Contains the formula for a table total or calculated formula\.<br />|
|[TTableStyle](TTableStyle/index.md)|Defines a table style\.<br />|
|[TThemeTextFont](TThemeTextFont/index.md)|The characteristics that define a font\.<br />|
|[TUIColor](TUIColor/index.md)|Represents a color used to draw in a canvas \(gdi\+, wpf, etc\) in a way that is independent of the drawing framework\.<br />|
|[TUIGradientStop](TUIGradientStop/index.md)|A structure describing a gradient point, with its color and position in the gradient\.<br />|
|[TUIPointF](TUIPointF/index.md)|Platform independent point|
|[TUIRectangle](TUIRectangle/index.md)|A platform independent rectangle\. Coordinates are floating point numbers\.<br />|
|[TUISize](TUISize/index.md)|A platform independent Size structure\. Width and Height are floating point numbers\.<br />|
|[TUITextDecoration](TUITextDecoration/index.md)|Defines appearance of decorative lines used in text, like underline or strikeout\.<br />|
|[TVirtualCellValue](TVirtualCellValue/index.md)|Represents a cell, including the row, column and sheet where it was read\.<br />|
|[TWorkbookProtection&#8203;Options](TWorkbookProtectionOptions/index.md)|Options for protecting the workbook\.<br />|
|[TXls3DRange](TXls3DRange/index.md)|A 3d Excel range\.<br />|
|[TXlsCellRange](TXlsCellRange/index.md)|An Excel Cell range, 1\-based\.<br />|
|[TXlsChartLabel&#8203;Position](TXlsChartLabelPosition/index.md)|Stores a label position in the format used in xls files\. The numbers can have many different meanings depending on where they are applied\.<br />|
|[TXlsMargins](TXlsMargins/index.md)|Sheet margin for printing, in inches\.<br />|
|[TXlsNamedRange](TXlsNamedRange/index.md)|An Excel named range\.<br />|


## Interfaces

|Name|Description|
|---|---|
|[IAreaChartOptions](IAreaChartOptions/index.md)|Options specific for an Area chart\.<br />|
|[IAreaLineChart&#8203;Options](IAreaLineChartOptions/index.md)|Options specific for a Line or Area chart\.<br />|
|[IBarChartOptions](IBarChartOptions/index.md)|Options for a Bar or Column chart\.<br />|
|[IBaseImageProperties](IBaseImageProperties/index.md)|Image information, for headers and footers, normal images or objects in general\.<br />|
|[IBlip](IBlip/index.md)|Picture and properties used in a Blip fill\.<br />|
|[IBlipFill](IBlipFill/index.md)|Shapes are filled with an image\.<br />|
|[IChart3DOptions](IChart3DOptions/index.md)|Holds the 3D properties of the chart\.<br />|
|[IChartAxis](IChartAxis/index.md)|A class encapsulating the information of an axis|
|[IChartBubbleSeries](IChartBubbleSeries/index.md)|Returns the the bubble values for a bubble chart\.<br />|
|[IChartFillOptions](IChartFillOptions/index.md)|Fill options for a chart element\.<br />|
|[IChartFrameOptions](IChartFrameOptions/index.md)|Description of a box, its coordinates, fill style and line style\.<br />|
|[IChartLegend](IChartLegend/index.md)|Description of the chart's legend box\.<br />|
|[IChartLineOptions](IChartLineOptions/index.md)|Line style options for an element of a chart\.<br />|
|[IChartOptions](IChartOptions/index.md)|Base class for options specific to the type of chart\.<br />|
|[IChartPlotArea](IChartPlotArea/index.md)|Line and fill styles for the Plot Area\.<br />|
|[IChartSeries](IChartSeries/index.md)|The definition for a series, and the values of it\.<br />|
|[IChartSeries&#8203;Fill&#8203;Options](IChartSeriesFillOptions/index.md)|Fill options for a series or a point inside a series\.<br />|
|[IChartSeries&#8203;Line&#8203;Options](IChartSeriesLineOptions/index.md)|Line style options for a series or a point inside a series\.<br />|
|[IChartTextOptions](IChartTextOptions/index.md)|Options for text inside the chart\.<br />|
|[IChartTrendline](IChartTrendline/index.md)|This class holds a definition for a trendline\.<br />|
|[ICommentProperties](ICommentProperties/index.md)|Holds the properties for a comment\. This class is a descendant of [IObjectProperties](IObjectProperties/index.md), and it adds specific behavior for a comment\.<br />|
|[IConditional&#8203;Above&#8203;Average&#8203;Rule](IConditionalAboveAverageRule/index.md)|A conditional format rule which highlights cells which are below or above the average value of the group of cells\.<br />|
|[IConditional&#8203;Base&#8203;Text&#8203;Rule](IConditionalBaseTextRule/index.md)|A base conditional format rule which highlights cells which contain specific text\. This class is not used directly, you use the descendants\.<br />|
|[IConditional&#8203;Begins&#8203;With&#8203;Text&#8203;Rule](IConditionalBeginsWithTextRule/index.md)|A conditional format rule which highlights cells which start with some text\.<br />|
|[IConditional&#8203;Cell&#8203;IsRule](IConditionalCellIsRule/index.md)|A conditional format rule specified by the value on a cell \(less than, equal, etc\)\.<br />|
|[IConditional&#8203;Color&#8203;Scale&#8203;Rule](IConditionalColorScaleRule/index.md)|A conditional format rule specified as a color scale\.<br />|
|[IConditional&#8203;Contains&#8203;Blanks&#8203;Rule](IConditionalContainsBlanksRule/index.md)|A conditional format rule which highlights blank cells\.<br />|
|[IConditional&#8203;Contains&#8203;Errors&#8203;Rule](IConditionalContainsErrorsRule/index.md)|A conditional format rule which highlights cells with errors\.<br />|
|[IConditional&#8203;Contains&#8203;Text&#8203;Rule](IConditionalContainsTextRule/index.md)|A conditional format rule which highlights cells which contain some text\.<br />|
|[IConditional&#8203;Data&#8203;BarRule](IConditionalDataBarRule/index.md)|A conditional format rule specified as a Data Bar\.<br />|
|[IConditional&#8203;Duplicate&#8203;Values&#8203;Rule](IConditionalDuplicateValuesRule/index.md)|A conditional format rule which highlights duplicated values\.<br />|
|[IConditional&#8203;Ends&#8203;With&#8203;Text&#8203;Rule](IConditionalEndsWithTextRule/index.md)|A conditional format rule which highlights cells which end with some text\.<br />|
|[IConditional&#8203;Expression&#8203;Rule](IConditionalExpressionRule/index.md)|A conditional format rule specified by a formula\.<br />|
|[IConditional&#8203;Format&#8203;Rule](IConditionalFormatRule/index.md)|A rule specifying a conditional format\. You cannot create instances of this class, only of their children\.<br />|
|[IConditional&#8203;Format&#8203;Standard&#8203;DefRule](IConditionalFormatStandardDefRule/index.md)|A conditional format rule which modifies the cell format \(color, font, etc\)\. This is different from other rules as databars or iconsets\.<br />|
|[IConditional&#8203;Format&#8203;Values&#8203;Rule](IConditionalFormatValuesRule/index.md)|An abstract class which has common properties for a Databars, IconSet or ColorScale rule\.<br />|
|[IConditional&#8203;Icon&#8203;SetRule](IConditionalIconSetRule/index.md)|A conditional format rule specified as an icon Set\.<br />|
|[IConditional&#8203;NotContains&#8203;Blanks&#8203;Rule](IConditionalNotContainsBlanksRule/index.md)|A conditional format rule which highlights not blank cells\.<br />|
|[IConditional&#8203;NotContains&#8203;Errors&#8203;Rule](IConditionalNotContainsErrorsRule/index.md)|A conditional format rule which highlights cells without errors\.<br />|
|[IConditional&#8203;NotContains&#8203;Text&#8203;Rule](IConditionalNotContainsTextRule/index.md)|A conditional format rule which highlights cells which don't contain some text\.<br />|
|[IConditional&#8203;Time&#8203;Period&#8203;Rule](IConditionalTimePeriodRule/index.md)|A conditional format rule which highlights cells which are in a specific time period\. Note that it will also apply to number intervals, since dates are formatted numbers\.<br />|
|[IConditionalTopNRule](IConditionalTopNRule/index.md)|A conditional format rule specified by the top\-N or bottom\-N values\.<br />|
|[IConditional&#8203;Unique&#8203;Values&#8203;Rule](IConditionalUniqueValuesRule/index.md)|A conditional format rule which highlights unique values\.<br />|
|[ICustomTableStyle](ICustomTableStyle/index.md)|Represents a custom table style\.<br />|
|[IDataConnections](IDataConnections/index.md)|Collection of data connections in a file\.<br />|
|[IDataLabel](IDataLabel/index.md)|Represents one data label on the chart\.<br />|
|[IDrawingConditional&#8203;Format](IDrawingConditionalFormat/index.md)|This class contains the data needed to draw a "complex" conditional format like a databar or iconset\.<br />It is used for exporting xls/x files to drawings or pdf\.<br />|
|[IEffectProperties](IEffectProperties/index.md)|A class encapsulating an effect that can be used for subtle, intense or moderate types\. This class can contain either a standard list of effects \(which you can access with EffectLst\) or a Directed Acyclic Graph \(DAG\)\.<br />One of EffectLst or EffectDag will always be null\.<br />|
|[IEffectStyle](IEffectStyle/index.md)|A class encapsulating a style including 3D styles\.<br />|
|[IEmbeddedObjects](IEmbeddedObjects/index.md)|Use this interface to read or write Embedded drawing objects inside other object\.<br />|
|[IExcelChart](IExcelChart/index.md)|Information for a chart inside a sheet or an object\.<br />|
|[IExcelGradient](IExcelGradient/index.md)|Represents a gradient fill for a background cell\. This class is abstract, you need to use its children: [IExcelLinearGradient](IExcelLinearGradient/index.md) and [IExcelRectangular&#8203;Gradient](IExcelRectangularGradient/index.md)|
|[IExcelLinearGradient](IExcelLinearGradient/index.md)|A linear gradient used for filling a background\.<br />|
|[IExcelRectangular&#8203;Gradient](IExcelRectangularGradient/index.md)|A rectangular gradient used for filling a background\.<br />|
|[IFillStyle](IFillStyle/index.md)|Base definition for a Drawing fill style\. This class is abstract, and you should use its descendants like [ISolidFill](ISolidFill/index.md) or [IGradientFill](IGradientFill/index.md)|
|[IGradientFill](IGradientFill/index.md)|Shapes are filled with a gradient\.<br />|
|[IGroupFill](IGroupFill/index.md)|Shape is part of a group and filled with its parent fill style\.<br />|
|[IHeaderOrFooter&#8203;Image&#8203;Properties](IHeaderOrFooterImageProperties/index.md)|Image information for an image embedded inside a header or footer\.<br />|
|[IHtmlFontEvent](IHtmlFontEvent/index.md)|Provides a method to customize the fonts used in the HTML methods\.<br />|
|[IImageProperties](IImageProperties/index.md)|Image information for a normal image\.<br />|
|[ILineChartOptions](ILineChartOptions/index.md)|Options specific for a Line chart\.<br />|
|[ILineStyle](ILineStyle/index.md)|Definition for a Drawing line style\.<br />|
|[INoFill](INoFill/index.md)|There is no fill associated with the shapes\.<br />|
|[IObjectProperties](IObjectProperties/index.md)|Holds the properties for an object\.<br />|
|[IPatternFill](IPatternFill/index.md)|Shapes are filled with a texture\.<br />|
|[IPieChartOptions](IPieChartOptions/index.md)|Options specific for a Pie chart\.<br />|
|[IRadarChartOptions](IRadarChartOptions/index.md)|Options specific for a Radar chart\.<br />|
|[IRowColSize](IRowColSize/index.md)|Interface for row heights and columns widths\. XlsFile implements this interface, so you can pass an XlsFile object anytime you need to pass this interface\.<br />|
|[IScatterChartOptions](IScatterChartOptions/index.md)|Options specific for a Scatter/Bubble chart\.<br />|
|[IShapeEffects](IShapeEffects/index.md)|Contains information for the basic effects of an autoshape \(subtle, none or moderate\)\.<br />|
|[IShapeFill](IShapeFill/index.md)|Contains the information for the fill of an autoshape\.<br />|
|[IShapeFont](IShapeFont/index.md)|Contains information for the font of an autoshape\.<br />|
|[IShapeLine](IShapeLine/index.md)|Contains the information for the line style for an autoshape\.<br />|
|[IShapeOptionList](IShapeOptionList/index.md)|This class holds a list of key/values pairs specifying the options for a shape\.<br />To Get a value from it, use: ShapeOptionList\[&#8203;TShape&#8203;Option\.&#8203;xxx\]&#8203;;|
|[IShapeProperties](IShapeProperties/index.md)|A class describing an Excel graphics object\.<br />|
|[ISolidFill](ISolidFill/index.md)|Shapes are filled with a solid color\.<br />|
|[IStackedOptions](IStackedOptions/index.md)|Interface for charts that can be stacked\.<br />|
|[ITableDefinition](ITableDefinition/index.md)|Contains the definition of an Excel table\.<br />|
|[ITheme](ITheme/index.md)|Contains a complete definition for an Office Theme\.<br />|
|[IThemeColorScheme](IThemeColorScheme/index.md)|A color scheme for a theme\.<br />|
|[IThemeElements](IThemeElements/index.md)|Definitions of the elements in a theme \(colors, fonts, formats\)\. This is the main part of a theme\.<br />|
|[IThemeFontScheme](IThemeFontScheme/index.md)|Represents the fonts for a theme\.<br />|
|[IThemeFormatScheme](IThemeFormatScheme/index.md)|Represents the drawing formats \(fill styles, line styles, effects\) for a theme\.<br />|
|[ITokenList](ITokenList/index.md)|A list of tokens which create a formula\.<br />|
|[IUnknownChartOptions](IUnknownChartOptions/index.md)|Options for an unknown chart\. This class does not have any information except the charttype\.<br />|
|[IUserDefined&#8203;Function&#8203;Aggregator](IUserDefinedFunctionAggregator/index.md)|This interface is passed to methods that will process the workbook\. Implement your own custom decendant to create new functions\.<br />|
|[IXmlMap](IXmlMap/index.md)|Encapsulates the XML Maps in a file\.<br />|


## Enumerations

|Name|Description|
|---|---|
|[TArrowLen](TArrowLen.md)|The length of an arrow head\.<br />|
|[TArrowStyle](TArrowStyle.md)|Style of an arrow\.<br />|
|[TArrowWidth](TArrowWidth.md)|Preset width for an arrow\.<br />|
|[TAutofitMerged](TAutofitMerged.md)|Specifies how a merged cell will be autofitted\. For example, if you have a merged cell from row 1 to 4, You might want to increase the size of the first row, the second, the last, or every row a little\.<br />|
|[TAutomaticColor](TAutomaticColor.md)|A list of special colors that depend on the user settings in windows\.<br />|
|[TAxisLabelPosition](TAxisLabelPosition.md)|Position of the labels on the axis\.<br />|
|[TAxisType](TAxisType.md)|Type of axis\.<br />|
|[TBackgroundMode](TBackgroundMode.md)|How to draw backgrounds of text\.<br />|
|[TBlipCompression](TBlipCompression.md)|This type specifies the amount of compression that has been used for a particular picture\.<br />|
|[TBlipTransformType](TBlipTransformType.md)|The type of transform applied to an image\.<br />|
|[TBubbleSizeType](TBubbleSizeType.md)|What the bubble size means\.<br />|
|[TBuiltInStyle](TBuiltInStyle.md)|Enumerator with all built\-in styles in Excel\.<br />|
|[TCategoryAxisOptions](TCategoryAxisOptions.md)|Options for a Category Axis\.<br />|
|[TCellIndentation&#8203;Rendering](TCellIndentationRendering.md)|Defines how FlexCel renders cell indentation when exporting to pdf or printing\.<br />|
|[TCellType](TCellType.md)|This enumeration holds all the possible datatypes inside a cell\.<br />|
|[TCellValueType](TCellValueType.md)|This enumeration holds all the possible datatypes inside a cell\.<br />|
|[TCfvoType](TCfvoType.md)|Type of a Value\-Object for a conditional format\.<br />|
|[TChartAxisPos](TChartAxisPos.md)|Axis postion\.<br />|
|[TChartErrorBar&#8203;BarType](TChartErrorBarBarType.md)|Specifies the possible ways to draw an error bar\.<br />|
|[TChartErrorBar&#8203;Direction](TChartErrorBarDirection.md)|Direction of an Error bar in a chart\.<br />|
|[TChartErrorBar&#8203;Error&#8203;Type](TChartErrorBarErrorType.md)|Error amount type for the error bar\.<br />|
|[TChartLabelPosition&#8203;Mode](TChartLabelPositionMode.md)|How coordinates are stored for a label when it is manually positioned\.<br />|
|[TChartLayoutMode](TChartLayoutMode.md)|Specifies how the coordinates of a chart rectangle apply\.<br />|
|[TChartLayoutTarget](TChartLayoutTarget.md)|Defines if the coordinates of the enclosing rectangle include the axis marks and labels\.<br />|
|[TChartLegend&#8203;Placement](TChartLegendPlacement.md)|Position of the legend inside the chart\.<br />|
|[TChartLineStyle](TChartLineStyle.md)|Line styles for a chart object\.<br />|
|[TChartLineWeight](TChartLineWeight.md)|Different widths for chart lines\. Since Excel 2007 this isn't used anymore, as you can use arbitrary line widths\.<br />|
|[TChartMarkerType](TChartMarkerType.md)|Kind of marker\.<br />|
|[TChartRadarStyle](TChartRadarStyle.md)|Style for the radar chart\.<br />|
|[TChartTrendlineType](TChartTrendlineType.md)|Defines the type of trendline\.<br />|
|[TChartType](TChartType.md)|Chart style\.<br />|
|[TCheckboxState](TCheckboxState.md)|Possible values of a checkbox in a sheet\.<br />|
|[TClippingStyle](TClippingStyle.md)|Can be used to clip into a region instead of drawing on it\.<br />|
|[TCollapseChildren&#8203;Mode](TCollapseChildrenMode.md)|Determines how the children of the node of an outline will be when the node  is collapsed or expanded\.<br />|
|[TColorTransformType](TColorTransformType.md)|List of transformations that can be done to a color\.<br />|
|[TColorType](TColorType.md)|Defines which one of the values stored in a [TExcelColor](TExcelColor/index.md) structure is the one that must be used\.<br />|
|[TColumnImportType](TColumnImportType.md)|Handles how to convert a column from text when importing a text file\.<br />|
|[TCompoundLineType](TCompoundLineType.md)|Type of line\.<br />|
|[TCompressionLevel](TCompressionLevel.md)|This specifies how much the xlsx or pdf files must be compressed\. The bigger compression ratio, the slower it will be to generate the files\.<br />|
|[TCondFmtError](TCondFmtError.md)|Errors that might happen in a conditional format\.<br />|
|[TCondFmtIconSet](TCondFmtIconSet.md)|Different icon sets used in conditional formatting\.<br />|
|[TConditional&#8203;Format&#8203;Kind](TConditionalFormatKind.md)|Defines which kind of conditional formatting the rule contains\.<br />|
|[TConditionType](TConditionType.md)|A list of conditional operators that you can apply in a Conditional format\.<br />|
|[TContentTransfer&#8203;Encoding](TContentTransferEncoding.md)|Defines how a part of a MIME message will be coded\.<br />|
|[TDataBarAxisPosition](TDataBarAxisPosition.md)|Axis position for the databar\.<br />|
|[TDataBarDirection](TDataBarDirection.md)|The direction of the databar\.<br />|
|[TDataBindingLoadMode](TDataBindingLoadMode.md)|Specifies the loading mode of an XML Map databinding\.<br />|
|[TDataConnection&#8203;Credential&#8203;Method](TDataConnectionCredentialMethod.md)|Credentials method used for server access\.<br />|
|[TDataConnection&#8203;Field&#8203;Type](TDataConnectionFieldType.md)|These are the possible data types to use when importing text into the SpreadsheetML document\. Strings are converted to these data types in the worksheet\.<br />|
|[TDataConnection&#8203;File&#8203;Type](TDataConnectionFileType.md)|The file type being used for text import\.<br />|
|[TDataConnection&#8203;Html&#8203;Format](TDataConnectionHtmlFormat.md)|How to handle formatting from the HTML source\.<br />|
|[TDataConnection&#8203;Parameter&#8203;Type](TDataConnectionParameterType.md)|Specifies how a parameter is refreshed\.<br />|
|[TDataConnection&#8203;Qualifier](TDataConnectionQualifier.md)|Qualifier to use to denote string data types in when text is imported from an external file\.<br />|
|[TDataConnection&#8203;Reconnection&#8203;Method](TDataConnectionReconnectionMethod.md)|How to reconnect when a connection fails\.<br />|
|[TDataConnectionType](TDataConnectionType.md)|Represents a connection type\. This enumeration lists the documented values, but there could be other values peresent in the file\.<br />|
|[TDataLabelPosition](TDataLabelPosition.md)|Defines where a label is displayed on a chart\.<br />|
|[TDataValidation&#8203;Condition&#8203;Type](TDataValidationConditionType.md)|Defines the condition used in the data validation box\.<br />|
|[TDataValidation&#8203;Data&#8203;Type](TDataValidationDataType.md)|Possible types of data validation\.<br />|
|[TDataValidationIcon](TDataValidationIcon.md)|Icon to be displayed in the error box of a data validation action\. Note that this not only affects the icon used, but the possible values\.<br />An information icon will allow you to enter an invalid value in a cell, a stop icon will not\.<br />|
|[TDataValidation&#8203;ImeMode](TDataValidationImeMode.md)|The IME \(input method editor\) mode enforced by a data validation\.<br />|
|[TDateUnits](TDateUnits.md)|Date units for a date axis\.<br />|
|[TDocumentCustom&#8203;Property&#8203;Type](TDocumentCustomPropertyType.md)|Defines which kind of property is a custom property\.<br />|
|[TDrawingAlignment](TDrawingAlignment.md)|Specifies the alignment types for text in a drawing\.<br />|
|[TDrawingColorType](TDrawingColorType.md)|Defines the kind of colors that might be stored inside a color definition in a drawing or a theme\.<br />|
|[TDrawingFontAlign](TDrawingFontAlign.md)|Different types of font alignment\.<br />|
|[TDrawingFontCharSet](TDrawingFontCharSet.md)|Character set for a font as defined in the DrawingML standard\.<br />|
|[TDrawingPattern](TDrawingPattern.md)|Different types of patterns for filling an Excel 2007 object\. This is different from the patterns to fill a cell\.<br />|
|[TDrawingRectAlign](TDrawingRectAlign.md)|How to position two rectangles relative to each other\.<br />|
|[TDrawingText&#8203;Capitalization](TDrawingTextCapitalization.md)|how text is capitalized when rendered\.<br />|
|[TDrawingTextStrike](TDrawingTextStrike.md)|How the text is stroke out\.<br />|
|[TDrawingUnderline&#8203;Style](TDrawingUnderlineStyle.md)|Possible underline types in a drawing\.<br />|
|[TDrawingValueType](TDrawingValueType.md)|Data that can be stored inside a [TDrawingValue](TDrawingValue/index.md)|
|[TEncryptionAlgorithm](TEncryptionAlgorithm.md)|Encryption algorithms supported in xlsx encrypted files\.<br />|
|[TEncryptionType](TEncryptionType.md)|How the file is encrypted\. This applies only to xls files\. Xlsx files are encrypted using the Agile xlsx encryption\.<br />|
|[TEnterStyle](TEnterStyle.md)|Defines how characters will be converted when encoding a string as Html\.<br />|
|[TEscherConnectorType](TEscherConnectorType.md)|The type of connector\.<br />|
|[TExcelFileError&#8203;Actions](TExcelFileErrorActions.md)|Enumerates what to do on different FlexCel error situations\.<br />|
|[TExcelFileFormat](TExcelFileFormat.md)|Different Excel versions create different empty xls/xlsx files\. For example an empty xls file created by Excel 2003 will have "Arial" as its default font, and one created by Excel 2007 will have "Calibri"\. By default, when you call [TExcelFile.NewFile](TExcelFile/NewFile.md) FlexCel will create a file that is similar to what Excel 2003 would create\. This is fine, but if you want to start for example from an  empty Excel 2007 file, you can do so by calling NewFile\(\) with this enumeration\.<br />|
|[TExcelVersion](TExcelVersion.md)|Defines which Excel version FlexCel is targeting\. Note that while on v2007 you still can make xls 97 spreadsheets\.<br />|
|[TExcludedRecords](TExcludedRecords.md)|A list of records that might not be saved into a file when using [TExcelFile.&#8203;Save&#8203;ForHashing\(&#8203;&#8203;TStream\)](TExcelFile/SaveForHashing.md#texcelfilesaveforhashingtstream)|
|[TFileFormats](TFileFormats.md)|Supported file formats to read and write files\.<br />|
|[TFillStyleType](TFillStyleType.md)|Stores the different kind of fill styles for an autoshape or drawing\.<br />|
|[TFillType](TFillType.md)|Type of fill for an autoshape\. \(In xls files\)|
|[TFlexCelClipboard&#8203;Format](TFlexCelClipboardFormat.md)|The file fomats that FlexCel can natively put in the clipboard\.<br />|
|[TFlexCelError](TFlexCelError.md)|An enumeration of all possible FlexCel non fatal errors that can be logged\.<br />|
|[TFlexCelImage&#8203;Horiz&#8203;Align](TFlexCelImageHorizAlign.md)|Sets how an image is aligned inside a box\.<br />|
|[TFlexCelImage&#8203;Vert&#8203;Align](TFlexCelImageVertAlign.md)|How an image is aligned inside a box\.<br />|
|[TFlipMode](TFlipMode.md)|How an image will be flipped when filling a pattern\.<br />|
|[TFlxAnchorType](TFlxAnchorType.md)|How an image behaves when inserting/copying rows/columns|
|[TFlxBorderStyle](TFlxBorderStyle.md)|Cell border style\.<br />|
|[TFlxDiagonalBorder](TFlxDiagonalBorder.md)|Diagonal border style\.<br />|
|[TFlxErr](TFlxErr.md)|Error Codes used in Exceptions\.<br />|
|[TFlxFontStyles](TFlxFontStyles.md)|Font style\. You can "or" on "and" it to get the actual styles\.<br />For example, to set style to bold\+italic,  you should use TFlxFontStyles\.Bold \| TFlxFontStyles\.&#8203;Italic\.&#8203;<br />to check if style includes italic, use \(\(Style &amp; TFlxFontStyles\.&#8203;Italic\)&#8203;\!&#8203;=0\)|
|[TFlxFormulaError&#8203;Value](TFlxFormulaErrorValue.md)|Error codes for cells on excel|
|[TFlxInsertMode](TFlxInsertMode.md)|Inserting mode\. **Important:** This enumeration is also used when deleting ranges\. When deleting, Down means Up and Right means Left\.<br />|
|[TFlxMessage](TFlxMessage.md)|Some custom strings\.<br />|
|[TFlxParam](TFlxParam.md)|Parameter names that can go into an "invalid params" error message\.<br />|
|[TFlxPatternStyle](TFlxPatternStyle.md)|Pattern style\.<br />|
|[TFlxReadingOrder](TFlxReadingOrder.md)|Reading order for a cell\.<br />|
|[TFlxUnderline](TFlxUnderline.md)|Underline type\.<br />|
|[TFmReturnType](TFmReturnType.md)|Formula return types\.\.\. A value, an array or a reference\.<br />|
|[TFontCharSet](TFontCharSet.md)|Character set for a font as defined in the DrawingML standard\.<br />|
|[TFontScheme](TFontScheme.md)|Specifies the scheme to which a font belongs in the theme\. This attribute is only valid in Excel 2007 or newer\.<br />|
|[TFormattingType](TFormattingType.md)|The elements here are different types of fill/effects/etc that can be applied to an object\.<br />Currently Excel only defines 3 types, but more can be added in future specifications\.<br />Newer types can be accessed by casting an int to TFormattingType\. \(for example "\(&#8203;TFormatting&#8203;Type\)&#8203;5"  would refer to a now non existing formatting type\)|
|[TFormulaToken](TFormulaToken.md)|Known token on a formula\.  They are not supposed to be localized, but they can be by editing formulamsg\.resx|
|[TFormulaValueType](TFormulaValueType.md)|This enumeration contains the possible values a formula might contain\.<br />|
|[TFullRecalcOn&#8203;Load&#8203;Mode](TFullRecalcOnLoadMode.md)|Defines how FlexCel will save the files so they will be recalculated or not when you open them in Excel\.<br />|
|[TFunctionGroup](TFunctionGroup.md)|Specifies the function group index if the defined name refers to a function\. The function  group defines the general category for the function\. This attribute is used when there is  an add\-in or other code project associated with the file\.<br />|
|[TGradientType](TGradientType.md)|The type of gradient stored inside a [IExcelGradient](IExcelGradient/index.md) object\.<br />|
|[THeaderAndFooterKind](THeaderAndFooterKind.md)|Different kinds of headers and footers depending on which pages they apply\.<br />|
|[THeaderAndFooterPos](THeaderAndFooterPos.md)|Different sections on a header or footer\.<br />|
|[THFlxAlignment](THFlxAlignment.md)|Horizontal Alignment on a cell\.<br />|
|[THideObjects](THideObjects.md)|Defines how objects are shown on the file\.<br />|
|[THidePrintObjects](THidePrintObjects.md)|Enumeration defining which objects should not be printed or exported to PDF\. You can 'or' more than one option together\.<br />For example, to not print images and not comments, you should specify: THidePrintObjects\.&#8203;Images \| THidePrintOption\.&#8203;Comments|
|[THtmlFileFormat](THtmlFileFormat.md)|How the html page will be saved\.<br />|
|[THtmlStyle](THtmlStyle.md)|Defines the way html is generated\.<br />|
|[THtmlVersion](THtmlVersion.md)|Defines the HTML version that will be used when exporting\.<br />|
|[THyperLinkType](THyperLinkType.md)|Possible types of cell hyperlinks\.<br />|
|[TIgnoredErrors](TIgnoredErrors.md)|Specifies what kind of errors Excel will ignore for ranges of cells\. "Errors" in a spreadsheet are the green triangles that appear in the top left corner of the cell, like "Number stored as text"\.<br />|
|[TImageColorDepth](TImageColorDepth.md)|Number of colors for the exported images\.<br />|
|[TImageExportType](TImageExportType.md)|Defines how you want to export the sheet\.<br />|
|[TImageNaming](TImageNaming.md)|Defines how images will be automatically named by FlexCel, when you do not supply a better name\.<br />|
|[TInternalNameRange](TInternalNameRange.md)|List of internal range names\.<br />On Excel, internal range names like "Print\_Area" are stored as a 1 character string\.<br />This is the list of the names and their value\.<br />You can convert an InternalNameRange into a string by casting it to a char, or by calling [TXlsNamedRange.&#8203;Get&#8203;Internal&#8203;Name](TXlsNamedRange/GetInternalName.md)<br />|
|[TJpegOrientation](TJpegOrientation.md)|Specifies the rotation of a JPEG image\.<br />|
|[TLabelDataValue](TLabelDataValue.md)|Defines what information a DataLabel should show\.<br />|
|[TLineCap](TLineCap.md)|How the line ends\.<br />|
|[TLineDashing](TLineDashing.md)|Line style \(dashes, solid, etc\)\.<br />|
|[TLineJoin](TLineJoin.md)|How a line joins with the next|
|[TLinkOption](TLinkOption.md)|Specifies to which object the label is linked to\.<br />|
|[TListBoxSelection&#8203;Type](TListBoxSelectionType.md)|Types of selection allowed in a listbox\.<br />|
|[TMultipartType](TMultipartType.md)|Different ways to define a multipart archive\.<br />|
|[TObjectType](TObjectType.md)|A type of object\. Do not confuse this with a type of shape \( [TShapeType](TShapeType.md) \) This does not describe the shape form \(like if it is a rectangle or a circle\) but the shape kind \(for example if it is a comment, an image or an autoshape\)|
|[TOperator](TOperator.md)|Operators that can be found inside a formula|
|[TOverlayBlendMode](TOverlayBlendMode.md)|Overlay blend modes\.<br />|
|[TPanePosition](TPanePosition.md)|Position on a pane when window is split|
|[TPaperSize](TPaperSize.md)|Pre\-defined Page sizes\. For Printer specific page\-sizes, see [TPrinterDriver&#8203;Settings](TPrinterDriverSettings/index.md) Note that a printer specific page size might have a value that is *not* on this enumeration\.<br />|
|[TPathShadeType](TPathShadeType.md)|Enumerates the different gradient modes for a Path gradient\.<br />|
|[TPenAlignment](TPenAlignment.md)|Specifies the alignment to be used for the underline stroke\.<br />|
|[TPitchFamily](TPitchFamily.md)|Pitch family for a font\.<br />|
|[TPlotEmptyCells](TPlotEmptyCells.md)|Defines how empty cells will be plotted in the chart\.<br />|
|[TPresetColor](TPresetColor.md)|Preset colors\.<br />|
|[TPresetShadow&#8203;Effect&#8203;Type](TPresetShadowEffectType.md)|Types of preset shadow\.<br />|
|[TPrimaryThemeColor](TPrimaryThemeColor.md)|Specifies one of the 12 theme colors\. Does not include semantic colors, which are in [TThemeColor](TThemeColor.md)|
|[TPrintComments](TPrintComments.md)|Determines how the comments will be displayed when printing\.<br />|
|[TPrintErrors](TPrintErrors.md)|Determines how to print the errors when printing or exporting a sheet\.<br />|
|[TPrintOptions](TPrintOptions.md)|How the sheet should be printed\. You can mix value together by and'ing and or'ing the flags\.<br />See the example to see how to set or clear one specific value of the enumeration\.<br />|
|[TPropertyId](TPropertyId.md)|Standard properties of an ole file\. There are two different sets of properties, the standard ones \(properties that exist for any file\) and the extended ones \(properties that exist for Ms Office documents\)|
|[TProtectionType](TProtectionType.md)|Indicates how a sheet will be protected\.<br />|
|[TQEncodeMetaInfo](TQEncodeMetaInfo.md)|Defines how a string returned by Q\-Encode will be handled\.<br />|
|[TRangeCopyMode](TRangeCopyMode.md)|What we do with the cells when we call InsertAndCopy&#8203;Range\.&#8203;<br />|
|[TRangeOp](TRangeOp.md)|Operation between ranges\.<br />|
|[TRecalcMode](TRecalcMode.md)|Sets how the excel file will be recalculated\. Normally FlexCel calculates a file only before saving and when you explicitly call [TExcelFile.&#8203;Recalc\(&#8203;&#8203;Boolean\)](TExcelFile/Recalc.md#texcelfilerecalcboolean)\. With this enum you can change that behavior\.<br />|
|[TRecalcVersion](TRecalcVersion.md)|Identifies how FlexCel will identify itself in the generated file, in order to recalculate\.<br />|
|[TReferenceStyle](TReferenceStyle.md)|Use this enumerator in the property [TExcelFile.&#8203;Formula&#8203;Reference&#8203;Style](TExcelFile/FormulaReferenceStyle.md) to specify the reference mode that FlexCel will use when you enter formulas as text or when it returns the formula text\.<br />|
|[TShapeOption](TShapeOption.md)|Many different configuration options for a shape\.<br />|
|[TShapeOptionType](TShapeOptionType.md)|Returns the type of option type\.<br />|
|[TShapePreset&#8203;Guide&#8203;Type](TShapePresetGuideType.md)|Internal use\.<br />|
|[TShapeType](TShapeType.md)|Enumeration with the different shapes\.<br />|
|[TSheetCalcMode](TSheetCalcMode.md)|How the file will be calculated by Excel\. This enum doesn't affect FlexCel recalculation\.<br />|
|[TSheetOptions](TSheetOptions.md)|General options for a sheet\. In Excel, this settings are located in Tools\-&#8203;>Options\-&#8203;>View in the "Window options" box\.<br />Most of this options can be set with dedicated methods in [TExcelFile](TExcelFile/index.md), but this type allows to set them all at once, or copy them from other file\. This options apply only to the active sheet\. For options that apply to all the sheets see [TSheetWindowOptions](TSheetWindowOptions.md)|
|[TSheetType](TSheetType.md)|Sheet types|
|[TSheetViewType](TSheetViewType.md)|The page mode of a sheet\. You select this in Excel by changing the icons at the bottom right, or from the ribbon, in the "View" tab\.<br />|
|[TSheetWindowOptions](TSheetWindowOptions.md)|General options for how sheets display\. In Excel, this settings are located in Tools\-&#8203;>Options\-&#8203;>View in the "Window options" box\.<br />This options apply only to all the sheets\. For options that apply only to the active sheet see [TSheetOptions](TSheetOptions.md)|
|[TSortFormulaMode](TSortFormulaMode.md)|Defines how FlexCel will sort a range of cells, when you call XlsFile\.Sort\. You will normally want to specify "MoveFormulas",  but for huge amounts of data where you know formulas won't matter, you might choose the "ExcelLike" mode\. Note that Excel itself doesn't adapt correctly the formulas when sorting, and it works like the ExcelLike mode\.<br />|
|[TSortOrder](TSortOrder.md)|The sort order for a sort operation\.<br />|
|[TStackedMode](TStackedMode.md)|Way the series stack one to the other\. This does not apply to all chart types\.<br />|
|[TStructRefSection](TStructRefSection.md)|This enum contains the possible values that can go into a structured reference\.<br />You can combine multiple values, but not all combinations make sense\. For example \#Data \+ \#Headers it fine, but \#All \+ \#Headers is just \#All\.<br />|
|[TStyleCategory](TStyleCategory.md)|Category to which a cell style belongs\. This is only valid for Excel 2007 or newer\.<br />|
|[TSVGExportType](TSVGExportType.md)|Customized what data will be included in an svg file\.<br />|
|[TSystemColor](TSystemColor.md)|System colors\.<br />|
|[TTableStyleType](TTableStyleType.md)|Defines the part of the table for which a tablestyle applies\.<br />|
|[TTextHorzOverflow](TTextHorzOverflow.md)|How the text in a shape will overflow horizontally once there is no more room for it\.<br />|
|[TTextRotation](TTextRotation.md)|Text direction for objects like comments, that allow rotation, but only in 90 degrees\.<br />|
|[TTextVertOverflow](TTextVertOverflow.md)|How the text in a shape will overflow vertically once there is no more room for it\.<br />Note that from the Excel UI, you can only set both Vert overflow and Horizontal overflow at the same time\.<br />|
|[TThemeColor](TThemeColor.md)|Specifies one of the 12 theme colors, or one of the 4 semantic colors\. In cells, Excel doesn't use semantic colors, but in drawings they can be used, even if the Excel UI only allows one type of color\.<br />|
|[TTickType](TTickType.md)|Ticks for an axis\.<br />|
|[TTimePeriod](TTimePeriod.md)|A time period for conditional format\.<br />|
|[TTokenType](TTokenType.md)|Enumerates the different kind of tokens you can find in a formula|
|[TTokenWhitespace&#8203;Character](TTokenWhitespaceCharacter.md)|Character used in the whitespace\.<br />|
|[TTokenWhitespace&#8203;Position](TTokenWhitespacePosition.md)|Specifies where the whitespace is added in relation to the next token\.<br />|
|[TTotalsRowFunction](TTotalsRowFunction.md)|Type of function used to summarize a table column\.<br />|
|[TUIDashStyle](TUIDashStyle.md)|Platform independent line style\.<br />|
|[TUIFontStyle](TUIFontStyle.md)|The different styles a font can have\.<br />|
|[TUIHatchStyle](TUIHatchStyle.md)|Specifies the different patterns available\.<br />|
|[TUIInterpolationMode](TUIInterpolationMode.md)|How the image will be scaled\. See System\.&#8203;Drawing\.&#8203;Drawing2D\.&#8203;Interpolation&#8203;Mode for reference\.<br />|
|[TUISmoothingMode](TUISmoothingMode.md)|Smoothing mode\. See System\.&#8203;Drawing\.&#8203;Drawing2D\.&#8203;Smoothing&#8203;Mode\.&#8203;<br />|
|[TUIStrikeout](TUIStrikeout.md)|Defines if the text is stroke out\. Currently there is only an style of strike out, which is a single strikeout\.<br />|
|[TUIUnderline](TUIUnderline.md)|Type of underline in the text\.<br />|
|[TUnsupported&#8203;Formula&#8203;Error&#8203;Type](TUnsupportedFormulaErrorType.md)|Types of error that might happen while recalculating\.<br />|
|[TUserDefined&#8203;Function&#8203;Location](TUserDefinedFunctionLocation.md)|Defines where the custom function is located, if inside a macro in the same file, or inside a macro in an external file\.<br />|
|[TUserDefined&#8203;Function&#8203;Scope](TUserDefinedFunctionScope.md)|Defines how custom functions are added to the recalculation engine\.<br />If a function is defined in both Global and Local scope, Local scope will be used\.<br />|
|[TValueAxisOptions](TValueAxisOptions.md)|Options for a Value Axis\.<br />|
|[TVFlxAlignment](TVFlxAlignment.md)|Vertical Alignment on a cell\.<br />|
|[TXlsBiffVersion](TXlsBiffVersion.md)|The specific Excel version that FlexCel will emulate when reading and saving files\.<br />|
|[TXlsImgType](TXlsImgType.md)|Possible image types on an excel sheet\.<br />|
|[TXlsSheetVisible](TXlsSheetVisible.md)|Sheet visibility\.<br />|


## Anonymous methods

|Name|Description|
|---|---|
|[TOnSheetName&#8203;Event&#8203;Handler](TOnSheetNameEventHandler.md)|Delegate used to specify which name to use for every sheet when exporting multiple sheets to multiple files\.<br />|


## Types

|Name|Description|
|---|---|
|[TCultureCreating&#8203;Event&#8203;Handler](TCultureCreatingEventHandler.md)|Delegate for CultureCreating events\. Return null to use the culture that would have been used had this event not be assigned\.<br />|
|[TFlexCelError&#8203;Event&#8203;Handler](TFlexCelErrorEventHandler.md)|Delegate for ErrorInfo events\.<br />|
|[TFontCreated&#8203;Event&#8203;Handler](TFontCreatedEventHandler.md)|Delegate for FontCreated events\.<br />|
|[TFontCreating&#8203;Event&#8203;Handler](TFontCreatingEventHandler.md)|Delegate for FontCreating events\.<br />|
|[THtmlFontEvent&#8203;Handler](THtmlFontEventHandler.md)|Delegate used to specify which fonts to use on a page\.<br />|
|[TLoadLinkedFile&#8203;Event&#8203;Handler](TLoadLinkedFileEventHandler.md)|Delegate for LoadLinkedFile event\.<br />|
|[TOnPasswordEvent&#8203;Handler](TOnPasswordEventHandler.md)|This event fires when opening an encrypted file and no password has been supplied\.<br />|
|[TVirtualCell&#8203;EndReading&#8203;Event&#8203;Handler](TVirtualCellEndReadingEventHandler.md)|Delegate for virtual cell reads\. This delegate is called after the full file has been read\.<br />|
|[TVirtualCell&#8203;Read&#8203;Event&#8203;Handler](TVirtualCellReadEventHandler.md)|Delegate for virtual cell reads\.<br />|
|[TVirtualCell&#8203;Start&#8203;Reading&#8203;Event&#8203;Handler](TVirtualCellStartReadingEventHandler.md)|Delegate for virtual cell reads\. It is called before we start reading the file, but after sheet names are known\.<br />|


## Methods

|Name|Description|
|---|---|
|[FlexCelDllInit](FlexCelDllInit.md)|Use this method to initialize FlexCel when encapsulating it in a dll\.<br /><br /><br /><br />Note that you don't normally need to call this method, as FlexCel is initialized automatically\. But when you are hosting FlexCel inside a dll instead of the main application you need to call this method before calling the methods in the dll\. Currently, this method will just initialize GDI\+ when running in Windows, because GDI\+ can't be initialized from the dll itself\. When you use this method, always call [FlexCelDllShutdown](FlexCelDllShutdown.md) before closing your app\.<br /><br /><br />|
|[FlexCelDllShutdown](FlexCelDllShutdown.md)|This method shutdowns FlexCel, and is designed to be used when you are using FlexCel inside a dll\. for more information, take a look at [FlexCelDllInit](FlexCelDllInit.md)\.<br />|
|[TUISmoothing&#8203;Mode\_&#8203;FlexCel&#8203;Default](TUISmoothingMode_FlexCelDefault.md)|Default mode used by FlexCel\. You can change this value with TUIInterpolation&#8203;Mode\_&#8203;Set&#8203;FlexCel&#8203;Default\.&#8203;<br />|
|[TUIInterpolation&#8203;Mode\_&#8203;FlexCel&#8203;Default](TUIInterpolationMode_FlexCelDefault.md)|Default mode used by FlexCel\. You can change this value with TUIInterpolation&#8203;Mode\_&#8203;Set&#8203;FlexCel&#8203;Default\.&#8203;<br />|
|[TUISmoothing&#8203;Mode\_&#8203;Set&#8203;FlexCel&#8203;Default](TUISmoothingMode_SetFlexCelDefault.md)|Sets the default mode used by FlexCel\. You can change this in your application to change how FlexCel will render the images\.<br />|
|[TUIInterpolation&#8203;Mode\_&#8203;Set&#8203;FlexCel&#8203;Default](TUIInterpolationMode_SetFlexCelDefault.md)|Sets the default mode used by FlexCel\. You can change this in your application to change how FlexCel will render the images\.<br />|
|[EncryptionFactory](EncryptionFactory.md)|Returns the encryption factory used by FlexCel\. You can use it to sign PDF files|


