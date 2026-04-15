---
uid: VclFlexCelCoreVsFlexCelVCLSupport
---

# VCL.FlexCel.Core vs FlexCel.VCLSupport


Until FlexCel 7.17, you used `VCL/FMX/LCL/SKIA.FlexCel.Core` at least once in your project and then `FlexCel.Core` in the rest of your units. Since FlexCel 7.18, while your old code and uses will still work, we now encourage you to use `FlexCel.VCL(FMX/LCL/SKIA)Support` instead. In this tip, we will expand on the reasons why.

## How we arrived here

When FlexCel 5 launched back in 2012, it came with different "FlexCel.Core" units for different platforms. If you were writing a VCL application, you had to use `VCL.FlexCel.Core`. If you were writing an FMX application, you would use `FMX.FlexCel.Core` instead. All the other units, like `FlexCel.Render`, were platform-agnostic, didn't have a "VCL" or "FMX" prefix, and worked everywhere.

But this approach rapidly became tiring. In reality, most of the code you write in FlexCel is cross-platform by default, and it made no sense to write `uses {$IFDEF FIREMONKEY}FMX.FlexCel.Core{$ELSE}VCL.FlexCel.Core{$ENDIF}` in every unit. So in [2014](https://doc.tmssoftware.com/flexcel/vcl/about/whatsnew.html#new-in-v-6600---october-2014), we introduced a new unit: `FlexCel.Core`, which was platform-agnostic the same as the others like `FlexCel.Render` and could be used everywhere. You still had to use at least once in your project `VCL/FMX.FlexCel.Core` to initialize the graphics engine, but all the other units could use `FlexCel.Core` and not worry about the platform.

This solution wasn't as elegant as we would have liked, but it worked well and didn't break any existing code, which is one big priority for us. Your old code using `VCL.FlexCel.Core` and ifdefs would still work, and you could use `FlexCel.Core` for the newer units.

## It is 2023 and C++ Builder enters the chat

FlexCel [supported C++ Builder almost from the start](https://doc.tmssoftware.com/flexcel/vcl/about/whatsnew.html#new-in-v-5020). But changes in how headers are generated in the latest C++ builder releases are breaking our code without a simple solution going forward. This problem made us rethink everything from the start, and that's how we arrived at the newer units. Below are the issues with our old approach:

### Namespace nightmare

When generating the headers for both units, C++ Builder automatically creates a namespace for each "dot" in the name. So "VCL.FlexCel.Core" would generate a header like this:
<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">namespace</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> Vcl</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  namespace</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> Flexcel</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     namespace</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> Core</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    {</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     ...code...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"></span></code></pre>


And then automatically use all the namespaces. The code will be like this:
<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> !</span><span style="color:#AF00DB;--shiki-dark:#C586C0">defined</span><span style="color:#0000FF;--shiki-dark:#569CD6">(DELPHIHEADER_NO_IMPLICIT_NAMESPACE_USE) </span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x26;&#x26;</span><span style="color:#000000;--shiki-dark:#D4D4D4"> !</span><span style="color:#AF00DB;--shiki-dark:#C586C0">defined</span><span style="color:#0000FF;--shiki-dark:#569CD6">(NO_USING_NAMESPACE_VCL_FLEXCEL_CORE)</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">using</span><span style="color:#0000FF;--shiki-dark:#569CD6"> namespace</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> Vcl</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#267F99;--shiki-dark:#4EC9B0">Flexcel</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#267F99;--shiki-dark:#4EC9B0">Core</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> !</span><span style="color:#AF00DB;--shiki-dark:#C586C0">defined</span><span style="color:#0000FF;--shiki-dark:#569CD6">(DELPHIHEADER_NO_IMPLICIT_NAMESPACE_USE) </span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x26;&#x26;</span><span style="color:#000000;--shiki-dark:#D4D4D4"> !</span><span style="color:#AF00DB;--shiki-dark:#C586C0">defined</span><span style="color:#0000FF;--shiki-dark:#569CD6">(NO_USING_NAMESPACE_VCL_FLEXCEL)</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">using</span><span style="color:#0000FF;--shiki-dark:#569CD6"> namespace</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> Vcl</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#267F99;--shiki-dark:#4EC9B0">Flexcel</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> !</span><span style="color:#AF00DB;--shiki-dark:#C586C0">defined</span><span style="color:#0000FF;--shiki-dark:#569CD6">(DELPHIHEADER_NO_IMPLICIT_NAMESPACE_USE) </span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x26;&#x26;</span><span style="color:#000000;--shiki-dark:#D4D4D4"> !</span><span style="color:#AF00DB;--shiki-dark:#C586C0">defined</span><span style="color:#0000FF;--shiki-dark:#569CD6">(NO_USING_NAMESPACE_VCL)</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">using</span><span style="color:#0000FF;--shiki-dark:#569CD6"> namespace</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> Vcl</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"></span></code></pre>

Note that we can fool C++ Builder into not using the namespaces with some {$HPPEMIT} magic, but if you #include other "Vcl.Something" unit, like, for example,`#include <Vcl.Forms> the Vcl namespace will be used, and there is no way to "unuse" a namespace in C++.

Now, with the "Vcl" namespace used, we will get an ambiguous namespace if we write `FlexCel::Core::TExcelFile` since the namespace could be `::Vcl::Flexcel::Core` or just `::Flexcel::Core` and the compiler can't tell which is which. While this can be easily solved when writing a header manually by adding "::" at the start (`::Flexcel::Core::TExcelFile`), the headers autogenerated from Delphi files don't have those starting "::" and will cause a compiler error.

This is why all the units now start with "FlexCel" (FlexCel.VCLSupport instead of VCL.FlexCel.Core). So they all are in the "Flexcel" namespace, which we control, unlike the "Vcl" namespace, which we don't. The only way to make this work was to rename the units to something starting with FlexCel.

### Redundant functionality

When we introduced the unit `FlexCel.Core` in FlexCel 6.6, it declared the same classes as `Vcl::FlexCel::Core`, but inside a different namespace. This was the only way to keep compatibility with older code, but it caused the same type to be inside two different namespaces. We now had `Vcl::Flexcel::Core::TExcelFile` and `Flexcel::Core::TExcelFile'. With all the automatic "using namespace" added by C++ Builder, those classes were likely to be ambiguous and cause compiler errors.

This is why the new "FlexCel.VCLSupport" classes only declare the types needed for VCL support, but not all the types in `VCL.FlexCel.Core`. And this is why you now need to use both "FlexCel.Core" and "FlexCel.VCLSupport". With our former approach, using "Vcl.FlexCel.Core" would be all needed: It would initialize the VCL graphics engine and make all the types available to your app. Now FlexCel.VCLSupport will only initialize the VCL graphics engine, and you still need to use "FlexCel.Core" to access all the FlexCel core types.

## Conclusion

We had to rethink everything to adapt to the new way C++ Builder started generating the headers. We had to deprecate the old "Platform.FlexCel.Core" units and introduce "FlexCel.PlatformSupport" units instead. If we had more control over how headers are generated we could have tried a different approach, but we have very little control and we can't really change the autogenerated headers. So the only option left for us was to change the units.

If you have old code and are not using C++ Builder, you can keep using the old "Platform.FlexCel.Core" units, we have no plans to drop them, and they will keep working. But for the new code, we recommend you switch to the new "FlexCel.PlatformSupport" units, which are the way forward. We've updated APIMate, all our documentation, and examples to use them.
