Part 1: Debugging Scenario

1. The Post
My code is getting a 0 on autograder but it looks pretty good to be what could be wrong? It says the files not found, could it be a syntax error?
<img width="557" alt="Screen Shot 2024-06-03 at 5 03 57 PM" src="https://github.com/jess1ooo/cse15l-lab-reports/assets/156467137/7b1b17c3-4881-4013-838c-1d02ab660fc9">


2. TA Response
You might have the labeled the class incorrectly try changing it to `ListExamples`

3. Student Screenshot
<img width="622" alt="Screen Shot 2024-06-03 at 5 12 14 PM" src="https://github.com/jess1ooo/cse15l-lab-reports/assets/156467137/e67e20b1-11d5-4b9b-9a32-08bcba8644bb">
The bug was the class name being `ListMethods` instead of `ListExamples`.

4. Setup Info
   - The file & directory structure needed was `List-Examples-Grader` as the main directory, then the `grading-area directory` inside of that. Inside of that directory is the `lib` folder containing the files to run tests. In the `grading-area directory` there is also the `ListExamples.java`, `result.txt`, and the `TestListExamples.java` files. Outside of the `grading-area directory` but inside the `List-Examples-Grader` directory are the `grade.sh`. `GradeServer.java`, `Server.java`, `TestListExamples.java` files. There is also a `student-submission` directory that contains the students `ListExamples.java` file.
<img width="278" alt="Screen Shot 2024-06-03 at 5 21 58 PM" src="https://github.com/jess1ooo/cse15l-lab-reports/assets/156467137/cec8b5d7-c66f-4f39-bc9e-242d1f8456c2">

   - The only file thats contents change is `ListExamples.java` file inside of the `student-submission` directory, depending on the file being graded.
ListExamples.java before the bug is fixed:
`import java.util.ArrayList;
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
}`
- The command I used to find the bug was `./grade.sh https://github.com/jess1ooo/ListMethods.git`.
- To fix the bug I changed the class name for `ListMethods` to `ListExamples`.



Part 2: Reflection
