# Copyright information

## Main Copyright

Unless in the parts specifically mentioned below,
all files in this distribution are copyright (c) Adrian Gallero
and licensed under the terms detailed in the file license.rtf.

## Third party copyrights

This distribution might also contain the following licensed code:


### File __FlexCelHash: MurmurHash3 implementation.

Parts are based in the public-domain implementation of MumurHash3 from https://github.com/aappleby/smhasher/blob/master/src/MurmurHash3.cpp

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>// MurmurHash3 was written by Austin Appleby, and is placed in the public</span></span>
<span class="line"><span>// domain. The author hereby disclaims copyright to this source code.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>// Note - The x86 and x64 versions do _not_ produce the same results, as the</span></span>
<span class="line"><span>// algorithms are optimized for their respective platforms. You can still</span></span>
<span class="line"><span>// compile and run any of them on any platform, but your performance with the</span></span>
<span class="line"><span>// non-native version will be less than optimal.</span></span>
<span class="line"><span></span></span></code></pre>

-----------------------------------------------------------

### File __RandomXorShift: xoshiro 256++ Random implementation.

Parts are based in the public-domain implementation of xoshiro 256++ from https://prng.di.unimi.it/xoshiro256plusplus.c

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>*  Written in 2019 by David Blackman and Sebastiano Vigna (vigna@acm.org)</span></span>
<span class="line"><span></span></span>
<span class="line"><span>To the extent possible under law, the author has dedicated all copyright</span></span>
<span class="line"><span>and related and neighboring rights to this software to the public domain</span></span>
<span class="line"><span>worldwide. This software is distributed without any warranty.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>See &#x3C;http://creativecommons.org/publicdomain/zero/1.0/>. */</span></span>
<span class="line"><span></span></span></code></pre>

-----------------------------------------------------------


### File _UXlsMD5: MD5 Message-Digest Algorithm.

Parts are Copyright (c) 1990-2, RSA Data Security, Inc.

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>Copyright (C) 1990-2, RSA Data Security, Inc. Created 1990.</span></span>
<span class="line"><span>All rights reserved.</span></span>
<span class="line"><span></span></span>
<span class="line"><span></span></span>
<span class="line"><span>RSA Data Security, Inc. makes no representations concerning either</span></span>
<span class="line"><span>the merchantability of this software or the suitability of this</span></span>
<span class="line"><span>software for any particular purpose. It is provided ""as is""</span></span>
<span class="line"><span>without express or implied warranty of any kind.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>These notices must be retained in any copies of any part of this</span></span>
<span class="line"><span>documentation and/or software.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Copyright (C) 1991-2, RSA Data Security, Inc. Created 1991.</span></span>
<span class="line"><span>All rights reserved.</span></span>
<span class="line"><span></span></span></code></pre>



-----------------------------------------------------------

### SHA1 Algorithm.

FlexCel uses the SHA1 algorithm which is Copyright (C) The Internet Society (2001).  All Rights Reserved.

SHA1 is licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>RFC 3174 - US Secure Hash Algorithm 1 (SHA1)</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Copyright(C) The Internet Society(2001).  All Rights Reserved.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>This document and translations of it may be copied and furnished to</span></span>
<span class="line"><span>others, and derivative works that comment on or otherwise explain it</span></span>
<span class="line"><span>or assist in its implementation may be prepared, copied, published</span></span>
<span class="line"><span>and distributed, in whole or in part, without restriction of any</span></span>
<span class="line"><span>kind, provided that the above copyright notice and this paragraph are</span></span>
<span class="line"><span>included on all such copies and derivative works.  However, this</span></span>
<span class="line"><span>document itself may not be modified in any way, such as by removing</span></span>
<span class="line"><span>the copyright notice or references to the Internet Society or other</span></span>
<span class="line"><span>Internet organizations, except as needed for the purpose of</span></span>
<span class="line"><span>developing Internet standards in which case the procedures for</span></span>
<span class="line"><span>copyrights defined in the Internet Standards process must be</span></span>
<span class="line"><span>followed, or as required to translate it into languages other than</span></span>
<span class="line"><span>English.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>The limited permissions granted above are perpetual and will not be</span></span>
<span class="line"><span>revoked by the Internet Society or its successors or assigns.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>This document and the information contained herein is provided on an</span></span>
<span class="line"><span>"AS IS" basis and THE INTERNET SOCIETY AND THE INTERNET ENGINEERING</span></span>
<span class="line"><span>TASK FORCE DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING</span></span>
<span class="line"><span>BUT NOT LIMITED TO ANY WARRANTY THAT THE USE OF THE INFORMATION</span></span>
<span class="line"><span>HEREIN WILL NOT INFRINGE ANY RIGHTS OR ANY IMPLIED WARRANTIES OF</span></span>
<span class="line"><span>MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Acknowledgement</span></span>
<span class="line"><span>Funding for the RFC Editor function is currently provided by the</span></span>
<span class="line"><span>Internet Society.</span></span>
<span class="line"><span></span></span></code></pre>

