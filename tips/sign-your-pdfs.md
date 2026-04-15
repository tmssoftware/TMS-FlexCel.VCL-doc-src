# Sign your PDF files

## A little story
Some time ago I requested some official documents from my government, and they provided them to me in PDF format. This is all as expected: PDF is the de-facto standard for digital documents.

But what I didn't expect was that those documents weren't digitally signed. This doesn't make them completely useless, but the fact that they are not digitally signed diminishes a lot their value for me. If in the future I need to use those documents myself to prove anything, I can't really prove that I didn't create those documents myself, or that I modified the data on them. Can you imagine them giving you any old-fashioned paper document that is not signed and/or rubberstamped?

The government should digitally sign all the digital documents they give us, in the same way they physically sign their paper documents. And if you are creating documents that can be used as proof of anything, so should you.

## What is a digital sign

Digitally signing a PDF document is a way to prove that the document is the same as the one you produced, and it wasn't altered by anyone else. Someone might change the document, but the signature will become invalid. They might re-sign the document, but they would have to sign it with their signature, not with yours. The only way they can have a PDF signed by you is if you gave that exact PDF to them.

PDF signing is also a proven technology based on solid asymmetric encryption. It is not something that you (or anyone else) can fake with a 5-minute google search, and neither with months of hard work. A digital sign is actually much more secure than a physical sign, as long as you use a secure encryption algorithm.

> [!Warning]
> 
> When working in FlexCel .NET, the examples used the default algorithm in a CMSSigner, which happens to be [SHA1](https://en.wikipedia.org/wiki/SHA-1). SHA1 is not considered secure anymore, so we have updated the examples to use SHA512. If you have old code, you might want to update it to use SHA512 too. In Delphi, we already use SHA512 by default.


## How to keep your signing secure.

As mentioned in the previous section, signing is a safe way to ensure your documents are not altered. But you need to do it right, and in this section we will discuss some of the stuff that you need to care about.

### Keep your key secure
 The most important thing you need to ensure is that **nobody can get your certificate with your private key**. No matter how good the lock on your door, if the attacker gets the key, he will be able to enter. Or in this case, if he gets your signing key, he will be able to sign as if he was you.

 In practice this means that you **can't bundle the certificate with your app**, even if you encrypt the certificate. If your application can read the certificate, a hacker can too. The only secure way to keep the certificate safe is to sign the PDFs in a server that your users don't have access to.

### Keep up to date with the signing algorithms

As we advance in our technology, vulnerabilities can be found in the algorithms used to sign, and you need to make sure you aren't using an algorithm that is considered vulnerable. At the time of this writing, this means to use SHA256 or SHA512 and not SHA1 as [SHA1 is known to be non-secure](https://arstechnica.com/security/2017/02/at-deaths-door-for-years-widely-used-sha1-function-is-now-dead/)

Should SHA2 or SHA3 become vulnerable in the future, you will need to update the signing algorithm again.

### Get a real certificate from a trusted CA

You can sign your PDFs with self-signed certificates and it will work, but then, nothing is preventing an attacker from creating his own self-signed certificates too, where he claims to be you.

If you teach your users to trust your self-signed certificates, they might trust other self-signed certificates too.


## Getting more information
You can read more about how to sign PDF files with FlexCel at the [PDF guide](xref:PdfExportingGuide#signing-pdf-files)

## Appendix: Also use PDF/A
As we are discussing how to best ship PDF files, I would also like to mention that it is a great idea to ship your documents as [PDF/A](https://en.wikipedia.org/wiki/PDF/A).
Basically, a PDF/A file is a file designed so "it can be still be read 100 years from now". And why wouldn't you want your documents
to be still readable 100 years from now? Documents created 20 years ago (like a wks lotus 123 file) might be already difficult to open today. Will it still be possible to open them 100 years from now?

Of course nobody can guarantee that any file (not PDF, nor PDF/A) will still be readable in the future. But PDF/A does have some characteristics that make it likely. For example:

  * It is "frozen in time". Different from normal pdf which is constantly evolving, the PDF/A file format is done. It will never change, and it will be the same 100 years from now. Nobody knows how the PDF file format might have evolved by then.
  * It removes complex and unnecessary stuff which is present in normal PDFs like JavaScript, Audio and Video.
  * It requires that everything is self-contained in the document. So for example the fonts that you use (which might not be available in the future) must be embedded.
  * There are multiple independent validators to check if a PDF/A file honors all the requisites. FlexCel currently uses 3 different validators to ensure that the documents it generates are valid.

  It doesn't mean that there are not drawbacks too: By making your files self-contained they will be larger, and some PDF features you might want to use might not be available. But in most cases, if your documents are meant to last, you should consider PDF/A.

  There are many varieties of PDF/A and all of them are supported by FlexCel. If you are not sure on what flavor to use, I would recommend PDF/A2, as PDF/A1 is a little too restrictive, especially because it doesn't support the modern signing algorithms we use in FlexCel. So if you want to sign **and** PDF/A your files, you can't use PDFA/1. PDF/A3 is similar to A2, but it allows attachments. Use A3 only if you want to attach files to your pdf documents.

  You can read more on how to create PDF/A files in the [PDF guide](xref:PdfExportingGuide#creating-pdfa-files)
