---
uid: SupportedExcelFunctions
---
# Supported Excel functions

This is a list of all the standard Excel functions up to Excel 2021.

Functions marked with ~~strikeout~~ are not implemented yet.
To know if a specific spreadsheet has all the formulas supported by FlexCel, you can use the [Validate Recalc](xref:Validate_Recalc-Delphi) demo

Formulas on column "Array Enabled" mean that you can enter them inside an Array formula with a range argument
(for example "if(a1:a10 &lt; 3;…;….)") All formulas can be used inside Array Formulas, but only the ones on this list can 
be used with array arguments where they would expect a single value. By "Array formulas" we mean formulas you enter with Shift-Ctrl-Enter in Excel


## Supported built-in functions

* **Total built-in functions**: 468
* **Implemented**: 353 (75%)

### Built-in functions in 2003

#### Financial

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|DB|&#x2713;| |
|DDB|&#x2713;| |
|FV|&#x2713;| |
|IPMT|&#x2713;| |
|IRR|&#x2713;| |
|~~ISPMT~~| | |
|MIRR|&#x2713;| |
|NPER|&#x2713;| |
|NPV|&#x2713;| |
|PMT|&#x2713;| |
|PPMT|&#x2713;| |
|PV|&#x2713;| |
|RATE|&#x2713;| |
|SLN|&#x2713;| |
|SYD|&#x2713;| |
|~~VDB~~| | |

#### Date & Time

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|DATE|&#x2713;|&#x2713;|
|DATEVALUE|&#x2713;|&#x2713;|
|DAY|&#x2713;|&#x2713;|
|DAYS360|&#x2713;| |
|HOUR|&#x2713;|&#x2713;|
|MINUTE|&#x2713;|&#x2713;|
|MONTH|&#x2713;|&#x2713;|
|NOW|&#x2713;|&#x2713;|
|SECOND|&#x2713;|&#x2713;|
|TIME|&#x2713;|&#x2713;|
|TIMEVALUE|&#x2713;|&#x2713;|
|TODAY|&#x2713;|&#x2713;|
|WEEKDAY|&#x2713;|&#x2713;|
|YEAR|&#x2713;|&#x2713;|
|DATEDIF|&#x2713;|&#x2713;|

#### Math & Trig

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|ABS|&#x2713;|&#x2713;|
|ACOS|&#x2713;|&#x2713;|
|ACOSH|&#x2713;|&#x2713;|
|ASIN|&#x2713;|&#x2713;|
|ASINH|&#x2713;|&#x2713;|
|ATAN|&#x2713;|&#x2713;|
|ATAN2|&#x2713;|&#x2713;|
|ATANH|&#x2713;|&#x2713;|
|CEILING|&#x2713;|&#x2713;|
|COMBIN|&#x2713;|&#x2713;|
|COS|&#x2713;|&#x2713;|
|COSH|&#x2713;|&#x2713;|
|DEGREES|&#x2713;|&#x2713;|
|EVEN|&#x2713;|&#x2713;|
|EXP|&#x2713;|&#x2713;|
|FACT|&#x2713;|&#x2713;|
|FLOOR|&#x2713;|&#x2713;|
|INT|&#x2713;|&#x2713;|
|LN|&#x2713;|&#x2713;|
|LOG|&#x2713;| |
|LOG10|&#x2713;|&#x2713;|
|~~MDETERM~~| | |
|~~MINVERSE~~| | |
|MMULT|&#x2713;|&#x2713;|
|MOD|&#x2713;|&#x2713;|
|ODD|&#x2713;|&#x2713;|
|PI|&#x2713;|&#x2713;|
|POWER|&#x2713;|&#x2713;|
|PRODUCT|&#x2713;|&#x2713;|
|RADIANS|&#x2713;|&#x2713;|
|RAND|&#x2713;|&#x2713;|
|ROMAN|&#x2713;| |
|ROUND|&#x2713;|&#x2713;|
|ROUNDDOWN|&#x2713;|&#x2713;|
|ROUNDUP|&#x2713;|&#x2713;|
|SIGN|&#x2713;|&#x2713;|
|SIN|&#x2713;|&#x2713;|
|SINH|&#x2713;|&#x2713;|
|SQRT|&#x2713;|&#x2713;|
|SUBTOTAL|&#x2713;| |
|SUM|&#x2713;|&#x2713;|
|SUMX2MY2|&#x2713;|&#x2713;|
|SUMX2PY2|&#x2713;|&#x2713;|
|SUMXMY2|&#x2713;|&#x2713;|
|SUMIF|&#x2713;|&#x2713;|
|SUMPRODUCT|&#x2713;|&#x2713;|
|SUMSQ|&#x2713;|&#x2713;|
|TAN|&#x2713;|&#x2713;|
|TANH|&#x2713;|&#x2713;|
|TRUNC|&#x2713;| |

