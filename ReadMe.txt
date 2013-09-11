Contributor: Renchen Sun

What is it?
--------------------
This is a shell script which facilitates auto-testing.

How to use it?
---------------------
./runSuite suite-file program

Note: 

The argument suite-file is the name of a file containing a list of filename stems (more details below), and the argument program is the name of the program to be run.

In summary, the runSuite would look at the content of the new-line-spearated suite-file	and run the program by using the contents of files as input of the program. It would report any test whose output does not match the expected output.

The suite-file contains a list of stems, from which we construct the names of files containing the input and expected output of each test. For example, suppose my suite file is:
		test1
		test2
		test3

The test is composed by three small tests which are test1, 2, 3. Firstly, the runSuite will search test1.in in its current directory and use its contents as input of the prorgam. The result would be compared with the contents of test1.out. If they are different, some information would be displayed on the screen. Secondly, it would search test2.in in its current directory...Thirdly, it would search test3.in in its current directory. If any of those finles do not exist or cannot be read, some information would be printed as well. 

Here is the samle run: 
./runSuite suite.txt myprogram
The script will then run ./myprogram three times, once for each test specified in suite.txt.

Output format:

If the output of a gieven test case differs from the expected output, the following message will be printed out.

Test failed:
Input:
(contents of the .in file)
Expected:
(contents of the .out file)
Actual:
(contents of the actual program output)

If the output of a given test case is identical to the expected output, nothing will be printed out.

If some test files are missing or unreadable, error message will be redirected to standard error.
