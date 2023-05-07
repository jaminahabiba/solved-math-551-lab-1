Download Link: https://assignmentchef.com/product/solved-math-551-lab-1
<br>
<strong>Goals: </strong>To learn and practice different forms of matrix input and basic operations with matrices in Matlab. The matrix operations to be studied include matrix addition and subtraction, scalar product, matrix product and elementwise matrix product in Matlab, matrix concatenation, and selecting submatrices.

<strong>To get started: </strong>Create a new Matlab script file and save it as “lab01.m”.

<strong>Matlab commands to practice: </strong>length, linspace, size, max, min, mean, sum, randi (rand), *, .*, eye, zeros, ones, diag, spdiags.

<strong>What you have to submit: </strong>The file lab01.m, which you will create during the lab session.

<h1>Reminders About the Grading Software</h1>

Remember, the labs are graded with the help of software tools. If you do not follow the instructions, you will lose points. If the instructions ask you to assign a value to a variable, you must <strong>use the variable name given in the instructions</strong>. If the instructions ask you to make a variable named x1 and instead you make a variable named x or X or X1 or any name other than x1, the grading software will not find your variable and you <em>will </em>lose points. Required variables are listed in the lab instructions in a gray box like this:

Variables: x1, A, q

At times you will also be asked to answer questions in a comment in your M-file. You must <strong>format your text answers correctly</strong>. Questions that you must answer are shown in gray boxes in the lab. For example, if you see the instruction

Q7: What does the Matlab command lu do? your file must contain a line similar to the following somewhere

% Q7: It computes the LU decomposition of a matrix.

The important points about the formatting are

<ul>

 <li>The answer is on a single line.</li>

 <li>The first characters on the line is the comment character %.</li>

 <li>The answer is labeled in the form Q<em>n</em>:, where <em>n </em>stands for the question number from the gray box.</li>

</ul>

If you do not format your answers correctly, the grading software will not find them and you <em>will </em>lose points.

<h1>INTRODUCTION</h1>

It is assumed that the readers are familiar with basic matrix operations and their properties, so the definitions and facts here are given mostly for the sake of a review.

We can think of a matrix as a table of numbers:

<table width="253">

 <tbody>

  <tr>

   <td rowspan="2" width="80"> <em>a</em>11 <em>a</em> 21 <sup> </sup>···<strong>A </strong>=  <em>a</em><em>i</em>1 ··· <em>a</em><em>m</em>1</td>

   <td rowspan="2" width="36"><em>a</em>12 <em>a</em>22 ··· <em>a</em><em>i</em>2···<em>a</em><em>m</em>2</td>

   <td rowspan="2" width="31"><em>…</em><em>…</em>…<em>…</em>··· <em>…</em></td>

   <td rowspan="2" width="35"><em>a</em>1<em>j </em><em>a</em>2<em>j </em>··· <em>a</em><em>ij</em>···<em>a</em><em>mj</em></td>

   <td rowspan="2" width="31"><em>…</em><em>…</em>··· <em>…</em>…<em>…</em></td>

   <td width="30"><em>a</em>1<em>n </em><em>a</em>2<em>n </em>··· <em>a</em><em>in</em>···</td>

   <td width="9"></td>

  </tr>

  <tr>

   <td colspan="2" width="39"><em>a</em><em>mn</em></td>

  </tr>

 </tbody>

</table>

The matrix <strong>A </strong>above contains <em>m </em>rows and <em>n </em>columns. We will say that <strong>A </strong>is an <em>m</em>×<em>n </em>(<em>m</em>-by-<em>n</em>) matrix, and call <em>m</em>, <em>n </em>the dimensions of the matrix <em>A</em>. The matrix <em>A </em>above can also be compactly written as <strong>A </strong>= (<em>a<sub>ij</sub></em>), where <em>a<sub>ij </sub></em>is called (<em>i,j</em>) element of the matrix <strong>A</strong>.

Matlab (originally named “MATrix LABoratory”) has an extensive list of functions which work with matrices. The operations discussed in this project consist of matrix addition/subtraction, multiplication of a matrix by a constant (scalar multiplication), transposition of a matrix, selecting submatrices, and concatenating several smaller matrices into a larger one, matrix multiplication and componentwise matrix multiplication, and operations of finding maximal/minimal element in the matrix, and finding the sum/mean in the row/column of the matrix.

<em>Scalar multiplication </em>of a matrix <strong>A </strong>by a constant <em>c </em>consists of multiplying every element of the matrix by this constant: <em>c</em><strong>A </strong>= (<em>ca<sub>ij</sub></em>)<em>.</em>