#### Statistical

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|AVEDEV|&#x2713;|&#x2713;|
|AVERAGE|&#x2713;|&#x2713;|
|AVERAGEA|&#x2713;|&#x2713;|
|~~BETADIST~~| | |
|~~BETAINV~~| | |
|BINOMDIST|&#x2713;| |
|CHIDIST|&#x2713;| |
|CHIINV|&#x2713;| |
|CHITEST|&#x2713;|&#x2713;|
|CONFIDENCE|&#x2713;| |
|CORREL|&#x2713;| |
|COUNT|&#x2713;|&#x2713;|
|COUNTA|&#x2713;|&#x2713;|
|COUNTBLANK|&#x2713;|&#x2713;|
|COUNTIF|&#x2713;|&#x2713;|
|COVAR|&#x2713;| |
|~~CRITBINOM~~| | |
|DEVSQ|&#x2713;| |
|EXPONDIST|&#x2713;| |
|~~FDIST~~| | |
|~~FINV~~| | |
|FISHER|&#x2713;|&#x2713;|
|FISHERINV|&#x2713;|&#x2713;|
|~~FORECAST~~| | |
|FREQUENCY|&#x2713;|&#x2713;|
|~~FTEST~~| | |
|GAMMADIST|&#x2713;| |
|GAMMAINV|&#x2713;| |
|GAMMALN|&#x2713;|&#x2713;|
|GEOMEAN|&#x2713;| |
|~~GROWTH~~| | |
|HARMEAN|&#x2713;| |
|HYPGEOMDIST|&#x2713;| |
|INTERCEPT|&#x2713;| |
|KURT|&#x2713;| |
|LARGE|&#x2713;|&#x2713;|
|~~LINEST~~| | |
|~~LOGEST~~| | |
|LOGINV|&#x2713;| |
|LOGNORMDIST|&#x2713;| |
|MAX|&#x2713;|&#x2713;|
|MAXA|&#x2713;|&#x2713;|
|MEDIAN|&#x2713;|&#x2713;|
|MIN|&#x2713;|&#x2713;|
|MINA|&#x2713;|&#x2713;|
|MODE|&#x2713;|&#x2713;|
|NEGBINOMDIST|&#x2713;| |
|NORMDIST|&#x2713;| |
|NORMINV|&#x2713;| |
|NORMSDIST|&#x2713;|&#x2713;|
|NORMSINV|&#x2713;|&#x2713;|
|PEARSON|&#x2713;|&#x2713;|
|PERCENTILE|&#x2713;|&#x2713;|
|PERCENTRANK|&#x2713;| |
|PERMUT|&#x2713;|&#x2713;|
|POISSON|&#x2713;| |
|~~PROB~~| | |
|QUARTILE|&#x2713;|&#x2713;|
|RANK|&#x2713;| |
|RSQ|&#x2713;|&#x2713;|
|SKEW|&#x2713;|&#x2713;|
|SLOPE|&#x2713;|&#x2713;|
|SMALL|&#x2713;|&#x2713;|
|STANDARDIZE|&#x2713;|&#x2713;|
|STDEV|&#x2713;| |
|STDEVA|&#x2713;| |
|STDEVP|&#x2713;| |
|STDEVPA|&#x2713;| |
|STEYX|&#x2713;|&#x2713;|
|~~TDIST~~| | |
|~~TINV~~| | |
|~~TREND~~| | |
|~~TRIMMEAN~~| | |
|~~TTEST~~| | |
|VAR|&#x2713;| |
|VARA|&#x2713;| |
|VARP|&#x2713;| |
|VARPA|&#x2713;| |
|WEIBULL|&#x2713;| |
|ZTEST|&#x2713;| |

