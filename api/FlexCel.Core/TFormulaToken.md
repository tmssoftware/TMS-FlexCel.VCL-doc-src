---
uid: TFormulaToken
description: TFormulaToken
---

# TFormulaToken Enumeration

Known token on a formula\.  They are not supposed to be localized, but they can be by editing formulamsg\.resx

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|fmErrStart|0|'\#';|
|fmTrue|1|'TRUE';|
|fmFalse|2|'FALSE';|
|fmStartFormula|3|'=' // as in =a1\*2 or \{=1\+2\}|
|fmFormulaDecimal|4|'\.' as in '1\.2'|
|fmFormulaThousands|5|',' as in '1,300'|
|fmFunctionSep|6|',' Argument separator on a function\.<br />For example, if fmFunctionSep=';' we should write "Max\(a1;a2\)" If you want to localize this, you could use fmFunctionSep=ListSeparator|
|fmUnion|7|',' as in "=a1, b2"|
|fmIntersect|8|' ' as in a1 a2|
|fmOpenArray|9|'\{';|
|fmCloseArray|10|'\}';|
|fmOpenParen|11|'\(';|
|fmCloseParen|12|'\)';|
|fmArrayRowSep|13|'/' Separates 2 rows on an array\. It is '\\' in spanish|
|fmArrayColSep|14|',' Separates 2 columns on an array\. Ex: \{1,2\}\. It is ';' in spanish If you want to localize this, you could use fmArrayColSep=ListSeparator|
|fmAbsoluteRef|15|'$' as in $A$3|
|fmRangeSep|16|':' as in A1:A3|
|fmSingleQuote|17|' \(as in 'Sheet 1'\!A1|
|fmExternalRef|18|'\!' as in Sheet1\!a1|
|fmWorkbookOpen|19|'\[' as in c:\\\[book1\.xls\]Sheet1\!a1|
|fmWorkbookClose|20|'\]';|
|fmTableText|21|'TABLE';|
|fmPlus|22|'\+';|
|fmMinus|23|'\-';|
|fmMul|24|'\*';|
|fmDiv|25|'/';|
|fmPower|26|'^';|
|fmPercent|27|'%%';|
|fmAnd|28|'&amp;';|
|fmLT|29|'\<';|
|fmLE|30|'\<=';|
|fmEQ|31|'=';|
|fmGE|32|'>=';|
|fmGT|33|'>';|
|fmNE|34|'\<>';|
|fmR1C1\_R|35|'R' in R1C1 notation as in R1C2|
|fmR1C1\_C|36|'C' in R1C1 notation as in R1C2|
|fmR1C1RelativeRefStart|37|'\[' in R1C1 notation as in R\[1\]C\[\-2\]|
|fmR1C1RelativeRefEnd|38|'\]' in R1C1 notation as in R\[1\]C\[\-2\]|


