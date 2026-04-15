---
uid: FlexViewTutorial
---

# iOS Tutorial
## Overview
In this tutorial we will create a small xls/x document viewer. The app isn't particularly useful or flashy, but it is designed to show most concepts you need to know in order to work with files in iOS

> [!Note]
> 
> **The complete source for this tutorial is available as [FlexView demo](xref:iOS_FlexView-FireMonkey_Mobile) in the FlexCel distribution.**


## Step 1. Setting up the Application

Lets start by creating a new Multi-Device Application:

<img alt = "new ios app menu" src = "../images/new-ios-app-menu.png" width = "490" height = "125"/>

<img alt = "new ios app dialog" src = "../images/new-ios-app-dialog.png" width = "563" height = "433"/>

* Select **Blank Application** (1) and then **Ok** (2)
* In Delphi press **Save** and give it a name. In this tutorial we will use **FlexView.dproj**  for the project and **UFlexView.pas** for the unit.

Once you have saved the project, set the target to **iOS** device. (or simulator if you are testing in a simulator and your Rad Studio version supports simulators)

<img alt = "select ios target" src = "../images/select-ios-target.png" width = "302" height = "276"/>

Then you can go to the application properties, and set icons and the application name.

You might now try running the application, it should show as an empty form in the simulator or the device.

## Step 2. Creating the User Interface

In the tool palette, select the “FlexCel” tab and drag a  to the Form:

<img alt = "ios flexcel previewer" src = "../images/ios-flexcel-previewer.png" width = "288" height = "340"/>

And set the “align” property of the TFlexCelPreviewer to “alClient”. The form should look like this:
<img alt = "ios flexview viewer" src = "../images/ios-flexview-viewer.png" width = "592" height = "455"/>


## Step 3. Registering the application
The next step is to tell iOS that our application can handle xls and xlsx files. This way, when another app like for example mail wants to share an xls or xlsx file, our application will show in the list of available options:

<img alt = "share sheet" src = "../images/share-sheet.png" width = "497" height = "535"/>

To register our app, we need to change the file Info.plist.

Delphi allows you to change simple properties in Info.plist in the “Version Info” screen:

<img alt = "delphi version info ios" src = "../images/delphi-version-info-ios.png" width = "771" height = "570"/>

But this only allows entering simple “Key/Value” entries. To register a file handler, we need to enter a more complex dictionary. As this is not possible in Delphi at the time of this writing (Delphi 11), we are going to do a workaround.

> [!Note]
> 
> We want to keep the “Delphi Settings” in Info.plist and merge our own settings. We don’t want to replace the Delphi settings completely, so if we change the “Version Info” in Delphi in the future, it will change in our application.


1) Create a file “**DocumentTypes.plist**” in your source folder with the following contents:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;?</span><span style="color:#800000;--shiki-dark:#569CD6">xml</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> version</span><span style="color:#000000;--shiki-dark:#D4D4D4">=</span><span style="color:#0000FF;--shiki-dark:#CE9178">"1.0"</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> encoding</span><span style="color:#000000;--shiki-dark:#D4D4D4">=</span><span style="color:#0000FF;--shiki-dark:#CE9178">"UTF-8"</span><span style="color:#800000;--shiki-dark:#808080">?></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;?</span><span style="color:#800000;--shiki-dark:#569CD6">xml</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> version</span><span style="color:#000000;--shiki-dark:#D4D4D4">=</span><span style="color:#0000FF;--shiki-dark:#CE9178">"1.0"</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> encoding</span><span style="color:#000000;--shiki-dark:#D4D4D4">=</span><span style="color:#0000FF;--shiki-dark:#CE9178">"UTF-8"</span><span style="color:#800000;--shiki-dark:#808080">?></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;!</span><span style="color:#0000FF;--shiki-dark:#569CD6">DOCTYPE</span><span style="color:#0000FF;--shiki-dark:#569CD6"> plist</span><span style="color:#000000;--shiki-dark:#D4D4D4"> PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">plist</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> version</span><span style="color:#000000;--shiki-dark:#D4D4D4">=</span><span style="color:#0000FF;--shiki-dark:#CE9178">"1.0"</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">CFBundleDocumentTypes</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">CFBundleTypeName</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">Excel document</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">CFBundleTypeRole</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">Editor</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">LSHandlerRank</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">Owner</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">LSItemContentTypes</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">           &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">com.microsoft.excel.xls</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">           &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">com.tms.flexcel.xlsx</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">			&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">org.openxmlformats.spreadsheetml.sheet</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">UTExportedTypeDeclarations</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">UTTypeDescription</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">Excel xlsx document</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">UTTypeTagSpecification</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">public.filename-extension</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">xlsx</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">public.mime-type</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">application/vnd.openxmlformats-officedocument.spreadsheetml.sheet</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">UTTypeConformsTo</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">       &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">public.data</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">UTTypeIdentifier</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">key</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">   &#x3C;</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span><span style="color:#000000;--shiki-dark:#D4D4D4">com.tms.flexcel.xlsx</span><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">string</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">array</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">dict</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"><span style="color:#800000;--shiki-dark:#808080">&#x3C;/</span><span style="color:#800000;--shiki-dark:#569CD6">plist</span><span style="color:#800000;--shiki-dark:#808080">></span></span>
<span class="line"></span></code></pre>

   This is the plist needed to register xls and xlsx files. You can find this file in the [FlexView demo](xref:iOS_FlexView-FireMonkey_Mobile) that comes with the FlexCel distribution.