#### Lookup & Reference

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|ADDRESS|&#x2713;|&#x2713;|
|AREAS|&#x2713;| |
|CHOOSE|&#x2713;|&#x2713;|
|COLUMN|&#x2713;|&#x2713;|
|COLUMNS|&#x2713;|&#x2713;|
|HLOOKUP|&#x2713;| |
|HYPERLINK|&#x2713;| |
|INDEX|&#x2713;|&#x2713;|
|INDIRECT|&#x2713;|&#x2713;|
|LOOKUP|&#x2713;| |
|MATCH|&#x2713;|&#x2713;|
|OFFSET|&#x2713;|&#x2713;|
|ROW|&#x2713;|&#x2713;|
|ROWS|&#x2713;|&#x2713;|
|TRANSPOSE|&#x2713;|&#x2713;|
|VLOOKUP|&#x2713;| |

#### Database

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|DAVERAGE|&#x2713;| |
|DCOUNT|&#x2713;| |
|DCOUNTA|&#x2713;| |
|DGET|&#x2713;| |
|DMAX|&#x2713;| |
|DMIN|&#x2713;| |
|DPRODUCT|&#x2713;| |
|DSTDEV|&#x2713;| |
|DSTDEVP|&#x2713;| |
|DSUM|&#x2713;| |
|DVAR|&#x2713;| |
|DVARP|&#x2713;| |
|~~GETPIVOTDATA~~| | |

#### Text

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|ASC|&#x2713;|&#x2713;|
|BAHTTEXT|&#x2713;|&#x2713;|
|CHAR|&#x2713;|&#x2713;|
|CLEAN|&#x2713;|&#x2713;|
|CODE|&#x2713;|&#x2713;|
|CONCATENATE|&#x2713;|&#x2713;|
|DOLLAR|&#x2713;| |
|EXACT|&#x2713;| |
|FIND|&#x2713;| |
|FIXED|&#x2713;| |
|~~JIS~~| | |
|LEFT|&#x2713;|&#x2713;|
|LEN|&#x2713;|&#x2713;|
|LOWER|&#x2713;|&#x2713;|
|MID|&#x2713;|&#x2713;|
|~~PHONETIC~~| | |
|PROPER|&#x2713;|&#x2713;|
|REPLACE|&#x2713;|&#x2713;|
|REPT|&#x2713;| |
|RIGHT|&#x2713;|&#x2713;|
|SEARCH|&#x2713;|&#x2713;|
|SUBSTITUTE|&#x2713;| |
|T|&#x2713;| |
|TEXT|&#x2713;| |
|TRIM|&#x2713;|&#x2713;|
|UPPER|&#x2713;|&#x2713;|
|VALUE|&#x2713;|&#x2713;|

#### Logical

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|AND|&#x2713;|&#x2713;|
|FALSE|&#x2713;|&#x2713;|
|IF|&#x2713;|&#x2713;|
|NOT|&#x2713;|&#x2713;|
|OR|&#x2713;|&#x2713;|
|TRUE|&#x2713;|&#x2713;|

#### Information

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|CELL|&#x2713;| |
|ERROR\.TYPE|&#x2713;|&#x2713;|
|~~INFO~~| | |
|ISBLANK|&#x2713;|&#x2713;|
|ISERR|&#x2713;|&#x2713;|
|ISERROR|&#x2713;|&#x2713;|
|ISLOGICAL|&#x2713;|&#x2713;|
|ISNA|&#x2713;|&#x2713;|
|ISNONTEXT|&#x2713;|&#x2713;|
|ISNUMBER|&#x2713;|&#x2713;|
|ISREF|&#x2713;| |
|ISTEXT|&#x2713;|&#x2713;|
|N|&#x2713;| |
|NA|&#x2713;|&#x2713;|
|TYPE|&#x2713;|&#x2713;|