<em>Matrix addition and subtraction </em>are possible if the matrices have the same dimensions and is done componentwise:

<strong>A </strong>± <strong>B </strong>= (<em>a<sub>ij </sub></em>± <em>b<sub>ij</sub></em>)<em>.</em>

If <em>n </em>is a positive integer then the <em>n </em>× <em>n identity matrix</em>, denoted by <strong>I</strong><em><sub>n</sub></em>, has 1 in every diagonal entry (<em>i,i</em>) for 1 ≤ <em>i </em>≤ <em>n</em>, and 0 in every other entry. There is one identity matrix for every dimension <em>n</em>. For instance,

<h1>I   I</h1>

are the 2 × 2 and 3 × 3 identity matrices.

The identity matrices are special examples of <em>diagonal matrices</em>. A matrix <strong>A </strong>is diagonal if <em>A</em>(<em>i,j</em>) is 0 whenever <em>i </em>6= <em>j </em>(it is not required that <em>a<sub>ii </sub></em>6= 0 for any <em>i</em>).

A <em>matrix product </em><strong>C </strong>= <strong>AB </strong>of an <em>m </em>× <em>n </em>matrix <strong>A </strong>and an <em>l </em>× <em>p </em>matrix <strong>B </strong>exists if and only if <em>n </em>= <em>l</em>. If this condition is satisfied, then <strong>C </strong>is an <em>m </em>× <em>p </em>matrix with the elements

<em>n</em>

<em>c</em><em>ij </em>= X<em>a</em><em>ikb</em><em>kj.</em>

<em>k</em>=1

Observe that matrix multiplication is non-commutative, <strong>AB </strong>6= <strong>BA</strong>.

For example if <strong>A </strong> and <strong>B </strong> then the product is given by

<strong>AB </strong><em> .</em>

If <strong>C </strong> and <strong>D </strong> then the product <em>CD </em>is not defined because the number of columns of

<strong>C </strong>does not equal the number of rows of <strong>D</strong>.

Please, perform the tasks below.

<h1>TASKS</h1>

<ol>

 <li>Open the “lab01.m” Matlab script you have created and type in the following commands:</li>

</ol>

%% basic operations with matrices

A=[1 2 -10 4; 3 4 5 -6; 3 3 -2 5];

B=[3 3 4 2];

This will create a new cell and define two new variables A and B. The variable A stores a 3 × 4 matrix, while the variable B contains a 1 × 4 row vector. Use the Workspace window to look at the variables A and B.

Variables: A, B

<ol start="2">

 <li>Type in the following commands:</li>

</ol>

lengthA = length(A) lengthB = length(B)

<table width="273">

 <tbody>

  <tr>

   <td width="177">Variables: lengthA, lengthB</td>

   <td width="96"> </td>

  </tr>

  <tr>

   <td colspan="2" width="273">Q1: What does the command length(A) do?</td>

  </tr>

 </tbody>

</table>

<ol start="3">

 <li>Add the vector B as the fourth row of the matrix A and save the result as a new matrix C using the following code:</li>

</ol>

C=[A; B]; Variables: C

<ol start="4">

 <li>Create a new matrix D whose entries are located in the rows 2<em>,</em>3<em>,</em>4 and columns 3<em>,</em>4 of the matrix C:</li>

</ol>

D=C(2:4,3:4);

Variables: D

<ol start="5">

 <li>Matlab allows to create equally spaced vectors which can be useful in many situations. For instance, run the following code:</li>

</ol>

EqualSpaced=0:pi/10:2*pi

EqualSpaced1=linspace(0,2*pi,21)

Take a look at the output produced by Matlab. Observe that both of these commands created the vector with equally spaced entries ranging from 0 to 2<em>π </em>and the distances between the elements equal to <em>π/</em>10.

Variables: EqualSpaced, EqualSpaced1

<ol start="6">

 <li>Create a new cell and find the maximal and minimal elements in each of the columns of the matrix A. Store the result respectively in row vectors named maxcolA and mincolA. You can use Matlab max and min functions:</li>

</ol>

%% Max, min, sum and mean maxcolA=max(A) mincolA=min(A)

Variables: maxcolA and mincolA