2) To merge this plist with the Delphi generated plist, we are going to use a small tool included with FlexCel: **infoplist.exe**.  This tool will take two plists as input, and return another plist with the contents of the two original files merged. You can find it at &lt;FlexCelInstallDir>\\Tools\\CompiledTools  (Full source code is also available in the FlexCel distribution).
   So let’s go to “Project Options->Build Events” and add the following line as “Post-build event”: (note that the text will wrap, but it is a single line)

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">"$(FLEXCELVCLNT)\Tools\CompiledTools\infoplist.exe"</span><span style="color:#A31515;--shiki-dark:#CE9178"> "$(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">OUTPUTDIR</span><span style="color:#A31515;--shiki-dark:#CE9178">)\FlexView.info.plist"</span><span style="color:#A31515;--shiki-dark:#CE9178"> "$(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">PROJECTDIR</span><span style="color:#A31515;--shiki-dark:#CE9178">)\DocumentTypes.plist"</span><span style="color:#A31515;--shiki-dark:#CE9178"> "$(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">OUTPUTDIR</span><span style="color:#A31515;--shiki-dark:#CE9178">)\ActualFlexView.info.plist"</span></span>
<span class="line"></span></code></pre>


   <img alt = "post build event" src = "../images/post-build-event.png" width = "772" height = "241"/>

> [!Note]
> 
> Before writing the command, make sure to select “All configurations – All platforms” in the combobox at the top, so the command is applied in all cases


   If everything went fine, when you compile the project it should have a file “ActualFlexView.info.plist” in the output folder. You can view this file with notepad, and it should have the contents of the original FlexView.info.plist merged with our DocumentTypes.plist. Remember that this file will be recreated every time you build, so don’t edit it. Always edit the original “DocumentTypes.plist”.

> [!Note]
> 
> If you are having problems with this step, you can look at the “Output window” in Delphi and see if the post-build event is throwing any errors:
> 
> <img alt = "postbuildevent errors" src = "../images/postbuildevent-errors.png" width = "219" height = "135"/>


3) Compile the App in **Debug**/**Release** and for the **simulator**/**device**. This way all four ActualFlexView.info.plist files will be created.

4) The final step of the workaround is to make Delphi deploy the new “ActualFlexView.info.plist” instead of “FlexView.info.plist”.

   Go to “Menu->Project->Deployment”.

   If you want to register your app in all configurations, you’ll need to repeat this step four times: iOSDevice/Debug, iOSDevice/Release, iOSSimulator/Debug and iOSSimulator/Release. If you only care about registering in some of them, you can set just those. But as the files are in different folders, you can’t use “All configurations – All platforms” combobox. You’ll need to select each final configuration, and add the corresponding ActualFlexView.plist for the configuration:

   <img alt = "ios tutorial deploy 1" src = "../images/ios-tutorial-deploy-1.png" width = "656" height = "116"/>

   Once the file is added, search for “info.plist” in the “Remote Name” column. You might see more than one entry, uncheck them all:

   <img alt = "ios tutorial deploy 2" src = "../images/ios-tutorial-deploy-2.png" width = "856" height = "200"/>

   Now locate our file “ActualFlexCelView.info.plist”, and in the “Remote Name” column, enter “Info.plist”

   <img alt = "ios tutorial deploy 3" src = "../images/ios-tutorial-deploy-3.png" width = "787" height = "125"/>

   And in the “Platforms” column, select the only the configuration/platform we are adding. For example, if we are adding the file for “Debug/iOS device”, select Platforms and uncheck “iOSSimulator:

   <img alt = "ios tutorial deploy 4" src = "../images/ios-tutorial-deploy-4.png" width = "712" height = "257"/>