* **Total**: 238
* **Implemented**: 214 (90%)


### Added functions in Excel 2007

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|ACCRINT|&#x2713;| |
|ACCRINTM|&#x2713;| |
|~~AMORDEGRC~~| | |
|~~AMORLINC~~| | |
|AVERAGEIF|&#x2713;|&#x2713;|
|~~BESSELI~~| | |
|~~BESSELJ~~| | |
|~~BESSELK~~| | |
|~~BESSELY~~| | |
|BIN2DEC|&#x2713;| |
|BIN2HEX|&#x2713;| |
|BIN2OCT|&#x2713;| |
|~~COMPLEX~~| | |
|CONVERT|&#x2713;| |
|COUPDAYBS|&#x2713;| |
|COUPDAYS|&#x2713;| |
|COUPDAYSNC|&#x2713;| |
|COUPNCD|&#x2713;| |
|COUPNUM|&#x2713;| |
|COUPPCD|&#x2713;| |
|CUMIPMT|&#x2713;| |
|CUMPRINC|&#x2713;| |
|DEC2BIN|&#x2713;| |
|DEC2HEX|&#x2713;| |
|DEC2OCT|&#x2713;| |
|DELTA|&#x2713;| |
|~~DISC~~| | |
|DOLLARDE|&#x2713;| |
|DOLLARFR|&#x2713;| |
|DURATION|&#x2713;| |
|EDATE|&#x2713;| |
|EFFECT|&#x2713;| |
|EOMONTH|&#x2713;| |
|~~ERF~~| | |
|~~ERFC~~| | |
|FACTDOUBLE|&#x2713;| |
|~~FVSCHEDULE~~| | |
|GCD|&#x2713;|&#x2713;|
|GESTEP|&#x2713;| |
|HEX2BIN|&#x2713;| |
|HEX2DEC|&#x2713;| |
|HEX2OCT|&#x2713;| |
|IFERROR|&#x2713;|&#x2713;|
|~~IMABS~~| | |
|~~IMAGINARY~~| | |
|~~IMARGUMENT~~| | |
|~~IMCONJUGATE~~| | |
|~~IMCOS~~| | |
|~~IMDIV~~| | |
|~~IMEXP~~| | |
|~~IMLN~~| | |
|~~IMLOG10~~| | |
|~~IMLOG2~~| | |
|~~IMPOWER~~| | |
|~~IMPRODUCT~~| | |
|~~IMREAL~~| | |
|~~IMSIN~~| | |
|~~IMSQRT~~| | |
|~~IMSUB~~| | |
|~~IMSUM~~| | |
|~~INTRATE~~| | |
|ISEVEN|&#x2713;| |
|ISODD|&#x2713;| |
|LCM|&#x2713;|&#x2713;|
|MDURATION|&#x2713;| |
|MROUND|&#x2713;| |
|MULTINOMIAL|&#x2713;|&#x2713;|
|NETWORKDAYS|&#x2713;| |
|NOMINAL|&#x2713;| |
|OCT2BIN|&#x2713;| |
|OCT2DEC|&#x2713;| |
|OCT2HEX|&#x2713;| |
|~~ODDFPRICE~~| | |
|~~ODDFYIELD~~| | |
|~~ODDLPRICE~~| | |
|~~ODDLYIELD~~| | |
|~~PRICE~~| | |
|~~PRICEDISC~~| | |
|~~PRICEMAT~~| | |
|QUOTIENT|&#x2713;| |
|RANDBETWEEN|&#x2713;| |
|~~RECEIVED~~| | |
|SERIESSUM|&#x2713;| |
|SQRTPI|&#x2713;| |
|~~TBILLEQ~~| | |
|~~TBILLPRICE~~| | |
|~~TBILLYIELD~~| | |
|WEEKNUM|&#x2713;| |
|WORKDAY|&#x2713;| |
|XIRR|&#x2713;| |
|XNPV|&#x2713;| |
|YEARFRAC|&#x2713;| |
|~~YIELDDISC~~| | |
|~~YIELDMAT~~| | |