-----------------------------------------------------------

### Files _UCompress20.TCompressor, Source\Zlib\*.*: Zlib algorithm implementation.

Parts are Copyright (C) 1995-2004 Jean-loup Gailly and Mark Adler

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>Copyright (C) 1995-2004 Jean-loup Gailly and Mark Adler</span></span>
<span class="line"><span></span></span>
<span class="line"><span>This software is provided 'as-is', without any express or implied</span></span>
<span class="line"><span>warranty.  In no event will the authors be held liable for any damages</span></span>
<span class="line"><span>arising from the use of this software.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Permission is granted to anyone to use this software for any purpose,</span></span>
<span class="line"><span>including commercial applications, and to alter it and redistribute it</span></span>
<span class="line"><span>freely, subject to the following restrictions:</span></span>
<span class="line"><span></span></span>
<span class="line"><span>1. The origin of this software must not be misrepresented; you must not</span></span>
<span class="line"><span>   claim that you wrote the original software. If you use this software</span></span>
<span class="line"><span>   in a product, an acknowledgment in the product documentation would be</span></span>
<span class="line"><span>   appreciated but is not required.</span></span>
<span class="line"><span>2. Altered source versions must be plainly marked as such, and must not be</span></span>
<span class="line"><span>   misrepresented as being the original software.</span></span>
<span class="line"><span>3. This notice may not be removed or altered from any source distribution.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Jean-loup Gailly        Mark Adler</span></span>
<span class="line"><span>jloup@gzip.org          madler@alumni.caltech.edu</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### Files flxZLibEx_XE, flxZLibExApi_XE, flxZLibExGZ_XE: Zlib implementation in Delphi.

Parts are Copyright(c) 2000-2010 base2 technologies and copyright (c) 1995-2002 Borland Software Corporation

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>this software is provided "as-is", without any express or implied warranty.</span></span>
<span class="line"><span>in no event will the authors be held liable for any damages arising from the</span></span>
<span class="line"><span>use of this software.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>permission is granted to anyone to use this software for any purpose,</span></span>
<span class="line"><span>including commercial applications.  please do not misrepresent the origin of</span></span>
<span class="line"><span>this software.  if you use this software in a product, an acknowledgment in</span></span>
<span class="line"><span>the product documentation (readme, about box, help file, etc.) would be</span></span>
<span class="line"><span>appreciated but is not required.</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------


### File _EllipticalArc.TEllipticalArc: Implementation of an arc using Bezier curves.

