---
uid: LangWars-FireMonkey_Mobile
description: LangWars-FireMonkey_Mobile
---


# LangWars (FireMonkey Mobile)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\FireMonkey Mobile\\Modules\\80\.LangWars** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Fire&#8203;Monkey Mobile/&#8203;Modules/&#8203;80.&#8203;Lang&#8203;Wars](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/FireMonkey%20Mobile/Modules/80\.LangWars)


## Overview


This example shows how to do a simple report using FlexCel. It will fetch the most used
tags from Stack Overflow and rank and provide a chart to visualize them. You can work with
online or offline data, in case you don't have access to Stack Overflow.

In this example, we are exporting the results to an html file and showing the results in a web browser.
We could also export to pdf, as shown in the [iOS_FlexView](~/samples/firemonkey-mobile/iosflexview/index.md) demo.

## Files

### DataModel.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DataModel;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SysUtils, Generics.Defaults, Generics.Collections;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TVersion = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FCount: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Count</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCount;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aCount: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TVersionList = TObjectList&#x3C;TVersion>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TVersionComparer = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TInterfacedObject, IComparer&#x3C;TVersion>)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Compare</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Left, Right: TVersion): </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TVersion }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TVersion.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aCount: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FName := aName;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FCount := aCount;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TVersionComparer }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TVersionComparer.Compare</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Left, Right: TVersion): </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Left.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Length &#x3C; Right.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Length </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(-</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Left.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Length > Right.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Length </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Left.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.CompareTo(Right.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### MainForm.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.SysUtils, System.Types, System.UITypes, System.Classes, System.Variants,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.Types, FMX.Controls, FMX.Forms, FMX.Graphics, FMX.Dialogs, IPPeerClient,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Data.DBXJSON, System.JSON, ZLib,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DataModel, Generics.Defaults,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.FMXSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Report, FlexCel.Render, FlexCel.Pdf,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  REST.Client, Data.Bind.Components, Data.Bind.ObjectScope, FMX.StdCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.WebBrowser, FMX.FlexCel.DocExport, REST.Types, FMX.Controls.Presentation;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFMainForm = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SORESTClient: TRESTClient;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SORESTRequest: TRESTRequest;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SORESTResponse: TRESTResponse;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar1: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnRun: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Viewer: TWebBrowser;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnShare: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelDocExport: TFlexCelDocExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnOffline: TButton;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnRunClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnShareClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    PdfPath: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ResponseStr: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): TVersionList;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Versions: TVersionList): TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ExportToHtml</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ExportToPdf</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetOfflineData</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMainForm: TFMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils, System.Threading;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.fmx}</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.SmXhdpiPh.fmx ANDROID}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.LoadData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ResponseStr: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): TVersionList;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Response: TJSONValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Entries: TJSONArray;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Item: TJSONValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Count: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  VersionComparer: IComparer&#x3C;TVersion>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TVersionList.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Response := TJSONObject.ParseJSONValue(ResponseStr);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Entries := Response.GetValue&#x3C;TJsonArray>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'items'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Item </span><span style="color:#0000FF;--shiki-dark:#569CD6">in</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Entries </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := Item.GetValue&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'name'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Substring(</span><span style="color:#A31515;--shiki-dark:#CE9178">'delphi-'</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Length);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.StartsWith(</span><span style="color:#A31515;--shiki-dark:#CE9178">'XE'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">)) and </span><span style="color:#0000FF;--shiki-dark:#569CD6">not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">.StartsWith(</span><span style="color:#A31515;--shiki-dark:#CE9178">'10.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">)) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">        continue</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Count > </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> break</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Count := Item.GetValue&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'count'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TVersion.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Count));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    VersionComparer := TVersionComparer.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Sort(VersionComparer);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Free;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.GetOfflineData</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OfflineStream: TResourceStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OfflineBytes: TBytes;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OfflineStream := TResourceStream.Create(hinstance, </span><span style="color:#A31515;--shiki-dark:#CE9178">'OFFLINE_DATA'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, RT_RCDATA);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SetLength(OfflineBytes, OfflineStream.Size);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OfflineStream.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Read</span><span style="color:#000000;--shiki-dark:#D4D4D4">(OfflineBytes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">], Length(OfflineBytes));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OfflineStream.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TEncoding.UTF8.GetString(OfflineBytes);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ResponseStr: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Versions: TVersionList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Url: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> btnOffline.IsPressed </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ResponseStr := GetOfflineData;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SORESTRequest.Execute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ResponseStr := SORESTResponse.Content;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Versions := LoadData(ResponseStr);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls := CreateReport(Versions);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Url := ExportToHtml(Xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      PdfPath := ExportToPdf(Xls); </span><span style="color:#008000;--shiki-dark:#6A9955">//for sharing and printing.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Versions.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Viewer.LoadFromStrings(TFile.ReadAllText(Url), </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.btnRunClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Run;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.btnShareClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (PdfPath = </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Please run the app first'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // To send the file, we need to define a file provider in AndroidManifest.xml</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // See https://doc.tmssoftware.com/flexcel/vcl/guides/android-guide.html#sharing-files</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCelDocExport.ExportFile(btnShare, PdfPath);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.CreateReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Versions: TVersionList): TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report: TFlexCelReport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Template: TResourceStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Template := TResourceStream.Create(hinstance, </span><span style="color:#A31515;--shiki-dark:#CE9178">'REPORT_TEMPLATE'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, RT_RCDATA);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Open(Template);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report := TFlexCelReport.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.AddTable&#x3C;TVersion>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Version'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Versions, TDisposeMode.DoNotDispose);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.Run(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Free;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.ExportToHtml</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html: TFlexCelHtmlExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Meta: TArray&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html := TFlexCelHtmlExport.Create(Xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //We will use SVG, which is vectorial to export the chart, so it looks nice no matter the resolution of the phone</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.HtmlVersion := THtmlVersion.Html_5; </span><span style="color:#008000;--shiki-dark:#6A9955">//Needed to support SVG and embedded images.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.SavedImagesFormat := THtmlImageFormat.Svg;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.EmbedImages := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#008000;--shiki-dark:#6A9955">//Embedding the chart in the html avoids the issue with managing multiple files.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SetLength(Meta, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Meta[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := </span><span style="color:#A31515;--shiki-dark:#CE9178">'&#x3C;meta name="viewport" content="width=device-width" />'</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#008000;--shiki-dark:#6A9955">//To have the web page zoom to the display</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    html.ExtraInfo.Meta := Meta;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TPath.Combine(TPath.GetDocumentsPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'versions.html'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFMainForm.ExportToPdf</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf := TFlexCelPdfExport.Create(Xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.FontEmbed := TFontEmbed.None;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.FontMapping := TFontMapping.ReplaceAllFonts;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TPath.Combine(TPath.GetDocumentsPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'delphiversions.pdf'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


