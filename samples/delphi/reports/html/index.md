---
uid: HTML-Delphi
description: HTML-Delphi
---


# HTML (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\20\.Reports\\83\.HTML** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;20.&#8203;Reports/&#8203;83.&#8203;HTML](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/20\.Reports/83\.HTML)


## Overview


A demo that shows how to use HTML formatted strings directly on FlexCel.
On this example we used to connect to **Yahoo Travel** web service, and
format the results into an Excel or pdf sheet. As Yahoo Travel doesn't exist anymore, 
some sample data is included to work offline without connecting.

## Concepts

- FlexCel supports a light subset of HTML commands, like *\<b\>,
  \<br\>,* and the escaped characters like *&amp;*. But this should
  be enough to for having rich format inside cells.

- Any HTML tag that FlexCel cannot parse will be ignored.

- Note how the word \"London\" is in bold in titles like \"**London**
  and Paris\". This is because the HTML returned contained
  those tags.

- You can allow HTML in a [TFlexCelReport](~/api/FlexCel.Report/TFlexCelReport/index.md) in two ways:

   1. You can enable it globally by setting [TFlexCelReport.HTMLMode](~/api/FlexCel.Report/TFlexCelReport/HTMLMode.md) =
   true, and disable it where not needed with the \<\#[HTML](~/guides/reports-tag-reference.md#html)(false)\>
   tag. This is not normally recommended, since when in HTML mode all
   strings have to be html strings, where for example two spaces mean
   only one, and carriage returns are created with \<br\> tags.

   2. You can enable it on a cell by cell basis, by using the
   \<\#[HTML](~/guides/reports-tag-reference.md#html)(true)\> tag. This is the approach we use here.

