Download Link: https://assignmentchef.com/product/solved-cse021-lab12-2d-arrays-and-file-output
<br>
This week we will read more than one file as input, and also create an output file. More specifically, we will take in two matrices and multiply them. The result will then be written to a file. Most of the code and logic you need to finish this lab is presented in lecture this week, and also included in this lab assignment. Your job is to combine each portion to do the job correctly.




<strong>Before you get started</strong>, read chapters 5.7 and 5.9. Answer the assessment questions as you encounter them in the next section. The prompts for answering assessment questions are placed immediately following the material to which the listed questions relate.

<h1>Getting Started</h1>

After following the import instructions in the assignment page, you should have a Java project in Eclipse titled Lab 21_12. This PDF document is included in the project in the <strong>doc</strong> directory. The Java files you will use in this lab are in the <strong>src/matrix</strong> directory.

<h1>Part 1: Multiplying Matrices</h1>

The file format we will use has 2 types of information. The first is the dimensions of the array. The second is the actual values inside the array. In order to encode this information, we create a structured format that is easy to understand.




The first line will contain 2 numbers. The first is the # of rows and the second is the # of columns. Then each row of values will be printed in corresponding columns in a tab-delimited manner.




<table width="122">

 <tbody>

  <tr>

   <td width="122">


    <table width="107">

     <tbody>

      <tr>

       <td width="32">1</td>

       <td width="5"> </td>

       <td width="32">2</td>

       <td width="5"> </td>

       <td width="32">3</td>

      </tr>

      <tr>

       <td width="32">3</td>

       <td width="5"> </td>

       <td width="32">2</td>

       <td width="5"> </td>

       <td width="32">1</td>

      </tr>

      <tr>

       <td width="32">1</td>

       <td width="5"> </td>

       <td width="32">3</td>

       <td width="5"> </td>

       <td width="32">2</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>




The 3×3 matrix shown above would be translated to the following file:




3      3

1      2     3

3      2     1

1      3     2




We will introduce is the new keyword null which means an ‘empty’ object to which a pointer can point. We can also check if a pointer is valid by checking it against the object, null.




<h2>Task 1: Analyze code</h2>

Analyze the following code and answer the assessment questions that follow:




1 public static int[][] proc(String filename) {

2

<ul>

 <li>int[][] arr = null;</li>

 <li>try {</li>

 <li>Scanner sc = new Scanner(new FileReader(filename));</li>

 <li>int row = sc.nextInt();</li>

 <li>int column = sc.nextInt();</li>

 <li>arr = new int[row][column];</li>

</ul>

9

<ul>

 <li>for (int i = 0; i &lt; row; i++) {</li>

 <li>for (int j = 0; j &lt; column; j++) {</li>

 <li>arr[i][j] = sc.nextInt();</li>

 <li>}</li>

 <li>}</li>

 <li>close();</li>

 <li>} catch(NoSuchElementException e) {</li>

 <li>out.println(e);</li>

 <li>} catch(FileNotFoundException e) {</li>

 <li>out.println(e);</li>

 <li>}</li>

 <li>return arr;</li>

 <li>}</li>

</ul>




[Answer assessment questions 1a – 1g]




<h2>Task 2: Fill-in readMatrix</h2>

Fill in the code to read in the values from the file whose name is specified by the given string parameter inside the readMatrix method of MatrixMultiply.java [Hint: see Task 1].




<h2>Task 3: Analyze code</h2>

Analyze the following code sample and answer the assessment questions that follow:




String filename = “Result.txt”;

try {

FileWriter output = new FileWriter(filename);   String ostr = “”;   for (int i = 0; i &lt; arr2D.length; i++) {    for (int j = 0; j &lt; arr2D[0].length; j++) {      System.out.print(ostr = (arr2D[i][j] + “t”));

output.write(ostr);

}

System.out.println();    output.write(“r
”); // Carriage return

}

output.close();

} catch(Exception e) {

System.out.println(e);

}




[Answer assessment questions 2a – 2c]




<h2>Task 4: Fill-in writeMatrix</h2>

Fill in the code to write the values after multiplying the two matrices [Hint: See Task 3]. You will have 3 input combinations to test for this lab. Each output should be saved to a different file. They should be named Result1.txt, Result2.txt and Result3.txt.




Result1.txt is matrix1.txt and matrix2.txt multiplied.

Result2.txt is matrix2.txt and matrix3.txt multiplied.

Result3.txt is matrix2.txt and matrix4.txt multiplied.




You may do this by simply renaming the output file the program produces. Or you may modify filenames in code for different runs of the program. Other techniques are also possible.

<strong>Part 2: Fill in Survey </strong>

Please complete the survey in survey.txt provided in the project’s <strong>doc</strong> directory.

<strong> </strong>

<h1>Part 3: (Assessment) Logic Check and Level of Understanding</h1>

Create a Word document or text file named Part3 that contains answers to the following:

<ul>

 <li>For the proc method shown in Task 1, answer the following:

  <ol>

   <li>What is the return type of the method, proc? What line in the code can you find this information?</li>

   <li>What is line 3 doing? (Answer in terms of variable name, type and initial value)</li>

   <li>Why do we need to use try in line 4?</li>

   <li>What line(s) read in the dimension of the matrix?</li>

   <li>What is line 8 doing?</li>

   <li>Why is there no while-loop in this method, and why we can use a for-loop?</li>

   <li>How many times does line 12 get executed? (Answer in terms of an expression involving # rows and # of columns)</li>

  </ol></li>

 <li>Answer the following questions concerning the code given in Task 3:

  <ol>

   <li>What does length mean?</li>

   <li>What does arr2D[0].length mean?</li>

   <li>What does arr2D[i][j] + “t” create?</li>

  </ol></li>

</ul>