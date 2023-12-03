# Lab Report 5 - Putting it All Together

## Part 1: Debugging Scenario

___Student___

> Hi! I'm having some trouble in getting my tests to pass for the file `ListExamples.java`. The output makes me believe that the problem has something to do with the structure of the merged list. I'm guessing the problem could lie on either the lists are not merging as they should be or the merged list is not sorted correctly but I'm not entirely sure.
> 
>  ![Debug Symptom Image](lab5-symptom.png)

___TA___

> Carefully look at the error output in your terminal when you ran your tests and use that as a guide to figure out what might be wrong. What was your expected result versus what the outcome actually was and is there anything in your code that might've led to a disruption in how the list may be sorted?

___Student___

> After closely analyzing the output, for `testMerge1()` the first element of the merged list should've been the first element ("a") from `list2` but instead it was the first element from `list1` ("x") and similarily for `testMerge2()`, the failure resulted from a difference in the fourth element of the merged list that should've been the first element ("c") from `list2` but instead it was second element of `list2` ("d"). This caused me to believe that the bug specifically impacted `list2` -  it skiped the next element in `list2` by incrementing `index2` in `merge()`. This led to missing elements from `list2` in the final merged list. I was then able fix the bug in `merge()` so that all elements from `list2` are in the final merged list and all my tests were able to pass!
> 
>  ![Fix Bug Image](lab5-fix.png)



---

__Setup Information__

File(s):

- ListExamples.java
- ListExamplesTests.java
- test.sh

Directory structure: 

```
/home/linux/ieng6/cs15lfa23/cs15lfa23fd/lab7
├── ListExamples.java
├── ListExamplesTests.java
├── lib
│   ├── hamcrest-core-1.3.jar
│   └── junit-4.13.2.jar
└── test.sh
```

Contents of each file:

```
# ListExamples.java file before fix
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
        result.add(0, s);
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
        
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }


}
```

```
# ListExamplesTests.java file
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;
import java.util.ArrayList;


public class ListExamplesTests {
	@Test(timeout = 500)
	public void testMerge1() {
    		List<String> l1 = new ArrayList<String>(Arrays.asList("x", "y"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("a", "b"));
		assertArrayEquals(new String[]{ "a", "b", "x", "y"}, ListExamples.merge(l1, l2).toArray());
	}
	
	@Test(timeout = 500)
        public void testMerge2() {
		List<String> l1 = new ArrayList<String>(Arrays.asList("a", "b", "c"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("c", "d", "e"));
		assertArrayEquals(new String[]{ "a", "b", "c", "c", "d", "e" }, ListExamples.merge(l1, l2).toArray());
        }

}
```

```
# test.sh bash file
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```

Command line that triggered bug: `bash test.sh`

Bug fix: The elements in `list2` need to be added to the result when the corresponding index (`index2`) is incremented. To ensure this, the code line `result.add(list2.get(index2))` needs to be included inside the `else` block code before the line `index2 += 1` in order to add the elements from `list2` to the `result` list so that the merged list is sorted in ascending order. The `index2` will be incremented to move to the next element in `list2`. The merging process will continue until all elements from both lists are added to the `result` list in sorted order.   

---

## Part 2: Reflection

In the second half of this quarter, I was able to work with bash script for the first time and delve into its useful and interesting capabilities. I was able to learn how to write efficient scripts in Bash to automate repetitive tasks such has checking matching file. Bash allows you to work with variables, perform operations, and use control flow constructs like loops and conditionals. It allows you to use the output of a command as an argument for another command, which I learned can enhance the flexibility of scripts. I learned to use commands such as `cp` and `rm` in order to be able to easily navigate and manipulate the file system. I learned to use `grep` to help search, match, and manipulate text in a flexible manner. I also learned to use constructs such as `if` statements and `exit codes` to handle errors and exceptions with ease. 