* **Total**: 94
* **Implemented**: 52 (55%)


### Added functions in Excel 2010

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|NETWORKDAYS\.INTL|&#x2713;| |
|WORKDAY\.INTL|&#x2713;| |
|AGGREGATE|&#x2713;| |
|CEILING\.PRECISE|&#x2713;|&#x2713;|
|ISO\.CEILING|&#x2713;|&#x2713;|
|~~CHISQ\.DIST~~| | |
|~~CHISQ\.INV~~| | |
|~~CONFIDENCE\.T~~| | |
|~~COVARIANCE\.S~~| | |
|~~ERF\.PRECISE~~| | |
|~~ERFC\.PRECISE~~| | |
|~~F\.DIST~~| | |
|~~F\.INV~~| | |
|FLOOR\.PRECISE|&#x2713;| |
|~~GAMMALN\.PRECISE~~| | |
|~~MODE\.MULT~~| | |
|PERCENTILE\.EXC|&#x2713;| |
|~~PERCENTRANK\.EXC~~| | |
|QUARTILE\.EXC|&#x2713;| |
|RANK\.AVG|&#x2713;|&#x2713;|
|~~T\.DIST~~| | |
|~~T\.INV~~| | |


* **Total**: 22
* **Implemented**: 9 (41%)


### Added functions in Excel 2013

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|DAYS|&#x2713;|&#x2713;|
|ISOWEEKNUM|&#x2713;|&#x2713;|
|BITAND|&#x2713;|&#x2713;|
|BITLSHIFT|&#x2713;|&#x2713;|
|BITOR|&#x2713;|&#x2713;|
|BITRSHIFT|&#x2713;|&#x2713;|
|BITXOR|&#x2713;|&#x2713;|
|~~IMCOSH~~| | |
|~~IMCOT~~| | |
|~~IMCSC~~| | |
|~~IMCSCH~~| | |
|~~IMSEC~~| | |
|~~IMSECH~~| | |
|~~IMSINH~~| | |
|~~IMTAN~~| | |
|PDURATION|&#x2713;|&#x2713;|
|RRI|&#x2713;|&#x2713;|
|ISFORMULA|&#x2713;|&#x2713;|
|SHEET|&#x2713;| |
|SHEETS|&#x2713;|&#x2713;|
|IFNA|&#x2713;|&#x2713;|
|XOR|&#x2713;|&#x2713;|
|FORMULATEXT|&#x2713;|&#x2713;|
|ACOT|&#x2713;|&#x2713;|
|ACOTH|&#x2713;|&#x2713;|
|ARABIC|&#x2713;|&#x2713;|
|BASE|&#x2713;|&#x2713;|
|CEILING\.MATH|&#x2713;|&#x2713;|
|COMBINA|&#x2713;|&#x2713;|
|COT|&#x2713;|&#x2713;|
|COTH|&#x2713;|&#x2713;|
|CSC|&#x2713;|&#x2713;|
|CSCH|&#x2713;|&#x2713;|
|DECIMAL|&#x2713;|&#x2713;|
|FLOOR\.MATH|&#x2713;|&#x2713;|
|ISO\.CEILING|&#x2713;|&#x2713;|
|MUNIT|&#x2713;|&#x2713;|
|SEC|&#x2713;|&#x2713;|
|SECH|&#x2713;|&#x2713;|
|~~BINOM\.DIST\.RANGE~~| | |
|~~GAMMA~~| | |
|~~GAUSS~~| | |
|PERMUTATIONA|&#x2713;|&#x2713;|
|~~PHI~~| | |
|~~SKEW\.P~~| | |
|NUMBERVALUE|&#x2713;|&#x2713;|
|UNICHAR|&#x2713;|&#x2713;|
|UNICODE|&#x2713;|&#x2713;|
|~~ENCODEURL~~| | |
|~~FILTERXML~~| | |
|~~WEBSERVICE~~| | |