Parts are Copyright (c) 2003-2004, Luc Maisonobe

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>// Copyright (c) 2003-2004, Luc Maisonobe</span></span>
<span class="line"><span>// All rights reserved.</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>// Redistribution and use in source and binary forms, with</span></span>
<span class="line"><span>// or without modification, are permitted provided that</span></span>
<span class="line"><span>// the following conditions are met:</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>//    Redistributions of source code must retain the</span></span>
<span class="line"><span>//    above copyright notice, this list of conditions and</span></span>
<span class="line"><span>//    the following disclaimer.</span></span>
<span class="line"><span>//    Redistributions in binary form must reproduce the</span></span>
<span class="line"><span>//    above copyright notice, this list of conditions and</span></span>
<span class="line"><span>//    the following disclaimer in the documentation</span></span>
<span class="line"><span>//    and/or other materials provided with the</span></span>
<span class="line"><span>//    distribution.</span></span>
<span class="line"><span>//    Neither the names of spaceroots.org, spaceroots.com</span></span>
<span class="line"><span>//    nor the names of their contributors may be used to</span></span>
<span class="line"><span>//    endorse or promote products derived from this</span></span>
<span class="line"><span>//    software without specific prior written permission.</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND</span></span>
<span class="line"><span>// CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED</span></span>
<span class="line"><span>// WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED</span></span>
<span class="line"><span>// WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A</span></span>
<span class="line"><span>// PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL</span></span>
<span class="line"><span>// THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY</span></span>
<span class="line"><span>// DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR</span></span>
<span class="line"><span>// CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,</span></span>
<span class="line"><span>// PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF</span></span>
<span class="line"><span>// USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)</span></span>
<span class="line"><span>// HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER</span></span>
<span class="line"><span>// IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING</span></span>
<span class="line"><span>// NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE</span></span>
<span class="line"><span>// USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE</span></span>
<span class="line"><span>// POSSIBILITY OF SUCH DAMAGE.</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### File _BidiReference.BidiReference, _BidiPBAReference.BidiPBAReference and _ArabicShaping.ArabicShaping: Implementation of arabic shaping algorithm.

Parts are Copyright (c) 1991-2019 Unicode, Inc. All rights reserved. Distributed under the Terms of Use in http://www.unicode.org/copyright.html

Those parts are licensed under the following following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>UNICODE, INC. LICENSE AGREEMENT - DATA FILES AND SOFTWARE</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Unicode Data Files include all data files under the directories http://www.unicode.org/Public/, http://www.unicode.org/reports/, and http://www.unicode.org/cldr/data/. Unicode Data Files do not include PDF online code charts under the directory http://www.unicode.org/Public/. Software includes any source code published in the Unicode Standard or under the directories http://www.unicode.org/Public/, http://www.unicode.org/reports/, and http://www.unicode.org/cldr/data/.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>NOTICE TO USER: Carefully read the following legal agreement. BY DOWNLOADING, INSTALLING, COPYING OR OTHERWISE USING UNICODE INC.'S DATA FILES ("DATA FILES"), AND/OR SOFTWARE ("SOFTWARE"), YOU UNEQUIVOCALLY ACCEPT, AND AGREE TO BE BOUND BY, ALL OF THE TERMS AND CONDITIONS OF THIS AGREEMENT. IF YOU DO NOT AGREE, DO NOT DOWNLOAD, INSTALL, COPY, DISTRIBUTE OR USE THE DATA FILES OR SOFTWARE.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>COPYRIGHT AND PERMISSION NOTICE</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Copyright (c) 1991-2019 Unicode, Inc. All rights reserved. Distributed under the Terms of Use in http://www.unicode.org/copyright.html.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Permission is hereby granted, free of charge, to any person obtaining a copy of the Unicode data files and any associated documentation (the "Data Files") or Unicode software and any associated documentation (the "Software") to deal in the Data Files or Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, and/or sell copies of the Data Files or Software, and to permit persons to whom the Data Files or Software are furnished to do so, provided that (a) the above copyright notice(s) and this permission notice appear with all copies of the Data Files or Software, (b) both the above copyright notice(s) and this permission notice appear in associated documentation, and (c) there is clear notice in each modified Data File or in the Software as well as in the documentation associated with the Data File(s) or Software that the data or software has been modified.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>THE DATA FILES AND SOFTWARE ARE PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT OF THIRD PARTY RIGHTS. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR HOLDERS INCLUDED IN THIS NOTICE BE LIABLE FOR ANY CLAIM, OR ANY SPECIAL INDIRECT OR CONSEQUENTIAL DAMAGES, OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THE DATA FILES OR SOFTWARE.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Except as contained in this notice, the name of a copyright holder shall not be used in advertising or otherwise to promote the sale, use or other dealings in these Data Files or Software without prior written authorization of the copyright holder</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### File _KhmerShaper.KhmerShaper: Shaper for Khmer language.

Parts are Copyright (c) 2008 Nokia Corporation and/or its subsidiary(-ies)

