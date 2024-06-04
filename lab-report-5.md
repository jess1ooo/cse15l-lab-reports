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

import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }
    return result;
  }


}

- The command I used to find the bug was `./grade.sh https://github.com/jess1ooo/ListMethods.git`.
- To fix the bug I fixed line 43 so that it was getting the value for index2 rather than index1.


Part 2: Reflection
Something cool I learned in the second half of this quarter is how to use bash and create an autograder myself. I learned how our assignments are basically graded. I've also learned some new things from my classmates like different study methods and other paths to get to classes and just around in general. 