* **Total**: 51
* **Implemented**: 35 (69%)


### Added functions in Excel 2016

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|~~FORECAST\.LINEAR~~| | |
|~~FORECAST\.ETS~~| | |
|~~FORECAST\.ETS\.SEASONALITY~~| | |
|~~FORECAST\.ETS\.CONFINT~~| | |
|~~FORECAST\.ETS\.STAT~~| | |
|SWITCH|&#x2713;|&#x2713;|


* **Total**: 6
* **Implemented**: 1 (17%)


### Added functions in Excel 2019

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|AVERAGEIFS|&#x2713;|&#x2713;|
|COUNTIFS|&#x2713;|&#x2713;|
|SUMIFS|&#x2713;|&#x2713;|
|TEXTJOIN|&#x2713;|&#x2713;|
|CONCAT|&#x2713;|&#x2713;|
|IFS|&#x2713;|&#x2713;|
|MINIFS|&#x2713;|&#x2713;|
|MAXIFS|&#x2713;|&#x2713;|


* **Total**: 8
* **Implemented**: 8 (100%)


### Added functions in Office 2021

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|FILTER|&#x2713;|&#x2713;|
|RANDARRAY|&#x2713;|&#x2713;|
|SEQUENCE|&#x2713;|&#x2713;|
|SORT|&#x2713;|&#x2713;|
|SORTBY|&#x2713;|&#x2713;|
|UNIQUE|&#x2713;|&#x2713;|
|XLOOKUP|&#x2713;|&#x2713;|
|XMATCH|&#x2713;|&#x2713;|
|LET|&#x2713;|&#x2713;|
|SINGLE|&#x2713;|&#x2713;|


* **Total**: 10
* **Implemented**: 10 (100%)


### Added functions in Office 365

|Name|Implemented|Array enabled|
|:---|:---:|:---:|
|ARRAYTOTEXT|&#x2713;|&#x2713;|
|VALUETOTEXT|&#x2713;|&#x2713;|
|BYCOL|&#x2713;|&#x2713;|
|BYROW|&#x2713;|&#x2713;|
|~~FIELDVALUE~~| | |
|ISOMITTED|&#x2713;|&#x2713;|
|LAMBDA|&#x2713;|&#x2713;|
|MAKEARRAY|&#x2713;|&#x2713;|
|MAP|&#x2713;|&#x2713;|
|REDUCE|&#x2713;|&#x2713;|
|SCAN|&#x2713;|&#x2713;|
|~~STOCKHISTORY~~| | |
|TEXTBEFORE|&#x2713;|&#x2713;|
|TEXTAFTER|&#x2713;|&#x2713;|
|TEXTSPLIT|&#x2713;|&#x2713;|
|VSTACK|&#x2713;|&#x2713;|
|HSTACK|&#x2713;|&#x2713;|
|TOROW|&#x2713;|&#x2713;|
|TOCOL|&#x2713;|&#x2713;|
|WRAPROWS|&#x2713;|&#x2713;|
|WRAPCOLS|&#x2713;|&#x2713;|
|TAKE|&#x2713;|&#x2713;|
|DROP|&#x2713;|&#x2713;|
|CHOOSEROWS|&#x2713;|&#x2713;|
|CHOOSECOLS|&#x2713;|&#x2713;|
|EXPAND|&#x2713;|&#x2713;|
|~~COPILOT~~| | |
|~~DETECTLANGUAGE~~| | |
|~~DROP~~| | |
|~~EXPAND~~| | |
|~~GROUPBY~~| | |
|~~IMAGE~~| | |
|~~PERCENTOF~~| | |
|~~PIVOTBY~~| | |
|~~REGEXEXTRACT~~| | |
|~~REGEXREPLACE~~| | |
|~~REGEXTEST~~| | |
|~~TRANSLATE~~| | |
|~~TRIMRANGE~~| | |


