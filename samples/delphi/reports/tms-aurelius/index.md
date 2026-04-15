---
uid: TMS_Aurelius-Delphi
description: TMS_Aurelius-Delphi
---


# Using FlexCel with TMS Aurelius (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\20\.Reports\\A1\.TMS Aurelius** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;20.&#8203;Reports/&#8203;A1.&#8203;TMS Aurelius](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/20\.Reports/A1\.TMS%20Aurelius)


## Overview


You can run a report in data from [TMS Aurelius](https://www.tmssoftware.com/site/aurelius.asp) the same way you would
run a report from a TList\<T\>.

## Concepts

- There is no need to use TAureliusDataSet. FlexCel can bind directly
  to the TList\<T\> managed by Aurelius.

- Aurelius has 2 specific types that must be handled differently:
  Nullable\<T\> and TBlob. In the unit AureliusFlexCelSupport, we
  add support for those types in FlexCel. To run your own reports
  with Aurelius, copy the unit \"AureliusFlexCelSupport.pas\" in
  your own app, and call SetupAurelius(Report) after creating the
  [TFlexCelReport](~/api/FlexCel.Report/TFlexCelReport/index.md) instance.

## Files

### AureliusFlexCelSupport.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> AureliusFlexCelSupport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IF CompilerVersion &#x3C; 23.0}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//Aurelius doesn't support XE</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$ELSE}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> RTTI, FlexCel.Report, Aurelius.Types.Blob, Aurelius.Mapping.RttiUtils;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SetupAurelius</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Report: TFlexCelReport);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TypInfo, StrUtils;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ConvertAureliusTypes</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> v: TFlexCelDataConversionArgs; </span><span style="color:#0000FF;--shiki-dark:#569CD6">out</span><span style="color:#000000;--shiki-dark:#D4D4D4"> r: TReportValue): </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Blob: TBlob;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  v0: TValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RttiType: TRttiType;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FieldHasValue, FieldValue: TRttiField;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  HasValue: </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  v0 := v.v;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> v0.IsEmpty </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    r := TReportValue.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Empty</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (v0.Kind &#x3C;> tkRecord) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> v0.TryAsType&#x3C;TBlob>(Blob) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    r := Blob.AsBytes;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (v0.TypeInfo = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TName := GetTypeName(v0.TypeInfo);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> StartsStr(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Nullable&#x3C;'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TName) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    RttiType := v.Rtti.GetType(v0.TypeInfo);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FieldHasValue := RttiType.GetField(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FHasValue'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FieldHasValue = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FieldValue := RttiType.GetField(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FValue'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FieldValue = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    HasValue := FieldHasValue.GetValue(v0.GetReferenceToRawData).AsBoolean;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> HasValue </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      r := TReportValue.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Empty</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    r := TReportValue.Create(FieldValue.GetValue(v0.GetReferenceToRawData).AsVariant);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SetupAurelius</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Report: TFlexCelReport);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report.DataConversionEvent :=</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      function (</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> v: TFlexCelDataConversionArgs; </span><span style="color:#0000FF;--shiki-dark:#569CD6">out</span><span style="color:#000000;--shiki-dark:#D4D4D4"> r: TReportValue): </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ConvertAureliusTypes(v, r);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### DataModel.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DataModel;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IF CompilerVersion &#x3C; 23.0}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//Aurelius doesn't support XE</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$ELSE}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SysUtils, Generics.Collections, Aurelius.Mapping.Attributes, Aurelius.Types.Blob, Aurelius.Types.DynamicProperties, Aurelius.Types.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Aurelius.Types.Proxy, Aurelius.Criteria.Dictionary;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TEmployees = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TOrders = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TShippers = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TEmployeesTableDictionary = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TOrdersTableDictionary = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TShippersTableDictionary = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Entity]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Table(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Employees'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Id(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FEmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TIdGenerator.IdentityOrSequence)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TEmployees = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'EmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.Required, TColumnProp.NoInsert, TColumnProp.NoUpdate])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FEmployeeID: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'LastName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.Required], </span><span style="color:#098658;--shiki-dark:#B5CEA8">20</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FLastName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FirstName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.Required], </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FFirstName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Title'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">30</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FTitle: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'TitleOfCourtesy'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">25</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FTitleOfCourtesy: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'BirthDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FBirthDate: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'HireDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FHireDate: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Address'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">60</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FAddress: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'City'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FCity: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Region'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FRegion: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'PostalCode'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPostalCode: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Country'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FCountry: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'HomePhone'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">24</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FHomePhone: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Extension'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FExtension: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Photo'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Lazy</span><span style="color:#000000;--shiki-dark:#D4D4D4">])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPhoto: TBlob;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Notes'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Lazy</span><span style="color:#000000;--shiki-dark:#D4D4D4">])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FNotes: TBlob;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'PhotoPath'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">255</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPhotoPath: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Association([TAssociationProp.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Lazy</span><span style="color:#000000;--shiki-dark:#D4D4D4">], [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [JoinColumn(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ReportsTo'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#A31515;--shiki-dark:#CE9178">'EmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FReportsTo: Proxy&#x3C;TEmployees>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetReportsTo</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TEmployees;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SetReportsTo</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TEmployees);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> EmployeeID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployeeID </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployeeID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LastName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FLastName </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FLastName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FirstName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FFirstName </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FFirstName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FTitle </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FTitle;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TitleOfCourtesy</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FTitleOfCourtesy </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FTitleOfCourtesy;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> BirthDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FBirthDate </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FBirthDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> HireDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FHireDate </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FHireDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Address</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FAddress </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FAddress;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> City</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCity </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCity;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Region</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FRegion </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FRegion;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> PostalCode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPostalCode </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPostalCode;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Country</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCountry </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCountry;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> HomePhone</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FHomePhone </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FHomePhone;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Extension</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FExtension </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FExtension;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Photo</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TBlob </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhoto </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhoto;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Notes</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TBlob </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FNotes </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FNotes;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> PhotoPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhotoPath </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhotoPath;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ReportsTo</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TEmployees </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> GetReportsTo </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SetReportsTo;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Entity]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Table(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Orders'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Id(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FOrderID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TIdGenerator.IdentityOrSequence)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TOrders = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'OrderID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.Required, TColumnProp.NoInsert, TColumnProp.NoUpdate])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FOrderID: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'OrderDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FOrderDate: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'RequiredDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FRequiredDate: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShippedDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShippedDate: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Freight'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FFreight: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">40</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipAddress'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">60</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipAddress: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipCity'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipCity: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipRegion'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipRegion: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipPostalCode'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipPostalCode: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipCountry'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipCountry: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'EmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FEmployeeID: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Association([TAssociationProp.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Lazy</span><span style="color:#000000;--shiki-dark:#D4D4D4">], [])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [JoinColumn(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipVia'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipperID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipVia: Proxy&#x3C;TShippers>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetShipVia</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TShippers;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SetShipVia</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TShippers);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OrderID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrderID </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrderID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OrderDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrderDate </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrderDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> RequiredDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FRequiredDate </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FRequiredDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShippedDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;TDateTime> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShippedDate </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShippedDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Freight</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FFreight </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FFreight;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipName </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipAddress</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipAddress </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipAddress;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipCity</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipCity </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipCity;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipRegion</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipRegion </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipRegion;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipPostalCode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipPostalCode </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipPostalCode;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipCountry</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipCountry </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipCountry;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> EmployeeID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployeeID </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployeeID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipVia</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TShippers </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> GetShipVia </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SetShipVia;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Entity]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Table(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Shippers'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  [Id(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FShipperID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TIdGenerator.IdentityOrSequence)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TShippers = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipperID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.Required, TColumnProp.NoInsert, TColumnProp.NoUpdate])]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipperID: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'CompanyName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TColumnProp.Required], </span><span style="color:#098658;--shiki-dark:#B5CEA8">40</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FCompanyName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    [Column(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Phone'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">24</span><span style="color:#000000;--shiki-dark:#D4D4D4">)]</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPhone: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipperID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipperID </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipperID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CompanyName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCompanyName </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCompanyName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Phone</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Nullable</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">> </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhone </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhone;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TDicDictionary = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FEmployees: TEmployeesTableDictionary;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FOrders: TOrdersTableDictionary;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShippers: TShippersTableDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetEmployees</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TEmployeesTableDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetOrders</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TOrdersTableDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetShippers</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TShippersTableDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Employees</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TEmployeesTableDictionary </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> GetEmployees;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Orders</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TOrdersTableDictionary </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> GetOrders;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Shippers</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TShippersTableDictionary </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> GetShippers;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TEmployeesTableDictionary = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FEmployeeID: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FLastName: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FFirstName: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FTitle: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FTitleOfCourtesy: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FBirthDate: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FHireDate: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FAddress: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FCity: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FRegion: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPostalCode: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FCountry: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FHomePhone: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FExtension: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPhoto: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FNotes: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPhotoPath: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FReportsTo: TDictionaryAssociation;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> EmployeeID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployeeID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LastName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FLastName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FirstName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FFirstName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Title</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FTitle;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TitleOfCourtesy</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FTitleOfCourtesy;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> BirthDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FBirthDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> HireDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FHireDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Address</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FAddress;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> City</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCity;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Region</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FRegion;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> PostalCode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPostalCode;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Country</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCountry;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> HomePhone</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FHomePhone;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Extension</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FExtension;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Photo</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhoto;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Notes</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FNotes;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> PhotoPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhotoPath;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ReportsTo</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAssociation </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FReportsTo;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TOrdersTableDictionary = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FOrderID: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FOrderDate: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FRequiredDate: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShippedDate: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FFreight: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipName: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipAddress: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipCity: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipRegion: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipPostalCode: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipCountry: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FEmployeeID: TDictionaryAssociation;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipVia: TDictionaryAssociation;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OrderID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrderID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OrderDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrderDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> RequiredDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FRequiredDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShippedDate</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShippedDate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Freight</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FFreight;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipAddress</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipAddress;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipCity</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipCity;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipRegion</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipRegion;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipPostalCode</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipPostalCode;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipCountry</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipCountry;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> EmployeeID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAssociation </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployeeID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipVia</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAssociation </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipVia;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TShippersTableDictionary = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FShipperID: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FCompanyName: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FPhone: TDictionaryAttribute;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShipperID</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShipperID;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CompanyName</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FCompanyName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Phone</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDictionaryAttribute </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FPhone;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Dic</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDicDictionary;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __Dic: TDicDictionary;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Dic</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDicDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> __Dic = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> __Dic := TDicDictionary.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := __Dic</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TEmployees}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TEmployees.GetReportsTo</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TEmployees;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := FReportsTo.Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TEmployees.SetReportsTo</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TEmployees);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FReportsTo.Value := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TOrders}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TOrders.GetShipVia</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TShippers;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := FShipVia.Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TOrders.SetShipVia</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TShippers);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipVia.Value := Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TDicDictionary}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TDicDictionary.Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployees &#x3C;> </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployees.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrders &#x3C;> </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrders.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShippers &#x3C;> </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShippers.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TDicDictionary.GetEmployees</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TEmployeesTableDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployees = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FEmployees := TEmployeesTableDictionary.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := FEmployees;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TDicDictionary.GetOrders</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TOrdersTableDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrders = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FOrders := TOrdersTableDictionary.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := FOrders;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TDicDictionary.GetShippers</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TShippersTableDictionary;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShippers = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FShippers := TShippersTableDictionary.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := FShippers;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TEmployeesTableDictionary}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TEmployeesTableDictionary.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FEmployeeID := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'EmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FLastName := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'LastName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FFirstName := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FirstName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FTitle := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Title'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FTitleOfCourtesy := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'TitleOfCourtesy'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FBirthDate := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'BirthDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FHireDate := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'HireDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FAddress := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Address'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FCity := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'City'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FRegion := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Region'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FPostalCode := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'PostalCode'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FCountry := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Country'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FHomePhone := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'HomePhone'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FExtension := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Extension'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FPhoto := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Photo'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FNotes := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Notes'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FPhotoPath := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'PhotoPath'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FReportsTo := TDictionaryAssociation.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ReportsTo'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TOrdersTableDictionary}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TOrdersTableDictionary.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FOrderID := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'OrderID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FOrderDate := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'OrderDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FRequiredDate := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'RequiredDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShippedDate := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShippedDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FFreight := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Freight'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipName := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipAddress := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipAddress'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipCity := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipCity'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipRegion := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipRegion'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipPostalCode := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipPostalCode'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipCountry := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipCountry'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FEmployeeID := TDictionaryAssociation.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'EmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipVia := TDictionaryAssociation.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipVia'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TShippersTableDictionary}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TShippersTableDictionary.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FShipperID := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ShipperID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FCompanyName := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'CompanyName'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FPhone := TDictionaryAttribute.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Phone'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">initialization</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">finalization</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> __Dic &#x3C;> </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> __Dic.Free</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### Queries.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Queries;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IF CompilerVersion &#x3C; 23.0}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//Aurelius doesn't support XE</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$ELSE}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Generics.Collections, DataModel,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     Aurelius.Drivers.Interfaces, Aurelius.Drivers.dbGo,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     Aurelius.Sql.MSSQL,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     Aurelius.Engine.ObjectManager,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     ADODb,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     Aurelius.Criteria.Base, Aurelius.Criteria.Linq;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TAureliusQuery = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ADOConnection: TADOConnection;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Connection: IDBConnection;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Manager: TObjectManager;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FEmployees: TObjectList&#x3C;TEmployees>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FOrders: TObjectList&#x3C;TOrders>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DBFile: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetEmployees</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TList&#x3C;TEmployees>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetOrders</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TList&#x3C;TOrders>;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SysUtils;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> BAseConnectionString = </span><span style="color:#A31515;--shiki-dark:#CE9178">'Provider=Microsoft.Jet.OLEDB.4.0;Data Source=Northwind.mdb;Persist Security Info=False;'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TAureliusQuery.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DBFile: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ADOConnection := TADOConnection.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ADOConnection.ConnectionString := StringReplace(BaseConnectionString, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Northwind.mdb'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, DbFile, []);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Connection := TDbGoConnectionAdapter.Create(ADOConnection, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Manager := TObjectManager.Create(Connection);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TAureliusQuery.Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FOrders.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FEmployees.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Manager.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Connection := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ADOConnection.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TAureliusQuery.GetEmployees</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TList&#x3C;TEmployees>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FEmployees.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FEmployees := Manager.Find&#x3C;TEmployees></span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            .List;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := FEmployees;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TAureliusQuery.GetOrders</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TList&#x3C;TOrders>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FOrders.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FOrders := Manager.Find&#x3C;TOrders></span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            .List;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := FOrders;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
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
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellApi,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, StdCtrls, ExtCtrls;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TMainForm = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCancel: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnExportHTML: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialogXls: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label1: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnExportPdf: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnExportExcel: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialogPdf: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialogHtml: TSaveDialog;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnExportHTMLClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnExportExcelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnExportPdfClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog: TSaveDialog): </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShowOpenResult</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog: TSaveDialog);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MainForm: TMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils, DataModel, Queries, AureliusFlexCelSupport;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> DBFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TPath.Combine(TPath.GetDirectoryName(ParamStr(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">)), </span><span style="color:#A31515;--shiki-dark:#CE9178">'..\..\..\SharedData\Northwind.mdb'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnExportExcelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);  </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> RunReport(Xls, SaveDialogXls) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.Save(SaveDialogXls.FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowOpenResult(SaveDialogXls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnExportHTMLClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html: TFlexCelHtmlExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> RunReport(Xls, SaveDialogHtml) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html := TFlexCelHtmlExport.Create(Xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.HtmlVersion := THtmlVersion.Html_5;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.EmbedImages := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialogHtml.FileName, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ShowOpenResult(SaveDialogHtml);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnExportPdfClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> RunReport(Xls, SaveDialogPdf) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf := TFlexCelPdfExport.Create(Xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialogPdf.FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ShowOpenResult(SaveDialogPdf);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TPath.Combine(TPath.GetDirectoryName(ParamStr(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">)), </span><span style="color:#A31515;--shiki-dark:#CE9178">'..\..'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IF CompilerVersion &#x3C; 23.0}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//Aurelius doesn't support XE</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog: TSaveDialog): </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Aurelius doesn''t support Delphi XE. To run this demo you need XE2 or newer'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$ELSE}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog: TSaveDialog): </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report: TFlexCelReport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Query: TAureliusQuery;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report := TFlexCelReport.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SetupAurelius(Report);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Query := TAureliusQuery.Create(DBFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Report.AddTable&#x3C;TEmployees>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Employees'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Query.GetEmployees, TDisposeMode.DoNotDispose);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Report.AddTable&#x3C;TOrders>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Orders'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Query.GetOrders, TDisposeMode.DoNotDispose);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //Note that we've defined EmployeeID as an integer and not a TProxy, to avoid loading</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //the full employee for every order. If we had left EmployeeID as a proxy we would have</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //to define:</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //Report.AddRelationship('Employees', 'Orders', 'EmployeeID', 'EmployeeID.EmployeeID');</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //It would work, but it would be slower.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Report.AddRelationship(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Employees'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Orders'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'EmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'EmployeeID'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Report.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Date'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Now);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.Open(TPath.Combine(GetDataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'TMS Aurelius.template.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Report.Run(Xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Query.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.ShowOpenResult</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog: TSaveDialog);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