Those parts are licensed under the following following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>/*</span></span>
<span class="line"><span> * Copyright (C) 2008 Nokia Corporation and/or its subsidiary(-ies)</span></span>
<span class="line"><span> *</span></span>
<span class="line"><span> * This is part of HarfBuzz, an OpenType Layout engine library.</span></span>
<span class="line"><span> *</span></span>
<span class="line"><span> * Permission is hereby granted, without written agreement and without</span></span>
<span class="line"><span> * license or royalty fees, to use, copy, modify, and distribute this</span></span>
<span class="line"><span> * software and its documentation for any purpose, provided that the</span></span>
<span class="line"><span> * above copyright notice and the following two paragraphs appear in</span></span>
<span class="line"><span> * all copies of this software.</span></span>
<span class="line"><span> *</span></span>
<span class="line"><span> * IN NO EVENT SHALL THE COPYRIGHT HOLDER BE LIABLE TO ANY PARTY FOR</span></span>
<span class="line"><span> * DIRECT, INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES</span></span>
<span class="line"><span> * ARISING OUT OF THE USE OF THIS SOFTWARE AND ITS DOCUMENTATION, EVEN</span></span>
<span class="line"><span> * IF THE COPYRIGHT HOLDER HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH</span></span>
<span class="line"><span> * DAMAGE.</span></span>
<span class="line"><span> *</span></span>
<span class="line"><span> * THE COPYRIGHT HOLDER SPECIFICALLY DISCLAIMS ANY WARRANTIES, INCLUDING,</span></span>
<span class="line"><span> * BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND</span></span>
<span class="line"><span> * FITNESS FOR A PARTICULAR PURPOSE.  THE SOFTWARE PROVIDED HEREUNDER IS</span></span>
<span class="line"><span> * ON AN "AS IS" BASIS, AND THE COPYRIGHT HOLDER HAS NO OBLIGATION TO</span></span>
<span class="line"><span> * PROVIDE MAINTENANCE, SUPPORT, UPDATES, ENHANCEMENTS, OR MODIFICATIONS.</span></span>
<span class="line"><span> */</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### Files _OctreeQuantizer.OctreeQuantizer, _OctreeQuantizer.Octree,  _Quantizer.Quantizer: Color Quantizer to convert images to grayscale.

Parts are Copyright (c) Morgan Skinner

Those parts are licensed under the following following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>  THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF</span></span>
<span class="line"><span>  ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO</span></span>
<span class="line"><span>  THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A</span></span>
<span class="line"><span>  PARTICULAR PURPOSE.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>    This is sample code and is freely distributable.</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### File: sRGB_IEC61966-2-1_black_scaled.icc: Color profile for embedding in PDF/A files.

Copyright International Color Consortium, 2009

This file contains a color profile which will be embedded when you create PDF/A files, or when you set the PDF generation options to embed the color profile.
It is licensed on the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>To anyone who acknowledges that the file "sRGB_IEC61966-2-1_black scaled.icc" is provided "AS IS" WITH NO EXPRESS OR IMPLIED WARRANTY, permission to use, copy and distribute these file for any purpose is hereby granted without fee, provided that the file is not changed including the ICC copyright notice tag, and that the name of ICC shall not be used in advertising or publicity pertaining to distribution of the software without specific, written prior permission. ICC makes no representations about the suitability of this software for any purpose.</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### File: PdfStandardFontInfo.data.gz: Standard PDF Font data.

Copyright (c) Adobe systems

PdfStandardFontInfo.data.gz contains postcript data for fonts, and data comes from the AFM files published by Adobe, which are distributed under the following license:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span> This file and the 14 PostScript(R) AFM files it accompanies may be used, copied, and distributed for any purpose and without charge, with or without modification, provided that all copyright notices are retained; that the AFM files are not distributed without this file; that all modifications to this file or any of the AFM files are prominently noted in the modified file(s); and that this paragraph is not modified. Adobe Systems has no responsibility or obligation to support the use of the AFM files.</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### File __UStr2DateTime: Date and time handling routines.

