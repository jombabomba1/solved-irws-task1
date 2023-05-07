Download Link: https://assignmentchef.com/product/solved-irws-task1
<br>
<ul>

 <li>This is a group project. <strong>TWO</strong> members per group.</li>

 <li>There are two tasks to be achieved in this assignment. Solve them both.</li>

 <li>You should submit an archive (zip) containing all your code together with a README.txt. DO NOT submit a project folder from an IDE such as eclipse!</li>

 <li>Your README.txt should describe how to compile and execute each of your programs (two separate files one for each of the two tasks).</li>

 <li>All of your programs should be console applications, WITHOUT any user interface. Make sure that your code compiles on any machine (if you use a language or languages that need to compiled).</li>

 <li>Your applications will be tested on a windows system, with NO internet connection, only using command prompt.</li>

 <li>Your applications or scripts must not use fixed paths i.e. it should run from my system without any changes.</li>

 <li>If I have to edit it to get it to work, then your script/application is incomplete.</li>

 <li>Accepted languages are python and node.js. You cannot use R</li>

 <li>You should submit a <strong>video presentation</strong> for each of the tasks, both members should present and demonstrate how the systems works.</li>

</ul>

<h1>Task 1 (50 %)</h1>

In this task you are required to write a series of scripts to be able to return the proximity of a query, the following milestones should be achieved in order:

Preprocessing:

Write a script or a program that reads a text file, pre-processes it and saves the results into a new file. The text file contains documents, one document per line. Each document is one or several sentences.

Your program should take three parameters: input file name, output file name and stopword list. It should pre-process documents so that they can be later used to create an inverted index. Basic pre-processing should consider:

<ul>

 <li>Punctuation o Tokenization</li>

 <li>lower-casing/upper-casing / punctuation / numbers</li>

 <li>stop word removal (sample list will be provided, comma separated list of words) o stemming must use one of the Porter stemmer libraries you can find here: <a href="https://tartarus.org/martin/PorterStemmer/index.html">https://tartarus.org/martin/PorterStemmer/index.html</a> the library must be used or you can write your own as long as it gets the same result. the page also has a link to a sample vocab and output to test your algorithms.</li>

</ul>

Your program should write the pre-processed documents into the output file.

<strong>sample input file: </strong>

D1 This is a sample document

D2 This is a second document. This one has more sentences.

D3 The name of the document is spaced by a TAB character! all docs are on a single line <strong>sample output file </strong>

D1 sample document

D2 second document more sentence

D3 name document space tab character doc single line




<h2>Inverted index</h2>

Write a script or a program that reads a text file of documents (you can assume these are preprocessed already in previous milestone), creates an inverted index and saves to file.

Your program should take two parameters: input file name and output file name.

Input file is made of documents, each document will have an Identifier/Title separated from the content by a TAB character.

Each line of the output file should contain the term and title of documents that the term occurs in. Each column must be separated by a TAB character. The output file <strong>must</strong> be created in the same location as the input file.

sample RUN: script2 &lt;infile&gt; &lt;outfile&gt; <strong>sample input file: </strong>

D1 sample document D2 second sample document <strong>sample output file: </strong>sample D1 D2 document D1 D2

second D2




<h2>TF-IDF</h2>

Write a script or a program that reads a text file containing an inverted index, creates the TF-IDF weights matrix and saves it in a file.

Your program should take two parameters: input file name out file name.

Input file can be assumed to be a representation of an inverted index where each line contains the term and identifiers of documents where that term occurs in (milestone 2).

Your output file should contain the weights matrix, document identifiers as the header of each column and terms as the first column.

<strong>sample in file: (columns will be TAB delimited) </strong>

sample                  D1          D2 document     D1          D2

second                  D2

<strong>sample out file (columns must be TAB delimited) </strong>

D1           D2 sample           0  0 document        0             0 second              0  0.301

you MUST round to three decimal places as soon as the calculation is made




<h2>Cosine similarity</h2>

Write a script or a program that reads a text file containing a TF-IDF weights matrix defined in milestone 3, and two additional parameters that are documents’ identifiers. Your program should return the cosine similarity value of those two documents.

sample command to run: script weightfile D1 D2 sample output: 0.6




<h2>IR System</h2>

Write a script or program that launches from the command line and takes in two arguments. Argument 1 is an input file that contains documents, 1 per line with an identifier separated by a TAB character. Each document may be one or more sentences.

Argument 2 is a query




sample launch: script corpus.txt “Sample second”




Your output should be the ordered list of documents that matches the query with the score, example output would be

D2          0.9

D1          0.4




<h1>Task 2</h1>

You are required to write an application/program or script that will generate a fused results set from a set of historic results using the Probfuse fusion method.

<ol>

 <li>Ask the user for a set of historical results in csv format where each result set Starts with the IR engine Letter and the Query Number. So A2, means this is from IR engine A and is the second query . see below.</li>

 <li>Ask the user for input : how many segments to use</li>

 <li>Ask the user for the name of the live results file. In CSV format with each IR engine identified as the first entry (see below)</li>

 <li>Ask the user to state what results they want fused out of A, B, C or D</li>

 <li>Output the fused set of results to a file (user should not be asked for an output file name)</li>

</ol>




<strong>Historical data file: </strong>

<ul>

 <li>Each line is a new result set</li>

 <li>Each line starts with the name of the IR engine (A, B , C or D) and the number of the query (1, 2, 3) and is separated from the result set by a comma (,)</li>

 <li>Each result set contains R for a relevant result and N for a non-relevant result. There are no unknown results, this is a FULLY JUDGED CORPUS.</li>

 <li>Each result is separated from the next by a comma (,) Each line ends in a CR and a LF character to indicate end of line</li>

</ul>

<strong>Live Results file: </strong>

<ul>

 <li>The live results file is a CSV file</li>

 <li>Each line contains one set of live results</li>

 <li>Each line starts with the IR Engine name (A. B , C or D) , the name is separated for the result set by a comma (,)</li>

 <li>The result set consists of a set of document numbers (integer values only) separated by a comma (,)</li>

 <li>Each line ends with a CR and a LF character to indicate the end of a line</li>

</ul>