<ol start="7">

 <li>Now repeat the previous step but find maximal and minimal elements in each row of the matrix A. One way is to use max and min with an additional argument 2 to show that you are interested in the maximum and minimum along the second dimension (i.e. max(A,[],2)). Save the results as maxrowA and minrowA. Finally find the maximal and minimal elements in the whole matrix A. One way to do this is to find the maximal (or minimal) element in the maximal (or minimal) elements of each column of A (e.g. max(maxcolA) or max(max(A))). Save the results as maxA and minA. Variables: maxrowA, minrowA, maxA, minA</li>

 <li>Repeat the last two steps using the commands mean and sum instead of max and min. Type help mean and help sum in the command line to learn more about mean and sum, respectively. You should create six new variables, corresponding to the column/row mean/sum, and mean/sum of the elements of the entire matrix.</li>

</ol>

<table width="383">

 <tbody>

  <tr>

   <td colspan="2" width="383">Variables: meancolA, meanrowA, sumcolA, sumrowA, meanA, sumA</td>

  </tr>

  <tr>

   <td width="283">Q2: What do the commands mean and sum do?</td>

   <td width="101"> </td>

  </tr>

 </tbody>

</table>

<ol start="9">

 <li>Create a new cell and use the command randi([-4 4],5,3) to create two matrices F and G with 5 rows and 3 columns and random integer entries from −4 to 4:</li>

</ol>

%% Matrix addition/subtraction, and multiplication

F=randi([-4 4],5,3)

G=randi([-4 4],5,3)

Variables: F, G

<ol start="10">

 <li>Perform the operations 4*F, F+G, F-G, F.*G, storing the results in ScMultF, SumFG, DiffFG, and ElProdFG respectively.</li>

</ol>

<table width="276">

 <tbody>

  <tr>

   <td colspan="2" width="276">Variables: ScMultF, SumFG, DiffFG, ElProdFG</td>

  </tr>

  <tr>

   <td width="230">Q3: What does the last operation do?</td>

   <td width="47"> </td>

  </tr>

 </tbody>

</table>

<ol start="11">

 <li>Check the size of F and the size of A, storing the results in sizeF and sizeA, respectively.</li>

</ol>

<table width="282">

 <tbody>

  <tr>

   <td width="149">Variables: sizeF, sizeA</td>

   <td width="133"> </td>

  </tr>

  <tr>

   <td colspan="2" width="282">Q4: Can we matrix-multiply F and A? Explain.</td>

  </tr>

 </tbody>

</table>

<ol start="12">

 <li>Compute <em>H </em>= <em>F </em>∗ <em>A</em>.</li>

</ol>

<table width="214">

 <tbody>

  <tr>

   <td width="78">Variables: H</td>

   <td width="137"> </td>

  </tr>

  <tr>

   <td colspan="2" width="214">Q5: What are the dimensions of H?</td>

  </tr>

 </tbody>

</table>

<ol start="13">

 <li>Generate the identity matrix eye33 with 3 rows and 3 columns using the Matlab eye Variables: eye33</li>

 <li>Run the commands:</li>

</ol>

zeros53=zeros(5,3); ones42=ones(4,2);

<table width="288">

 <tbody>

  <tr>

   <td width="170">Variables: zeros53, ones42</td>

   <td width="119"> </td>

  </tr>

  <tr>

   <td colspan="2" width="288">Q6: What do the functions zeros and ones do?</td>

  </tr>

 </tbody>

</table>

<ol start="15">

 <li>Generate the diagonal 3 × 3 matrix <em>S </em>with the diagonal elements {1<em>,</em>2<em>,</em>7} using the Matlab diag To learn about diag type help diag in the command line. Variables: S</li>

 <li>Now let us do the opposite: extract the diagonal elements from the matrix and save them in the separate vector. The same function diag accomplishes that as well:</li>

</ol>

R=rand(6,6) diagR=diag(R)

This creates a matrix R with random entries from the interval (0<em>,</em>1), extracts the diagonal entries from it, and saves them in the vector diagR. Observe that the function diag has other interesting possibilities (use help diag). Variables: R,diagR

<ol start="17">

 <li>Another function which allows to create diagonal matrices is spdiags. Technically, this function creates a <em>sparse </em>matrix (a matrix with a large number of zeros). These matrices are stored in a special form in Matlab (only non-zero elements are stored), and operations with them are also done in a special way. To convert sparse form of the matrix to the regular one, the command full can be used. Run the following code:</li>

</ol>

diag121=spdiags([-ones(10,1) 2*ones(10,1) -ones(10,1)],[-1 0 1],10,10); full(diag121)

<table width="179">

 <tbody>

  <tr>

   <td width="120">Variables: diag121</td>

   <td width="59"> </td>

  </tr>

  <tr>

   <td colspan="2" width="179">Q7: What does this code do?</td>

  </tr>

 </tbody>

</table>


