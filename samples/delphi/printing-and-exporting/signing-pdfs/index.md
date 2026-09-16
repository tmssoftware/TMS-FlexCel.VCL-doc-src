---
uid: Signing_Pdfs-Delphi
description: Signing_Pdfs-Delphi
---


# Signing PDFs (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\25\.Printing and Exporting\\35\.Signing Pdfs** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;25.&#8203;Printing and Exporting/35.Signing Pdfs](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/25\.Printing%20and%20Exporting/35\.Signing%20Pdfs)


## Overview


In this example we will show how to add a visible or invisible signature
to a generated PDF file.

## Concepts

- FlexCel supports adbe.pkcs7.detached (the original Adobe format), PAdES baseline level B-B, and PAdES baseline level B-T.
  Being older, adbe.pkcs7.detached is the most extended and compatible, but PAdES is the standard required by the European Union to sign. 
  It probably makes sense to sign your PDFs with PAdES.

- In order to sign a PDF file you will need a certificate issued by a
  valid Certificate Authority, or one issued by yourself. In this
  example we will use a self signed certificate. **This certificate
  will not validate by default when you open it in Acrobat, you need
  to add it to your trusted list.**


- As SHA-1 is deprecated, FlexCel will default to using SHA512 
  for the signature. You could use a different algorithm by 
  providing an OID in the EncryptionFactory.GetSigner call.

- In order to sign a file, FlexCel **will write a requirement for
  Acrobat 8 or newer in the generated files. This is because only
  Acrobat 8 or newer support SHA512.** Older versions of acrobat
  will still display the pages but will not validate the signature.


