Download Link: https://assignmentchef.com/product/solved-cs220-lab10-the-jack-compiler-1
<br>
Name:<u>                                                 </u> Date: <u>                                              </u>




Syntax Analysis

<table>

 <tbody>

  <tr>

   <td width="0"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>




<strong><u>Tokenizer Questions:</u></strong>

<ol>

 <li>Translate the following Jack code into its tokenized XML code.</li>

</ol>

<table width="688">

 <tbody>

  <tr>

   <td width="372"><strong>Jack Code</strong></td>

   <td width="316"><strong>Tokenized XML</strong></td>

  </tr>

  <tr>

   <td width="372"><strong>How many tokens are generated?</strong></td>

   <td width="316"><strong> </strong></td>

  </tr>

  <tr>

   <td width="372">var int x;let x = 3; </td>

   <td width="316">            </td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>Translate the following Jack code into its tokenized XML code.</li>

</ol>

<table width="688">

 <tbody>

  <tr>

   <td width="372"><strong>Jack Code</strong></td>

   <td width="316"><strong>Tokenized XML</strong></td>

  </tr>

  <tr>

   <td width="372"><strong>How many tokens are generated?</strong></td>

   <td width="316"><strong> </strong></td>

  </tr>

  <tr>

   <td width="372">var int value;if (y &gt; x){let value = x &amp; y;} </td>

   <td width="316">            </td>

  </tr>

 </tbody>

</table>

<ol start="3">

 <li>How many tokens will be produced by the following Jack code? <u>Do not</u> translate into XML, just count tokens.</li>

</ol>

<table width="688">

 <tbody>

  <tr>

   <td width="372"><strong>Jack Code</strong></td>

   <td rowspan="2" width="316"><strong>Answer = </strong></td>

  </tr>

  <tr>

   <td width="372"><strong>How many tokens are generated?</strong></td>

  </tr>

  <tr>

   <td width="372">var int x, y, greatest;let x = 3;let y = 5;if (x &gt; y){let greatest = x;}else{let greatest = y;}do Output.printInt(greatest);do Output.println();</td>

   <td width="316"> </td>

  </tr>

 </tbody>

</table>

<strong><u> </u></strong>

<strong><u>Syntax Analyzer Questions:</u></strong>

<ol>

 <li>Translate the following Jack code into its XML parse tree (using the Jack grammar).</li>

</ol>

<table width="688">

 <tbody>

  <tr>

   <td width="372"><strong>Jack Code</strong></td>

   <td width="316"><strong>XML Parse Tree</strong></td>

  </tr>

  <tr>

   <td width="372">let greatest = “x is greater”; </td>

   <td width="316">            </td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>Translate the following Jack code into its XML parse tree (using the Jack grammar).</li>

</ol>

<table width="688">

 <tbody>

  <tr>

   <td width="372"><strong>Jack Code</strong></td>

   <td width="316"><strong>XML Parse Tree</strong></td>

  </tr>

  <tr>

   <td width="372">do Output.printInt(greatest); </td>

   <td width="316">            </td>

  </tr>

 </tbody>

</table>

























<ol start="3">

 <li>Translate the following Jack code into its XML parse tree (using the Jack grammar).</li>

</ol>

<table width="688">

 <tbody>

  <tr>

   <td width="372"><strong>Jack Code</strong></td>

   <td width="316"><strong>XML Parse Tree</strong></td>

  </tr>

  <tr>

   <td width="372">class Point{field int x, y; constructor Point new(){let x = 0;let y = 0;}} </td>

   <td width="316">            </td>

  </tr>

 </tbody>

</table>




Summative Questions:




<ul>

 <li>Consider the following statements, taken from three different Jack programs. In each one of these programs, the identifier foo represents a different thing:</li>

</ul>




let x = 5 + foo – a       // Here foo represents a simple variable.

let y = foo[12] – 3       // Here foo represents an array.

let z = 2 * foo.val()     // Here foo represents an object.




Suppose that we are parsing any one of these statements (we don’t know which), and that

the current token is foo. How many more tokens do we have to read until we can tell

what we have is a simple variable, an array reference, or a method call?




<ol>

 <li>Zero</li>

 <li>One</li>

 <li>Two</li>

 <li>Three</li>

 <li>All answers are wrong</li>

</ol>




<ul>

 <li>Consider the following rule, taken from the Jack grammar:</li>

</ul>

parameterList: ( ( type varName ) ( ‘,’ type varName ) * ) ?




Select the correct statement(s):

<ol>

 <li>The rule will parse successfully an empty parameter list</li>

 <li>The symbol * (in this context) is part of the Jack language</li>

 <li>The symbol * means 0 or 1</li>

 <li>The symbol * means 0 or more</li>

 <li>The symbol ? means 0 or 1</li>

 <li>The symbol ? means 0 or more</li>

 <li>The rule will parse successfully the parameter list (int x int y)</li>

 <li>The rule will parse successfully the parameter list (int x, int y)</li>

</ol>




<ul>

 <li>XML code is structured as a:

  <ol>

   <li>Stack</li>

   <li>Graph</li>

   <li>Tree</li>

   <li>Multi-dimensional array</li>

  </ol></li>

</ul>




<strong><u>Programming Exercise:</u></strong>




Using Java, complete the JackTokenizer class (JackTokenizer.java, part of the overall compiler) and implement the following enums (TokenType, Kind and Keyword).  You may use the following API design to help guide your work, or choose to implement your own design.

<table>

 <tbody>

  <tr>

   <td width="0"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>




















































Following is an explanation of each of the methods in the JackTokenizer class.  Please note the methods <strong>keyword(), intVal(), stringVal(), symbol(), tokenType()</strong> are really accessor (getter) methods, thus they have been renamed to <strong>getKeyword(), getIntVal(), getStringVal(), getSymbol() and getTokenType()</strong> accordingly in the class diagram above.

The main method of the JackTokenizer should prompt the user to enter the name of a Jack file (e.g. SquareDance.jack), then the program will produce an XML output file of all the tokens in the file with the extension xxxT.xml (e.g. SquareDanceT.xml).

You can use the TextComparer.bat (or .sh) supplied with the nand2tetris software to test your output against the solution (attached to this lab assignment on Canvas).







Here’s a sample input/output of the Jack Tokenizer:




Here’s the provided API for the Jack Tokenizer (also on Helper Sheet):




When you’re finished, please upload a single Word document (or PDF) containing the following in order on Canvas:

<ol>

 <li>The .xml files from your 2 sample programs (SquareDanceT.xml and ArrayMain.xml)</li>

 <li>The source code of your JackTokenizer</li>

 <li>The source code of each of your enums (TokenType, Kind and Keyword)</li>

</ol>