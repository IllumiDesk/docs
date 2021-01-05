# How do hidden tests within an assignment work?

Hidden tests are unit tests that are hidden from the student's version of the Jupyter Notebook. The grader's pre-processors replace the content in between the hidden tests delimiters and replaces the text with an empty space when the instructor generates the student version of the assignment.  
For example, consider the following asserts when placed in the **Auto-graded Tests** cell. When the instructor user clicks on the **Generate** option a pre-processor is used that replaces the content in between these delimiters with and empty space. Therefore a source cell that appears as:  
  


1. assert squares\(1\) = \[1\]
2. \#\#\# BEGIN HIDDEN TESTS
3. assert squares\(2\) = \[1, 4\]
4. \#\#\# END HIDDEN TESTS

  
will be generated/released as:  
  


1. assert squares\(1\) = \[1\] 

  
Once the grader receives the student's submission and initiates the auto-grader service, all tests from the original source files are used to assert and grade the answers, including those originally hidden from the student.