- FlexCel currently only has support for signing in Windows, 
  using CryptoAPI. You can still create your own signature 
  engine for other platforms by using a third party cryptography
  library or by calling the native crypto functions in that platform, 
  the same way we call CryptoAPI. This is explained in the section
  [Signing PDF Files](~/guides/pdf-exporting-guide.md#signing-pdf-files) in the 
  PDF exporting guide.

- By design, FlexCel never connects to the internet. 
  So if you want to create a PAdES B-T signature, which includes a timestamp from a TSA server, you need to provide the code to actually connect the server in an anonymous method. 
  This demo shows how to do it. 

## Files

### USigningPdfs.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> USigningPdfs;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  StdCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pngimage, ExtCtrls, ExtDlgs,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render, FlexCel.Pdf;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$SCOPEDENUMS ON}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  /// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  /// The entries of the "Signature type" combo box, in the same order as they are added in the form.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  /// &#x3C;/summary></span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TSignatureType = (</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// "/adbe.pkcs7.detached": the original Adobe format. It is the most compatible, but it is not a CAdES</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// signature, so it doesn't conform to the PAdES standard the European Union requires.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// &#x3C;/summary></span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pkcs7,</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// "/ETSI.CAdES.detached" without a timestamp: PAdES baseline level B-B.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// &#x3C;/summary></span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    PAdES_B_B,</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// PAdES baseline level B-T: a B-B signature plus a timestamp from a Time Stamping Authority, which proves</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// the document was signed before a given date instead of trusting the clock of whoever signed.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    /// &#x3C;/summary></span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    PAdES_B_T);</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$SCOPEDENUMS OFF}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFSigningPdfs = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCreateAndSignPdf: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    lblSignatureType: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbSignatureType: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbCertify: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbVisibleSignature: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SignaturePicture: TImage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OpenPictureDialog: TOpenPictureDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OpenExcelDialog: TOpenDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SavePdfDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbVisibleSignatureClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SignaturePictureClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCreateAndSignPdfClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    DataPath: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ImgData: ByteArray;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadImage</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateSignerFactory</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Signer: TCmsSigner): TPdfSignerFactory;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FSigningPdfs: TFSigningPdfs;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils, UFlexCelHDPI, ShellAPI, IdHTTP;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //The Time Stamping Authority we ask for the timestamps. Replace it with the one you use: the public ones are</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //rate-limited, and a timestamp is only as trustworthy as the TSA that created it.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TsaUrl = </span><span style="color:#A31515;--shiki-dark:#CE9178">'http://timestamp.digicert.com'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;b>FlexCel never connects to the internet by itself.&#x3C;/b> It creates the RFC 3161 request and reads the answer,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// but the connection to the TSA is this function, which you write. That way you know that no part of FlexCel can</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// reach the network unless you let it.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;/summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;remarks></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// We use Indy here because it is available in every Delphi version this demo compiles in. From XE8</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// (CompilerVersion 29) on you can use THTTPClient from the RTL instead: there is a version of this same function</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// written with it right below.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;br />&#x3C;b>About https:&#x3C;/b> the url above is plain http, which is what most TSAs publish, and it is safe because</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// the answer is signed by the TSA and FlexCel verifies it. If the TSA you use is https, THTTPClient talks to it</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// with nothing extra to deploy, as on Windows it goes through the system http stack. TIdHTTP instead needs the</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// OpenSSL dlls beside the exe, and an ssl handler:</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;code></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// uses IdSSLOpenSSL;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// ...</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// SslHandler := TIdSSLIOHandlerSocketOpenSSL.Create(Http);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// SslHandler.SSLOptions.SSLVersions := [sslvTLSv1_2]; //older Indy defaults to versions no server accepts today</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// Http.IOHandler := SslHandler;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;/code></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;/remarks></span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetTimestamp</span><span style="color:#000000;--shiki-dark:#D4D4D4">(timeStampRequest: ByteArray): ByteArray;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Http: TIdHTTP;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Request, Response: TMemoryStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Http := TIdHTTP.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Http.Request.ContentType := </span><span style="color:#A31515;--shiki-dark:#CE9178">'application/timestamp-query'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Request := TMemoryStream.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Response := TMemoryStream.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Request.WriteBuffer(timeStampRequest[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">], Length(timeStampRequest));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Request.Position := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //This demo signs when you click a button, so we just wait for the answer here. In a server you would</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //normally make the whole export async instead of blocking a thread on the TSA.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Http.Post(TsaUrl, Request, Response);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        SetLength(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Response.Size);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Response.Position := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Length(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">) > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Response.ReadBuffer(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">], Length(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Response.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Request.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Http.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">(*</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  The same function written with THTTPClient, which is in the RTL from XE8 (CompilerVersion 29) on. Add</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  System.Net.HttpClient and System.Net.URLClient to the uses clause to use it. Note that, unlike TIdHTTP, it does</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  not raise an exception when the server answers an error, so we have to look at the status code ourselves.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">function GetTimestamp(timeStampRequest: ByteArray): ByteArray;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">var</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  Http: THTTPClient;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  Request, Response: TMemoryStream;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  HttpResponse: IHTTPResponse;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  Http := THTTPClient.Create;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    Request := TMemoryStream.Create;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      Response := TMemoryStream.Create;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        Request.WriteBuffer(timeStampRequest[0], Length(timeStampRequest));</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        Request.Position := 0;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        HttpResponse := Http.Post(TsaUrl, Request, Response,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">                          [TNameValuePair.Create('Content-Type', 'application/timestamp-query')]);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        if HttpResponse.StatusCode &#x3C;> 200 then</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">          raise Exception.Create('The Time Stamping Authority answered ' + IntToStr(HttpResponse.StatusCode)</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">             + ' ' + HttpResponse.StatusText);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        Result := nil;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        SetLength(Result, Response.Size);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        Response.Position := 0;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        if Length(Result) > 0 then Response.ReadBuffer(Result[0], Length(Result));</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      finally</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        Response.Free;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      end;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    finally</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      Request.Free;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    end;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  finally</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    Http.Free;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  end;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">end;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">*)</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// Creates the factory that will sign the document in the format selected in the combo box.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;/summary></span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFSigningPdfs.CreateSignerFactory</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Signer: TCmsSigner): TPdfSignerFactory;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TSignatureType(cbSignatureType.ItemIndex) </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TSignatureType.PAdES_B_B:</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //Besides writing "/ETSI.CAdES.detached" in the pdf, this adds the ESS signing-certificate-v2 signed</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //attribute that CAdES needs, so the signature says which certificate created it.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TBuiltInSignerFactory.Create(Signer, TPdfSignatureSubFilter.EtsiCAdESDetached);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TSignatureType.PAdES_B_T:</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //FlexCel has to reserve the space for the signature before it knows how big the timestamp will be, so it</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //asks the TSA for one sample token the first time. Passing the url as the cache key means the size is</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //measured once for the whole application and shared by every factory using this TSA, which matters because</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //TSAs tend to rate-limit. If you already know the size, set TokenSizeHint instead and FlexCel will not ask</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //for the sample at all.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TBuiltInSignerFactory.Create(Signer, TPdfSignatureSubFilter.EtsiCAdESDetached,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                   TPdfTimestampSettings_Create(GetTimestamp, TsaUrl));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TBuiltInSignerFactory.Create(Signer, TPdfSignatureSubFilter.AdbePkcs7Detached);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFSigningPdfs.LoadImage</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ImgData := TFile.ReadAllBytes(FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SignaturePicture.Picture.LoadFromFile(FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFSigningPdfs.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DataPath := TPath.Combine(TPath.GetDirectoryName(ParamStr(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">)), </span><span style="color:#A31515;--shiki-dark:#CE9178">'..\..\'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LoadImage(DataPath + </span><span style="color:#A31515;--shiki-dark:#CE9178">'sign.png'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbSignatureType.ItemIndex := Ord(TSignatureType.PAdES_B_B);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFSigningPdfs.btnCreateAndSignPdfClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Cert: TX509Certificate2;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Signer: TCmsSigner;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SignerFactory: TPdfSignerFactory;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Signature: TPdfSignature;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Load the Excel file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#0000FF;--shiki-dark:#569CD6">not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OpenExcelDialog.Execute) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Open(OpenExcelDialog.FileName);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Export it to pdf.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf := TFlexCelPdfExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.FontEmbed := TFontEmbed.Embed;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //Load the certificate and create a signer.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Cert := EncryptionFactory.GetX509Certificate(TFile.ReadAllBytes(DataPath + </span><span style="color:#A31515;--shiki-dark:#CE9178">'flexcel.pfx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#A31515;--shiki-dark:#CE9178">'password'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        // The current implementation uses only one certificate. The algorithm by</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        // default if you leave the second parameter empty is SHA512.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Signer := EncryptionFactory.GetSigner(TArray&#x3C;TX509Certificate2>.Create(Cert), </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        SignerFactory := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">          //The format of the signature is decided by the factory, not by the signature itself.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          SignerFactory := CreateSignerFactory(Signer);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          Signer := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#008000;--shiki-dark:#6A9955">//The factory now owns the Signer so we don't want to free it.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cbVisibleSignature.Checked) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">            //The -1 as "page" parameter means the last page.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            Signature := TPdfVisibleSignature.Create(SignerFactory,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                            'Signature'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                            'I have read the document and certify it is valid.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                            'Springfield'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                            'adrian@tmssoftware.com'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                            -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                            TUIRectangle.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">140</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">70</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                            ImgData);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            Signature := TPdfSignature.Create(SignerFactory,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                                          'Signature'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                                          'I have read the document and certify it is valid.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                                          'Springfield'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                                          'adrian@tmssoftware.com'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          SignerFactory := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#008000;--shiki-dark:#6A9955">//The signature now owns the factory so we don't want to free it.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        Except</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          Signer.Free;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Only if there is an error.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          SignerFactory.Free;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">          raise</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //A certifying signature (the default) says who is responsible for the document and which changes are</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //allowed in it afterwards, and only the first signature of a document can certify it. An approval</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //signature just says that whoever signed agrees with what the document says at that moment, and many of</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //them can be added to the same document.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Signature.Certify := cbCertify.Checked;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //You must sign the document *BEFORE* starting to write it.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        pdf.Sign(Signature); </span><span style="color:#008000;--shiki-dark:#6A9955">//Now the pdf owns the signature. There is no need to free it.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#0000FF;--shiki-dark:#569CD6">not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SavePdfDialog.Execute) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        pdf.ExportAllVisibleSheets(SavePdfDialog.FileName, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Signed Pdf'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Cert.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SavePdfDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFSigningPdfs.cbVisibleSignatureClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  delta: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SignaturePicture.Visible := cbVisibleSignature.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Delta := SignaturePicture.Height + </span><span style="color:#098658;--shiki-dark:#B5CEA8">30</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cbVisibleSignature.Checked) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Height := Height + delta </span><span style="color:#0000FF;--shiki-dark:#569CD6">else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Height := Height - delta;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFSigningPdfs.SignaturePictureClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#0000FF;--shiki-dark:#569CD6">not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OpenPictureDialog.Execute) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LoadImage(OpenPictureDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