* **Total**: 39
* **Implemented**: 24 (62%)



## Renamed functions
This is a list of the functions renamed in Excel.

* **Supported** means that FlexCel understands the function and you can add it with the API.

* **Implemented for recalc** means that FlexCel knows how to calculate the function.

> [!Note]
> Normally, if a function renamed is implemented for recalc in FlexCel under the old name
> then it will also be implemented for recalc in the new name.
>
> But some renamed functions like **Norm.S.Dist** have a different list of
> parameters. Those might not be implemented for recalc.

### Renamed functions in Excel 2010

|New name|Old name|Supported|Implemented for recalc|
|:---|:---|:---:|:---:|
|~~BETA\.DIST~~|BETADIST|&#x2713;| |
|~~BETA\.INV~~|BETAINV|&#x2713;| |
|BINOM\.DIST|BINOMDIST|&#x2713;|&#x2713;|
|~~BINOM\.INV~~|CRITBINOM|&#x2713;| |
|CHISQ\.DIST\.RT|CHIDIST|&#x2713;|&#x2713;|
|CHISQ\.INV\.RT|CHIINV|&#x2713;|&#x2713;|
|CHISQ\.TEST|CHITEST|&#x2713;|&#x2713;|
|CONFIDENCE\.NORM|CONFIDENCE|&#x2713;|&#x2713;|
|COVARIANCE\.P|COVAR|&#x2713;|&#x2713;|
|EXPON\.DIST|EXPONDIST|&#x2713;|&#x2713;|
|~~F\.DIST\.RT~~|FDIST|&#x2713;| |
|~~F\.INV\.RT~~|FINV|&#x2713;| |
|~~F\.TEST~~|FTEST|&#x2713;| |
|GAMMA\.DIST|GAMMADIST|&#x2713;|&#x2713;|
|GAMMA\.INV|GAMMAINV|&#x2713;|&#x2713;|
|~~HYPGEOM\.DIST~~|HYPGEOMDIST|&#x2713;| |
|~~LOGNORM\.DIST~~|LOGNORMDIST|&#x2713;| |
|LOGNORM\.INV|LOGINV|&#x2713;|&#x2713;|
|MODE\.SNGL|MODE|&#x2713;|&#x2713;|
|~~NEGBINOM\.DIST~~|NEGBINOMDIST|&#x2713;| |
|NORM\.DIST|NORMDIST|&#x2713;|&#x2713;|
|NORM\.INV|NORMINV|&#x2713;|&#x2713;|
|~~NORM\.S\.DIST~~|NORMSDIST|&#x2713;| |
|NORM\.S\.INV|NORMSINV|&#x2713;|&#x2713;|
|PERCENTILE\.INC|PERCENTILE|&#x2713;|&#x2713;|
|PERCENTRANK\.INC|PERCENTRANK|&#x2713;|&#x2713;|
|POISSON\.DIST|POISSON|&#x2713;|&#x2713;|
|QUARTILE\.INC|QUARTILE|&#x2713;|&#x2713;|
|RANK\.EQ|RANK|&#x2713;|&#x2713;|
|STDEV\.P|STDEVP|&#x2713;|&#x2713;|
|STDEV\.S|STDEV|&#x2713;|&#x2713;|
|~~T\.DIST\.2T~~|TDIST|&#x2713;| |
|~~T\.DIST\.RT~~|TDIST|&#x2713;| |
|~~T\.INV\.2T~~|TINV|&#x2713;| |
|~~T\.TEST~~|TTEST|&#x2713;| |
|VAR\.P|VARP|&#x2713;|&#x2713;|
|VAR\.S|VAR|&#x2713;|&#x2713;|
|WEIBULL\.DIST|WEIBULL|&#x2713;|&#x2713;|
|Z\.TEST|ZTEST|&#x2713;|&#x2713;|


* **Total**: 39
* **Implemented**: 25 (64%)