Parts are Copyright (C) 2001 Marcel Narings, Copyright (C) 2004-2006 Novell, Inc (http://www.novell.com) and Copyright (C) 2012 Xamarin Inc (http://www.xamarin.com)

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>// Authors:</span></span>
<span class="line"><span>//   Marcel Narings (marcel@narings.nl)</span></span>
<span class="line"><span>//   Martin Baulig (martin@gnome.org)</span></span>
<span class="line"><span>//   Atsushi Enomoto (atsushi@ximian.com)</span></span>
<span class="line"><span>//   Marek Safar (marek.safar@gmail.com)</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>//   (C) 2001 Marcel Narings</span></span>
<span class="line"><span>// Copyright (C) 2004-2006 Novell, Inc (http://www.novell.com)</span></span>
<span class="line"><span>// Copyright (C) 2012 Xamarin Inc (http://www.xamarin.com)</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>// Permission is hereby granted, free of charge, to any person obtaining</span></span>
<span class="line"><span>// a copy of this software and associated documentation files (the</span></span>
<span class="line"><span>// "Software"), to deal in the Software without restriction, including</span></span>
<span class="line"><span>// without limitation the rights to use, copy, modify, merge, publish,</span></span>
<span class="line"><span>// distribute, sublicense, and/or sell copies of the Software, and to</span></span>
<span class="line"><span>// permit persons to whom the Software is furnished to do so, subject to</span></span>
<span class="line"><span>// the following conditions:</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>// The above copyright notice and this permission notice shall be</span></span>
<span class="line"><span>// included in all copies or substantial portions of the Software.</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>// THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,</span></span>
<span class="line"><span>// EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF</span></span>
<span class="line"><span>// MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND</span></span>
<span class="line"><span>// NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE</span></span>
<span class="line"><span>// LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION</span></span>
<span class="line"><span>// OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION</span></span>
<span class="line"><span>// WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------

### File: flxGDIPAPI_XE: GdiPlus wrapper for Delphi.

Parts are Copyright (C) Henri Gourvest from http://www.progdigy.com/?page_id=7

Those parts are licensed under the following terms:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>      {******************************************************************}</span></span>
<span class="line"><span>      { GDI+ API                                                         }</span></span>
<span class="line"><span>      {                                                                  }</span></span>
<span class="line"><span>      { home page : http://www.progdigy.com                              }</span></span>
<span class="line"><span>      { email     : hgourvest@progdigy.com                               }</span></span>
<span class="line"><span>      {                                                                  }</span></span>
<span class="line"><span>      { date      : 15-02-2002                                           }</span></span>
<span class="line"><span>      {                                                                  }</span></span>
<span class="line"><span>      { The contents of this file are used with permission, subject to   }</span></span>
<span class="line"><span>      { the Mozilla Public License Version 1.1 (the "License"); you may  }</span></span>
<span class="line"><span>      { not use this file except in compliance with the License. You may }</span></span>
<span class="line"><span>      { obtain a copy of the License at                                  }</span></span>
<span class="line"><span>      { http://www.mozilla.org/MPL/MPL-1.1.html                          }</span></span>
<span class="line"><span>      {                                                                  }</span></span>
<span class="line"><span>      { Software distributed under the License is distributed on an      }</span></span>
<span class="line"><span>      { "AS IS" basis, WITHOUT WARRANTY OF ANY KIND, either express or   }</span></span>
<span class="line"><span>      { implied. See the License for the specific language governing     }</span></span>
<span class="line"><span>      { rights and limitations under the License.                        }</span></span>
<span class="line"><span>      {                                                                  }</span></span>
<span class="line"><span>      { *****************************************************************}</span></span>
<span class="line"><span></span></span></code></pre>


### File: libskia.so: Skia Graphics Library

Copyright (c) 2011 Google Inc. All rights reserved.

Skia is used as a graphics backend in Linux, and it is only included if you use the FlexCel.SKIASupport or FlexCel.LCLSupport unit in your app.
Skia is licensed on the following terms (BSD Free Software License):

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>// Copyright (c) 2011 Google Inc. All rights reserved.</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>// Redistribution and use in source and binary forms, with or without</span></span>
<span class="line"><span>// modification, are permitted provided that the following conditions are</span></span>
<span class="line"><span>// met:</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>//    * Redistributions of source code must retain the above copyright</span></span>
<span class="line"><span>// notice, this list of conditions and the following disclaimer.</span></span>
<span class="line"><span>//    * Redistributions in binary form must reproduce the above</span></span>
<span class="line"><span>// copyright notice, this list of conditions and the following disclaimer</span></span>
<span class="line"><span>// in the documentation and/or other materials provided with the</span></span>
<span class="line"><span>// distribution.</span></span>
<span class="line"><span>//    * Neither the name of Google Inc. nor the names of its</span></span>
<span class="line"><span>// contributors may be used to endorse or promote products derived from</span></span>
<span class="line"><span>// this software without specific prior written permission.</span></span>
<span class="line"><span>//</span></span>
<span class="line"><span>// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS</span></span>
<span class="line"><span>// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT</span></span>
<span class="line"><span>// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR</span></span>
<span class="line"><span>// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT</span></span>
<span class="line"><span>// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,</span></span>
<span class="line"><span>// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT</span></span>
<span class="line"><span>// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,</span></span>
<span class="line"><span>// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY</span></span>
<span class="line"><span>// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT</span></span>
<span class="line"><span>// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE</span></span>
<span class="line"><span>// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.</span></span>
<span class="line"><span></span></span></code></pre>



-----------------------------------------------------------

### File: Northwind.mdb: Demo database.

Copyright (c) 2008, Microsoft

This file is used in the FlexCel demos (not used in the FlexCel itself) and it is under the following license:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>Copyright (c) 2008, Microsoft</span></span>
<span class="line"><span>All rights reserved.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:</span></span>
<span class="line"><span></span></span>
<span class="line"><span>* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>* Neither the name of Microsoft nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.</span></span>
<span class="line"><span></span></span>
<span class="line"><span>THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.</span></span>
<span class="line"><span></span></span></code></pre>


-----------------------------------------------------------


-----------------------------------------------------------

### Icons in demos and tools.

Some of the icons used in demos and tools are created using objects which are Copyright (c) Axialis Software Corporation

Those objects are used under the following license:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>This is a legal agreement between you (the "User") and Axialis Software Corporation ("Axialis"). By downloading this object pack (the "Objects") from Axialis.com, the user agrees to the following:</span></span>
<span class="line"><span></span></span>
<span class="line"><span> License Grant</span></span>
<span class="line"><span></span></span>
<span class="line"><span>Axialis grants the User a non-exclusive, non-transferable, royalty-free license to use these objects as indicated herein. The Objects can be assembled together to create icons (the "Icons").</span></span>
<span class="line"><span></span></span>
<span class="line"><span>You MAY:(a) assemble the Objects to create Icons using an Axialis product only; (b) use the Objects "as is" in personal or commercial software projects (menus, toolbars, dialog boxes...) as long as you own a licensed version of the associated Axialis Product; (c) use the created Icons in personal or commercial software projects (menus, toolbars, dialog boxes...) as long as you own a licensed version of the associated Axialis Product.</span></span>
<span class="line"><span></span></span>
<span class="line"><span> Restrictions</span></span>
<span class="line"><span></span></span>
<span class="line"><span>You MAY NOT:(a) use the Objects without owning a licensed version of the associated Axialis Product; (b) redistribute, loan, rent, sell the Objects "as is" and/or the created Icons as a set of Icons or individually; (c) use the Icons or Objects to illustrate pornographic, immoral, illegal or defamatory material.</span></span>
<span class="line"><span></span></span>
<span class="line"><span> Copyright / Ownership</span></span>
<span class="line"><span></span></span>
<span class="line"><span>The Objects are proprietary products of AXIALIS and are protected by copyright and other intellectual property laws. The Objects are licensed and not sold. You acquire only the right to use the Objects and do not acquire any rights, express or implied, in the Software other than those specified in this License.</span></span>
<span class="line"><span></span></span>
<span class="line"><span> Disclaimer of warranties</span></span>
<span class="line"><span></span></span>
<span class="line"><span>The Objects is supplied "as is". AXIALIS disclaims all warranties, expressed or implied, including, without limitation, the warranties of merchantability and of fitness for any purpose. The user must assume the entire risk of using the Objects.</span></span>
<span class="line"><span></span></span>
<span class="line"><span> Disclaimer of damages</span></span>
<span class="line"><span></span></span>
<span class="line"><span>AXIALIS assumes no liability for damages, direct or consequential, which may result from the use of the Objects, even if AXIALIS has been advised of the possibility of such damages. Any liability of the seller will be limited to refund the purchase price if any.</span></span>
<span class="line"><span></span></span>
<span class="line"><span></span></span></code></pre>

-----------------------------------------------------------