- How to set [Intelligent Page Breaks](~/guides/reports-designer-guide.md#intelligent-page-breaks). FlexCel will add page breaks so
  all entries are kept together when printing or exporting to pdf.

- You can also set an hyperlink in an image. In this case, we wrote an
  hyperlink in the image pointing to the URL in the database. This
  link is also exported to pdf.

## Files

### DataModel.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DataModel;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SysUtils, Generics. Collections;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TTravelItem = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FTitle: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FSummary: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FUrl: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FImageData: TBytes;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aTitle: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aSummary: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aUrl: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aImageData: TBytes);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FTitle;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FSummary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FUrl;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TBytes </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FImageData;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TTravelItemList = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (TObjectList&#x3C;TTravelItem>)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TTravelItem }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TTravelItem.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aTitle, aSummary, aUrl: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aImageData: TBytes);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FTitle := aTitle;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FSummary := aSummary;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FUrl := aUrl;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FImageData := aImageData;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### TripSearchResponse.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{***********************************************************************************************************************}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{                                                                                                                       }</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{                                                   XML Data Binding                                                    }</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{                                                                                                                       }</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{         Generated on: 27/09/2014 17:55:45                                                                             }</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{       Generated from: \Modules\20.Reports\83.HTML\OfflineData\OfflineData.xml   }</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{                                                                                                                       }</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{***********************************************************************************************************************}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TripSearchResponse;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xmldom, XMLDoc, XMLIntf;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ Forward Decls }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLNewDataSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLResultSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLResultType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLImageType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLGeocodeType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ IXMLNewDataSetType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLNewDataSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">(IXMLNode)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [</span><span style="color:#A31515;--shiki-dark:#CE9178">'{A20F7A18-B05F-4A11-89BB-0F3C2EE023ED}'</span><span style="color:#000000;--shiki-dark:#D4D4D4">]</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Property Accessors }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Xmlns</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_ResultSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLResultSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Xmlns</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Methods &#x26; Properties }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Xmlns</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Xmlns </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Xmlns;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ResultSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLResultSetType </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_ResultSet;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ IXMLResultSetType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLResultSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">(IXMLNodeCollection)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [</span><span style="color:#A31515;--shiki-dark:#CE9178">'{C75C878E-C014-44DD-9DAC-DDD082484592}'</span><span style="color:#000000;--shiki-dark:#D4D4D4">]</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Property Accessors }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_TotalResultsAvailable</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_TotalResultsReturned</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_FirstResultPosition</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_TotalResultsAvailable</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_TotalResultsReturned</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_FirstResultPosition</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Methods &#x26; Properties }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Insert</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#0000FF;--shiki-dark:#569CD6"> Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TotalResultsAvailable</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_TotalResultsAvailable </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_TotalResultsAvailable;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TotalResultsReturned</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_TotalResultsReturned </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_TotalResultsReturned;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FirstResultPosition</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_FirstResultPosition </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_FirstResultPosition;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">[</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">]: IXMLResultType </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Result; </span><span style="color:#0000FF;--shiki-dark:#569CD6">default</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ IXMLResultType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLResultType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">(IXMLNode)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [</span><span style="color:#A31515;--shiki-dark:#CE9178">'{FFF9EAEE-9172-41B2-88F7-BBABFF59856B}'</span><span style="color:#000000;--shiki-dark:#D4D4D4">]</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Property Accessors }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Id</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Destinations</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_CreateDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Duration</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Image</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLImageType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Geocode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLGeocodeType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Id</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Destinations</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_CreateDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Duration</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Methods &#x26; Properties }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Id</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Id </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Id;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Title </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Title;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Summary </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Summary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Destinations</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Destinations </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Destinations;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_CreateDate </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_CreateDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Duration</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Duration </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Duration;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Url </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Url;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_ImageData </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_ImageData;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Image</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLImageType </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Image;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Geocode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLGeocodeType </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Geocode;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ IXMLImageType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLImageType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">(IXMLNode)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [</span><span style="color:#A31515;--shiki-dark:#CE9178">'{1E1E3824-927A-4F1D-93BC-899E4014624A}'</span><span style="color:#000000;--shiki-dark:#D4D4D4">]</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Property Accessors }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Height</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Width</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Height</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Width</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Methods &#x26; Properties }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Url </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Url;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Height</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Height </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Height;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Width</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Width </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Width;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ IXMLGeocodeType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IXMLGeocodeType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span><span style="color:#000000;--shiki-dark:#D4D4D4">(IXMLNode)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [</span><span style="color:#A31515;--shiki-dark:#CE9178">'{718AD5DF-D0F0-4793-B836-F5ECABE3FB61}'</span><span style="color:#000000;--shiki-dark:#D4D4D4">]</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Property Accessors }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Longitude</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Longitude</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Methods &#x26; Properties }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Longitude</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Get_Longitude </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Set_Longitude;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ Forward Decls }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLNewDataSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLResultSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLResultType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLImageType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLGeocodeType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLNewDataSetType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLNewDataSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TXMLNode, IXMLNewDataSetType)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  protected</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { IXMLNewDataSetType }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Xmlns</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_ResultSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLResultSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Xmlns</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AfterConstruction</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLResultSetType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLResultSetType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TXMLNodeCollection, IXMLResultSetType)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  protected</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { IXMLResultSetType }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_TotalResultsAvailable</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_TotalResultsReturned</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_FirstResultPosition</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_TotalResultsAvailable</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_TotalResultsReturned</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_FirstResultPosition</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Insert</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#0000FF;--shiki-dark:#569CD6"> Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AfterConstruction</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLResultType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLResultType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TXMLNode, IXMLResultType)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  protected</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { IXMLResultType }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Id</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Destinations</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_CreateDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Duration</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Image</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLImageType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Geocode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLGeocodeType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Id</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Destinations</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_CreateDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Duration</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AfterConstruction</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLImageType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLImageType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TXMLNode, IXMLImageType)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  protected</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { IXMLImageType }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Height</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Width</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Height</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Width</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLGeocodeType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TXMLGeocodeType = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TXMLNode, IXMLGeocodeType)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  protected</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { IXMLGeocodeType }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Get_Longitude</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Set_Longitude</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ Global Functions }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetNewDataSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Doc: IXMLDocument): IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadNewDataSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> NewNewDataSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLNewDataSetType;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TargetNamespace = </span><span style="color:#A31515;--shiki-dark:#CE9178">'urn:yahoo:travel'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ Global Functions }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetNewDataSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Doc: IXMLDocument): IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := Doc.GetDocBinding(</span><span style="color:#A31515;--shiki-dark:#CE9178">'NewDataSet'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXMLNewDataSetType, TargetNamespace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadNewDataSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := LoadXMLDocument(FileName).GetDocBinding(</span><span style="color:#A31515;--shiki-dark:#CE9178">'NewDataSet'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXMLNewDataSetType, TargetNamespace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> NewNewDataSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := NewXMLDocument.GetDocBinding(</span><span style="color:#A31515;--shiki-dark:#CE9178">'NewDataSet'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXMLNewDataSetType, TargetNamespace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLNewDataSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLNewDataSetType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLNewDataSetType.AfterConstruction</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterChildNode(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ResultSet'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXMLResultSetType);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLNewDataSetType.Get_Xmlns</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := AttributeNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'xmlns'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLNewDataSetType.Set_Xmlns</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetAttribute(</span><span style="color:#A31515;--shiki-dark:#CE9178">'xmlns'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Value);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLNewDataSetType.Get_ResultSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLResultSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'ResultSet'</span><span style="color:#000000;--shiki-dark:#D4D4D4">] </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLResultSetType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLResultSetType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.AfterConstruction</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterChildNode(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Result'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXMLResultType);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ItemTag := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Result'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ItemInterface := IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Get_TotalResultsAvailable</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := AttributeNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'totalResultsAvailable'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Set_TotalResultsAvailable</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetAttribute(</span><span style="color:#A31515;--shiki-dark:#CE9178">'totalResultsAvailable'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Value);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Get_TotalResultsReturned</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := AttributeNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'totalResultsReturned'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Set_TotalResultsReturned</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetAttribute(</span><span style="color:#A31515;--shiki-dark:#CE9178">'totalResultsReturned'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Value);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Get_FirstResultPosition</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := AttributeNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'firstResultPosition'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Set_FirstResultPosition</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetAttribute(</span><span style="color:#A31515;--shiki-dark:#CE9178">'firstResultPosition'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Value);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Get_Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := List[</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">] </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := AddItem(-</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultSetType.Insert</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#0000FF;--shiki-dark:#569CD6"> Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">): IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := AddItem(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLResultType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLResultType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.AfterConstruction</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterChildNode(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Image'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXMLImageType);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterChildNode(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Geocode'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXMLGeocodeType);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Id</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := AttributeNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'id'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_Id</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetAttribute(</span><span style="color:#A31515;--shiki-dark:#CE9178">'id'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Value);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Title'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Title'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Summary'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_Summary</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Summary'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Destinations</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Destinations'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_Destinations</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Destinations'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_CreateDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'CreateDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_CreateDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'CreateDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Duration</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Duration'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_Duration</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Duration'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Url'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Url'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'ImageData'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Set_ImageData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'ImageData'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Image</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLImageType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Image'</span><span style="color:#000000;--shiki-dark:#D4D4D4">] </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLImageType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLResultType.Get_Geocode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: IXMLGeocodeType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Geocode'</span><span style="color:#000000;--shiki-dark:#D4D4D4">] </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IXMLGeocodeType;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLImageType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLImageType.Get_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Url'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLImageType.Set_Url</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Url'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLImageType.Get_Height</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Height'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLImageType.Set_Height</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Height'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLImageType.Get_Width</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Width'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLImageType.Set_Width</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Width'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TXMLGeocodeType }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLGeocodeType.Get_Longitude</span><span style="color:#000000;--shiki-dark:#D4D4D4">: UnicodeString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Longitude'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXMLGeocodeType.Set_Longitude</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Value: UnicodeString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChildNodes[</span><span style="color:#A31515;--shiki-dark:#CE9178">'Longitude'</span><span style="color:#000000;--shiki-dark:#D4D4D4">].NodeValue := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span></code></pre>


### UMainForm.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Report, FlexCel.Render,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellApi, DataModel,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, StdCtrls, ExtCtrls;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TMainForm = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCancel: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label1: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialogPdf: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialogExcel: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnExportExcel: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnExportPdf: TButton;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnExportExcelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnExportPdfClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog: TSaveDialog; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ToPdf: </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TravelItems: TTravelItemList);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetOfflineDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetImage</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): TBytes;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MainForm: TMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> XMLDoc, XMLIntf, IOUtils, DemoData, TripSearchResponse;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnExportExcelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RunReport(SaveDialogExcel, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnExportPdfClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RunReport(SaveDialogPdf, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TPath.Combine(TPath.GetDirectoryName(ParamStr(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">)), </span><span style="color:#A31515;--shiki-dark:#CE9178">'..\..'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.GetOfflineDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TPath.Combine(GetDataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'OfflineData'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.GetImage</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): TBytes;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DiskFileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fs: TFileStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DiskFileName := TPath.Combine(GetOfflineDataPath, TPath.GetFileName(FileName));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fs := TFileStream.Create(DiskFileName, fmOpenRead);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SetLength(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">, fs.Size);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (Length(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">) > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> fs.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Read</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">], Length(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fs.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.LoadData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TravelItems: TTravelItemList);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ResultSet: IXmlResultSetType;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ResultSet := LoadNewDataSet(TPath.Combine(GetOfflineDataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'OfflineData.xml'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)).ResultSet;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ResultSet.Count - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TravelItems.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TTravelItem.Create(ResultSet[i].Title, ResultSet[i].Summary, ResultSet[i].Url, GetImage(ResultSet[i].Image.Url)))</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog: TSaveDialog; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ToPdf: </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report: TFlexCelReport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TravelItems: TTravelItemList;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report := TFlexCelReport.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Date'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Now);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TravelItems := TTravelItemList.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      LoadData(TravelItems);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Report.AddTable&#x3C;TTravelItem>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Result'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TravelItems, TDisposeMode.DoNotDispose);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (ToPdf) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Xls := TXlsFile.Create(TPath.Combine(GetDataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'HTML.template.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          Report.Run(Xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          Pdf := TFlexCelPdfExport.Create(Xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            Pdf.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            Pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          Xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Report.Run(TPath.Combine(GetDataPath , </span><span style="color:#A31515;--shiki-dark:#CE9178">'HTML.template'</span><span style="color:#000000;--shiki-dark:#D4D4D4">) + TPath.GetExtension(SaveDialog.FileName), SaveDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      TravelItems.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