> [!Note]
> 
>    Some Delphi versions like for example Delphi 11 only support one iOS platform. (In Delphi 11's case this is iOS Device 64). If this is the case, then there is no need to unselect the other platforms, since there are none.
>    


   This concludes the workaround. Now the original Info.plist files won’t be deployed, and our merged file will be deployed instead.



Once you have done this, if you run the application and have for example an email with an xls or xlsx file, you should see “FlexView” in the list of possible applications where to send the file when you press "Share".

## Step 4. Reading the file sent by another application
If you tried the application after the last step, and pressed the “Open in FlexView” button, you will notice that FlexView starts, but the previewer is still empty. It won’t show the file that the other application sent.

What happens when you press the “Open in FlexView” button is that iOS  will copy the file in the “Documents/Inbox” private folder of FlexView, and send an OpenURL event to our app. We need to handle this event, and use it to load the file in the preview.

Add  **FMX.Platform** and **FMX.Platform.iOS** to your uses clause. After that, on the Form’s create event, write the following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IFmxApplicationEventService(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TPlatformServices.Current.GetPlatformService(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    IFmxApplicationEventService))</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    .SetApplicationEventHandler(AppHandler);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCelPreviewer1.Document :=</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TFlexCelImgExport.Create(TXlsFile.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.InvalidatePreview;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


And define the procedure AppHandler as:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>function TFormFlexView.AppHandler(AAppEvent: TApplicationEvent;</span></span>
<span class="line"><span>  AContext: TObject): Boolean;</span></span>
<span class="line"><span>begin</span></span>
<span class="line"><span>  Result := true;</span></span>
<span class="line"><span></span></span>
<span class="line"><span>  case AAppEvent of</span></span>
<span class="line"><span>   TApplicationEvent.aeOpenURL:</span></span>
<span class="line"><span>   begin</span></span>
<span class="line"><span>     Result := OpenFile(GetPhysicalPath((AContext as TiOSOpenApplicationContext).URL));</span></span>
<span class="line"><span>   end;</span></span>
<span class="line"><span>  end;</span></span>
<span class="line"><span>end;</span></span>
<span class="line"><span></span></span></code></pre>



> [!Note]
> 
> In iOS, we are going to get the URL of the file, not the filename. For example, the URL could be:
> 
> 'file://localhost/private/var/mobile/Applications/9D16227A-CB01-465D-B8F4-AC43D70C8461/Documents/Inbox/test.xlsx'
> 
> And the actual filename would be: ‘/private/var/mobile/Applications/9D16227A-CB01-465D-B8F4-AC43D70C8461/Documents/Inbox/test.xlsx’


But while iOS methods can normally use an URL or a path, Delphi’s TFileStream expects a path. This is why we need to convert the URL to a path, using the GetPhysicalPath function above.

We’ll use internal iOS functions to do the conversion, and so we will define it as:
<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetPhysicalPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> URL: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4"> FileURL: NSURL;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FileURL := TNSURL.Wrap(TNSURL.OCClass.URLWithString(NSStr(URL)));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := UTF8ToString(FileURL.path.UTF8String);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


And finally, define OpenFile as:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.OpenFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aURL: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ImgExport: TFlexCelImgExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls := TXlsFile.Create(aURL, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      TFile.Delete(aURL); </span><span style="color:#008000;--shiki-dark:#6A9955">//We've already read it. Now we need to</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">                //delete it or it would stay forever in the inbox.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //The file must be deleted even if it was invalid and FlexCel</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //raised an Exception when opening it.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ImgExport := TFlexCelImgExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.Document := ImgExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.InvalidatePreview;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


> [!Note]
> 
> We are using **ARC** here, so we don’t need to worry about freeing the objects. If this code was for Win32 FlexCel, we would have to free all objects.


If you run the application now and press “Open in FlexView” from another application, FlexView should start and display the file.

## Step 5. Modifying the file
FlexCel currently doesn’t provide a “Spreadsheet” component, even when one is planned for the future. So we are doing this demo with a Preview component, which isn’t really designed for editing. But anyway, we can add some basic editing capabilities.

In this step, we are going to add edit functionality to our app:

<img alt = "flexview edit ui" src = "../images/flexview-edit-ui.png" width = "486" height = "385"/>

1. Select a Toolbar component from the component bar and drop it into the form.
2. Drop a TSpeedButton on it, and name it “edEdit”. Set the “StyleLookup” property of the button to “composetoolbuttonbordered”. Set its anchor to be “akRight” instead of “akLeft”
3. Add a TCalloutPanel, name it “PanelEditor”, set its “Visible” property to false, and add “akRight” to its Anchor property
4. Drop a TMemo in the panel, set its “WrapText” property to true, and name it “edCell”
5. Drop a TEdit, name it edAddress. Set its text to “A1”
6. Drop two buttons, name them edOk and edCancel

Double click on the edit button, and write the following code:
<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edEditClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PanelEditor.Visible := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


Double click the edCancel button and write this code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PanelEditor.Visible := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


Double click the edOk button and write this code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edOkClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  addr: TCellAddress;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Trim(edAddress.Text) &#x3C;> </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      addr := TCellAddress.Create(edAddress.Text);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    except</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Invalid Cell Address: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + edAddress.Text);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.Document.Workbook.SetCellFromString(addr.Row, addr.Col, edCell.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.Document.Workbook.Recalc;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.InvalidatePreview;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PanelEditor.Visible := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


This will take care of updating the cell and recalculating the file.

> [!Note]
> 
> While the preferred way to set a cell value in FlexCel is using [SetCellValue](~/api/FlexCel.Core/TExcelFile//SetCellValue.md), here we are using [SetCellFromString](~/api/FlexCel.Core/TExcelFile//SetCellFromString.md) since we have the values stored as strings, so we need to convert them.


Now the final step in editing is to update the value of the cell when you type a different address. We can do it with the “OnChange” event of the “edAddress” control:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edAddressChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  UpdateCellValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

 
And we define UpdateCellValue as follows:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>procedure TFormFlexView.UpdateCellValue;</span></span>
<span class="line"><span>var</span></span>
<span class="line"><span>  addr: TCellAddress;</span></span>
<span class="line"><span>begin</span></span>
<span class="line"><span>  if Trim(edAddress.Text) &#x3C;> '' then</span></span>
<span class="line"><span>  begin</span></span>
<span class="line"><span>    try</span></span>
<span class="line"><span>      addr := TCellAddress.Create(edAddress.Text);</span></span>
<span class="line"><span>    except</span></span>
<span class="line"><span>      exit;</span></span>
<span class="line"><span>    end;</span></span>
<span class="line"><span>    edCell.Text := FlexCelPreviewer1.Document.Workbook.GetCellValue(addr.Row, addr.Col);</span></span>
<span class="line"><span>  end else</span></span>
<span class="line"><span>  begin</span></span>
<span class="line"><span>    edCell.Text := '';</span></span>
<span class="line"><span>  end;</span></span>
<span class="line"><span>end;</span></span>
<span class="line"><span></span></span></code></pre>


And to complete the app, we will call UpdateCellValue every time we show the panel. Let’s change the edit click event to be:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>procedure TFormFlexView.edEditClick(Sender: TObject);</span></span>
<span class="line"><span>begin</span></span>
<span class="line"><span>  UpdateCellValue;</span></span>
<span class="line"><span>  PanelEditor.Visible := true;</span></span>
<span class="line"><span>end;</span></span>
<span class="line"><span></span></span></code></pre>

If you run the app now, you can press the “Edit” button and a popover with the editing options will appear. Type the cell reference you want to change (like for example A2) and the value for the cell, press Ok and the cell will change, while the full file will be recalculated.


## Step 6. Sending the file to other applications
In [step 4](#step-4-reading-the-file-sent-by-another-application)
we saw how to import a file from another application. In this step we are going to see how to do the opposite: How to export the file and make it available to other applications that handle xls or xlsx files. We will also see how to print the file.

Luckily, this isn’t complex to do.

FlexCel comes with a component that makes this easy: TFlexCelDocExport

To export the file, we'll follow the steps:

<img alt = "ios tutorial share" src = "../images/ios-tutorial-share.png" width = "441" height = "503"/>

1. Drop a TFlexCelDocExport into the form.
2. Drop another TSpeedButton next to our edEdit button, name it “edShare”, and set its style to “actiontoolbuttonbordered”
   We want to be able to export the file either as Excel or as PDF, so we need to call a menu when you press this button. Exporting to pdf will also allow us to print the file, as this functionality comes for free with iOS.
3. Drop a TPopup in the form, name it PopShare
4. Drop a TListBox inside PopShare
5. Add two items to the listbox, name them edPdf and edExcel and set their text to Pdf and Excel.

Now, on the edShare handler, show the popup:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edShareClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PopShare.Parent := edShare;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PopShare.Popup;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


And, in the listbox item handlers, we will show the share dialog. The Excel handler is the easiest, because we don’t need to convert the file. We will just close the popup and call the ExportFile method in TFlexCelDocExport:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edExcelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PopShare.Visible := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCelPreviewer1.Document.Workbook.Save(GetHomePath + </span><span style="color:#A31515;--shiki-dark:#CE9178">'/tmp/tmpflexcel.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCelDocExport1.ExportFile(edShare, FlexCelPreviewer1.Document.Workbook.ActiveFileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


Note that we save the file to the tmp folder and export that. The tmp folder will be cleaned by iOS, so we don’t need to worry about deleting the file after we used it.

The pdf export code is a little more complex, in that we need to create the pdf file first:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edPdfClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  tmppdf: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PopShare.Visible := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf := TFlexCelPdfExport.Create(FlexCelPreviewer1.Document.Workbook, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  tmppdf := GetHomePath + </span><span style="color:#A31515;--shiki-dark:#CE9178">'/tmp/tmpflexcel.pdf'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf.BeginExport(TFileStream.Create(tmppdf, fmCreate));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf.ExportAllVisibleSheets(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Sheets'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf.EndExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCelDocExport1.ExportFile(edShare, tmppdf);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

 
But conceptually is as simple as exporting an xls/x file.


> [!Note]
> 
> **Exporting to pdf will show a “Print” option when sharing the file**, allowing us to print it.


## Step 7. Final touches
In this small tutorial we’ve gone from zero to a fully working Excel preview / pdf converter application. But for simplicity, we’ve conveniently “forgotten” about an interesting fact: Excel files can have more than one sheet.

In this final step we will add the code to show any sheet in our application, not just the one that was selected when the file was saved.
To do this, we will add a combobox to the toolbar. In it, we will show the file name we are working in, and the active sheet. When the user changes the sheet, we will update our app.
So drop a combobox and set its right anchor to true:

<img alt = "ios tutorial sheet selector" src = "../images/ios-tutorial-sheet-selector.png" width = "320" height = "63"/>

Name the combobox edSheets. In the “Items” property, write: “No File - Sheet 1” This text will show when you open the file from the Launchpad, instead of opening it from another app.

Set the ItemIndex property to 0.

Write the following event handler for the “OnChange” event in the combobox:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.edSheetsChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (edSheets.ItemIndex &#x3C; </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCelPreviewer1.Document.Workbook.ActiveSheet := edSheets.ItemIndex + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCelPreviewer1.InvalidatePreview;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


And finally, change the OpenFile method so when you open the file, you load the sheet in the combobox:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.OpenFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aURL: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): </span><span style="color:#0000FF;--shiki-dark:#569CD6">boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ImgExport: TFlexCelImgExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls := TXlsFile.Create(aURL, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      TFile.Delete(aURL); </span><span style="color:#008000;--shiki-dark:#6A9955">//We've already read it. Now we need to</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">                //delete it or it would stay forever in the inbox.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //The file must be deleted even if it was invalid and FlexCel</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //raised an Exception when opening it.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ImgExport := TFlexCelImgExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.Document := ImgExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    LoadSheets(xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelPreviewer1.InvalidatePreview;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

 
Where “LoadSheets” is:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFormFlexView.LoadSheets</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls: TXlsFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edSheets.Clear;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls.SheetCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edSheets.Items.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ExtractFileName(xls.ActiveFileName) +</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">    ' - Sheet: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + xls.GetSheetName(i));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edSheets.ItemIndex := xls.ActiveSheet - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


And we are done! If you run the application now, you should be able to accept xls and xlsx files from other applications like mail or DropBox, to display them and edit them, and to share the modified files with other applications. You will also be able to natively print the xls and xlsx files by pressing the "Share" button.

