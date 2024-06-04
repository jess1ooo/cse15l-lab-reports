Part 1: Debugging Scenario

1. The Post
My code is getting a 57 on autograder but it looks pretty good to be what could be wrong? It's failing 3 tests: testMergeLeftEmpty,testMergeInterleaved, and testMergeRightEnd.
<img width="655" alt="image" src="https://github.com/jess1ooo/cse15l-lab-reports/assets/156467137/3a5a54cb-9698-4bd9-a46b-a5551b282621">




2. TA Response
How does the second while loop differ to the first while loop, should that be different, what are you trying to get the value for after each loop?


3. Student Screenshot
<img width="496" alt="image" src="https://github.com/jess1ooo/cse15l-lab-reports/assets/156467137/2951b76a-ebc3-4ffc-829b-97a771769bc8">

The bug was on line 43 it should be index2 rather than index1.

4. Setup Info
   - The file & directory structure needed was `List-Examples-Grader` as the main directory, then the `grading-area directory` inside of that. Inside of that directory is the `lib` folder containing the files to run tests. In the `grading-area directory` there is also the `ListExamples.java`, `result.txt`, and the `TestListExamples.java` files. Outside of the `grading-area directory` but inside the `List-Examples-Grader` directory are the `grade.sh`. `GradeServer.java`, `Server.java`, `TestListExamples.java` files. There is also a `student-submission` directory that contains the students `ListExamples.java` file.
- 
<img width="278" alt="Screen Shot 2024-06-03 at 5 21 58 PM" src="https://github.com/jess1ooo/cse15l-lab-reports/assets/156467137/cec8b5d7-c66f-4f39-bc9e-242d1f8456c2">

   - The only file thats contents change is `ListExamples.java` file inside of the `student-submission` directory, depending on the file being graded.
ListExamples.java before the bug is fixed:

<img width="440" alt="image" src="https://github.com/jess1ooo/cse15l-lab-reports/assets/156467137/6b17b86c-111c-4b72-9906-a30366db5ec5">


- The command I used to find the bug was `./grade.sh https://github.com/jess1ooo/ListMethods.git`.
- To fix the bug I fixed line 43 so that it was getting the value for index2 rather than index1.


Part 2: Reflection
Something cool I learned in the second half of this quarter is how to use bash and create an autograder myself. I learned how our assignments are basically graded. I've also learned some new things from my classmates like different study methods and other paths to get to classes and just around in general. 
