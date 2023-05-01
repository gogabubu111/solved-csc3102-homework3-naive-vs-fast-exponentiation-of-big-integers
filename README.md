Download Link: https://assignmentchef.com/product/solved-csc3102-homework3-naive-vs-fast-exponentiation-of-big-integers
<br>
Setting up your Programming Environment and Tools

Review of the Use of Control Structures

Empirical Analysis of Two Integer Exponentiation Algorithms

Familiarization with the Course Programming Conventions

The purpose of the first programming exercise is to familiarize you with the programming standards and coding conventions that are required for this course. All students taking this course are expected to have a certain level of proficiency which includes the ability to read and understand code written by others. Students are also expected to write code that efficiently implements and tests various algorithms using programming constructs studied in your programming classes and functions whose syntaxes and usage information you can find in ANSI/ISO C<strong><sup>++ </sup></strong>11 language documentation.

In this exercise and all subsequent programming projects, you will be expected to properly document your code using the coding conventions for this course, program in multiple files so that there is a wall between the public interface and implementation of your algorithms as well as the application that uses the implementation. This assignment will test your ability to follow this approach to programming no matter what IDE (integrated development environment) that you use to write your code. Your code will be tested using ANSI/ISO C<strong><sup>++ </sup></strong>11. Your program will be considered acceptable for grading only if it compiles without any syntax errors. You will generally submit only your source code, the .cpp and .h files, in a zip archive file via a drop box on Moodle for grading.

<strong>Definition 1. Empirical algorithmics </strong>is a computer science area of specialization that involves the use of experimental and statistical, rather than theoretical, methods to analyze the behavior of algorithms.

The goals of empirical algorithmics are characterization of an algorithm based on its performance, enhancing the performance of an algorithm using empirical techniques and the comparative analysis of the various algorithms that solve the same problem within a given context.

<strong>Definition 2. </strong>A <strong>power </strong>is an exponent to which a given quantity is raised. The expression <em>x<sup>n </sup></em>is therefore known as “x to the <em>n<sup>th </sup></em>power.” The computation of powers arise in many numerical algorithms.

You will write code to empirically compare the performance of a naive and the <em>fast </em>algorithms for computing powers of positive big integer values where the exponent is a non-negative integer. Here is the pseudocode for a naive power algorithm,

<h2>Listing 1: Naive Power Algorithm</h2>

ALGORITHM: NAIVE-POWER(x,n)

{Input: n – a non-negative integer x – a positive integer Output: <em>x<sup>n</sup></em>

}

if n = 0 or x = 1

return 1

endif

y ← 1

for i ←1 to <em>n </em>stepSize ← 1

y ←<em>y</em>× x

endfor

return y

endAlgorithm

The power of a number can be determined more efficiently using a successive squaring algorithm.

Here is a pseudocode description of the algorithm.

<h2>Listing 2: Fast Power Algorithm</h2>

ALGORITHM: FAST-POWER(x,n)

{Input: n – a non-negative integer x – a positive integer Output: <em>x<sup>n</sup></em>

}

if n = 0 or x = 1 return 1

endif y ← 1

while n &gt; 1

if n mod 2 = 0

n ← n / 2

else

y ← y × x n ← (n – 1) / 2

endif

x ← x × x

endwhile

return y × x endAlgorithm

I have provided <em>BigInt.h </em>a header file that contains prototypes for functions of a “Big Integer” library. I have also provided <em>BigInt.cpp </em>the implementation file for the header file. These files allow for representing very large integers and performing basic arithmetic operations on them. Do not make any changes to these files.

<h1>The BigMath Header File</h1>

Complete the implementation of <em>BigMath.h </em>so that it contains implementations for the naive and fast exponentiation algorithms.

<h1>The PowerAnalyzer Program</h1>

The PowerAnalyzer.cpp file will consist of only one function, the <em>main</em>. The main function will perform the following tasks:

<ol>

 <li>It prompts the user to enter the base of a power.</li>

 <li>It prompts the user to enter the exponent of a power.</li>

 <li>It computes the powers using both the fast and naive algorithms and displays the powers.</li>

 <li>It randomly generates a four-digit positive integer for the base of a power.</li>

 <li>It randomly generates a two-digit positive integer for the exponent of a power.</li>

 <li>Similarly, it computes the powers using these randomly generated integers and both the fast and naive algorithms and displays the powers.</li>

 <li>It prompts the user for a positive integer to be used as the base in measuring and displaying runtimes for generating various powers of the base.</li>

 <li>For n = {16<em>,</em>32<em>,</em>64<em>,</em>128<em>,</em>256<em>,</em>512<em>,</em>1024<em>,</em>2048<em>,</em>4096<em>,</em>8192}, your program will compute, using the naive and fast exponentiation algorithms, powers of the base entered by the user and measure and display the execution times in nanoseconds for these algorithms as shown in the table in the sample run.</li>

</ol>

.

<h1>Additional Requirements</h1>

Test the program to ensure that it works correctly and generates its output in the same format as shown in the sample run. A <em>Big Integer </em>calculator at <em>http://www.javascripter.net/math/calculators/100digitbigintcalculator.htm </em>can be used to verify that the powers calculated by your program are correct.

Each file should have the following javadocs:

/**

<ul>

 <li>EXPLAIN THE PURPOSE OF THIS FIlE</li>

 <li>CSC 3102 Programming Project # 0</li>

 <li>@author YOUR NAME</li>

 <li>@since DATE THE FILE WAS LAST MODIFIED</li>

 <li>@see A LIST OF FILES THAT IT DIRECTLY REFERENCES*/</li>

</ul>

Also, submit an excel spreadsheet, <em>powertimes.xls</em>, containing the data generated by your program and a line graph of execution times of each algorithm in milliseconds (Y-axis) versus the integer exponent (X-axis). Locate the source files, <em>BigMath.h</em>, <em>BigInt.h</em>, <em>BigInt.cpp </em>and <em>PowerAnalyzer.cpp </em>and enclose them along with the spreadsheet in a zip file. Name the zip file <em>YOURPAWSID proj00.zip</em>, and submit your project for grading using the digital drop box on Moodle.

Sample Run:

Enter the base of the power -&gt; 2

Enter the exponent of the power -&gt; 100

Using Naive Algorithm: 2^100 = 1267650600228229401496703205376

Using Fast Algorithm: 2^100 = 1267650600228229401496703205376

Using a random 4-digit base and a random 2-digit exponent:

Using Naive Algorithm: 6362^24 = …. Using Fast Algorithm: 6362^24 = ….

Enter the base of the powers for the table -&gt; 546879

b = 546879

========================================================= n              b^n: Fast Power(ns) b^n: Naive Power (ns)

———————————————————

<table width="398">

 <tbody>

  <tr>

   <td width="139">16</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">32</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">64</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">128</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">256</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">512</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">1024</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">2048</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">4096</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

  <tr>

   <td width="139">8192</td>

   <td width="174">………….</td>

   <td width="84">…………</td>

  </tr>

 </tbody>

</table>

=========================================================