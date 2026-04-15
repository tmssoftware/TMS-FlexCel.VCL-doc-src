---
uid: UsingTokens
---

# Using Tokens to get information from formulas

## Introduction
When reading formulas with FlexCel, you get a string with the formula definition, like for example:


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>=SQRT(A1^2 + A2^2)</span></span>
<span class="line"><span></span></span></code></pre>


And while this is enough in many cases, sometimes you need a little more information. For example, which are the cells used in the formula above? It is challenging to know that the cells used are A1 and A2 just by looking at the string. You could try to use some kind of regex to get the information, but you will hit limits soon. Formula syntax depends on the context, and depending on its surroundings, the string "A1" might be present in the formula and not mean a cell.

To solve this problem correctly, we need to parse the string. And guess what? FlexCel already has one parser which you can use. To print out the cells used in the formula above, you can use the following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  tokens: ITokenList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  token: TToken;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Set up a file to analyze.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'A2'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=SQRT(A1^2 + A2^2)'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Print the cell addresses in the formula.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    tokens := xls.GetFormulaTokens(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> token </span><span style="color:#0000FF;--shiki-dark:#569CD6">in</span><span style="color:#000000;--shiki-dark:#D4D4D4"> tokens </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (token </span><span style="color:#0000FF;--shiki-dark:#569CD6">is</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TTokenCellAddress) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        WriteLn(TTokenCellAddress(token).Address.CellRef);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


> [!Note]
> 
> In the example above, we set cell A2 to the formula and then use [TExcelFile.GetFormulaTokens](~/api/FlexCel.Core/TExcelFile/GetFormulaTokens.md) to read the tokens. This was done to simulate a real-world situation where we already have the formulas in an existing file, and we want to parse them. But for this particular example, instead of setting the value of a cell and then reading the tokens from the cell, we could have used [TExcelFile.GetTokens](~/api/FlexCel.Core/TExcelFile/GetTokens.md) to get the tokens directly from the string.


## Analyzing formulas in a file

[TExcelFile.GetFormulaTokens](~/api/FlexCel.Core/TExcelFile/GetFormulaTokens.md) returns an array with the tokens that make up the formula, using [RPN Notation](https://en.wikipedia.org/wiki/Reverse_Polish_notation)

RPN is straightforward to evaluate mechanically. When you have a data token, you push it into the stack. When the token is an operator or function taking n parameters, you combine the n last members of the stack and replace them by the result.
So let's see in more detail the tokens in the formula above. This is the full list of tokens returned by GetFormulaTokens:

* TTokenCellAddress - **A1**
* TTokenData - **2**
* TTokenOperator - **Power**
* TTokenWhitespace - the is the space before the "+". We will ignore whitespace
* TTokenCellAddress - **A2**
* TTokenData - **2**
* TTokenOperator - **Power**
* TTokenWhitespace
* TTokenOperator - **Add**
* TTokenFunction - **SQRT**

Using RPN, this is evaluated as follows:

1. Push A1 into the stack
2. Push 2 into the stack
3. Calculate A1^2 - Now the stack contains only A1^2
4. Push A2 into the stack
5. Push 2 into the stack
6. Calculate A2^2 - Now the stack contains A1^2 and A2^2
7. Add both entries in the stack. Now the stack contains A1^2 + A2^2
8. Calculate SQRT of the entries in the stack. The result is SQRT(A1^2 + A2^2)

You can visualize the stack after each step above in the following diagram:

<img alt = "rpn tokens" src = "../images/rpn-tokens.svg" width = "998" height = "384"/>

## Manipulating formulas in a file

Up to now, we've seen how to analyze existing formulas. This enough can be very powerful, and allows you to create custom static analyzers that can detect unwanted constructs in spreadsheets. But do you know a nice feature that most good static analyzers have? They allow you to apply fixes to your code automatically.

So let's imagine we have a file with thousands of formulas, and in cell B1 we have a constant which contains the tax to apply. We want to check all the formulas for references to B1, and make sure they reference a name "Tax" instead. We have half of the solution already: [TExcelFile.GetFormulaTokens](~/api/FlexCel.Core/TExcelFile/GetFormulaTokens.md). This method will allow us to detect all references to B1 in the formulas. But now, to actually modify the code, we need the other half: [TExcelFile.SetFormulaTokens](~/api/FlexCel.Core/TExcelFile/SetFormulaTokens.md) 

We can now read the tokens of a formula, modify them, and write them back. The following code will replace all occurrences of B1 by the name "Tax":

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  tokens: ITokenList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  modified: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Set up a file to analyze.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2021, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'A2'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=B1 * C2'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetNamedRange(TXlsNamedRange.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Tax'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Modify all references to B1 to be references to the name "Tax"</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    tokens := xls.GetFormulaTokens(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    modified := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> tokens.Count - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (tokens[i] </span><span style="color:#0000FF;--shiki-dark:#569CD6">is</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TTokenCellAddress)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                      and (TTokenCellAddress(tokens[i]).Address.Row = </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                      and (TTokenCellAddress(tokens[i]).Address.Col = </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        tokens[i] := TTokenName.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Tax'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        modified := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> modified </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.SetFormulaTokens(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, tokens);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

