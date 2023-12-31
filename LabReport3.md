# Lab Report 3
## Part 1: Bugs

__Failure Inducing Input__
```
# test code that produces a failure
@Test
  public void testReversed2() {
    int[] input1 = {1, 2, 3, 4};
    assertArrayEquals(new int[]{4, 3, 2, 1}, ArrayExamples.reversed(input1));
  }
```

__Non-failure Inducing Input__
```
# test code that doesn't produce a failure
@Test
  public void testReversed3() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

__Symptom__
![Image](symptoms-2.png)

__Before Code Change__
```
# buggy code
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```
__After Code Change__
```
# fixed code
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
In the before code, there's an issue with the assignment of values in the `newArray` inside the `reversed` method. The correct values from the original array`arr` should be copied into `newArray` in reverse order. It is assigning values incorrectly, leading to a failure in producing the reversed array. In the corrected code, the values from the input array `arr` are appropriately assigned to the `newArray` in reverse order. This is achieved by iterating through the original array and assigning elements to the new array in a reversed sequence (`arr.length - i - 1` retrieves the elements in reverse order).In the before code, the assignment was flawed, causing incorrect or uninitialized values to be stored in the `newArray`. In the corrected code, a new array of the same size as the original array is correctly initialized to hold the reversed elements, ensuring the correct assignment of reversed elements. 

## Part 2: `find` Command
`find . -mtime`
```
# code for example 1 of -mtime
owner@Owners-MacBook-Pro docsearch % find technical/plos -mtime -5
technical/plos
technical/plos/pmed.0020273.txt
technical/plos/journal.pbio.0030032.txt
technical/plos/pmed.0020065.txt
technical/plos/pmed.0020071.txt
technical/plos/pmed.0020059.txt
technical/plos/pmed.0010039.txt
technical/plos/journal.pbio.0020354.txt
technical/plos/pmed.0010010.txt
technical/plos/journal.pbio.0020156.txt
technical/plos/pmed.0020104.txt
technical/plos/pmed.0020272.txt
technical/plos/pmed.0020258.txt
technical/plos/pmed.0020099.txt
technical/plos/journal.pbio.0020140.txt
technical/plos/journal.pbio.0020183.txt
technical/plos/journal.pbio.0020430.txt
technical/plos/journal.pbio.0020394.txt
technical/plos/journal.pbio.0020431.txt
technical/plos/journal.pbio.0020419.txt
technical/plos/pmed.0010013.txt
technical/plos/pmed.0020113.txt
technical/plos/journal.pbio.0020169.txt
technical/plos/pmed.0020098.txt
technical/plos/journal.pbio.0020035.txt
technical/plos/pmed.0020067.txt
technical/plos/pmed.0020073.txt
technical/plos/journal.pbio.0030024.txt
technical/plos/journal.pbio.0020223.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020275.txt
technical/plos/journal.pbio.0020019.txt
technical/plos/pmed.0020088.txt
technical/plos/journal.pbio.0020145.txt
technical/plos/pmed.0020103.txt
technical/plos/pmed.0020117.txt
technical/plos/journal.pbio.0020353.txt
technical/plos/journal.pbio.0020347.txt
technical/plos/journal.pbio.0020420.txt
technical/plos/journal.pbio.0020346.txt
technical/plos/journal.pbio.0020187.txt
technical/plos/pmed.0020116.txt
technical/plos/pmed.0020102.txt
technical/plos/journal.pbio.0020150.txt
technical/plos/pmed.0020062.txt
technical/plos/pmed.0020274.txt
technical/plos/journal.pbio.0020232.txt
technical/plos/journal.pbio.0030021.txt
technical/plos/journal.pbio.0020224.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020060.txt
technical/plos/pmed.0020074.txt
technical/plos/journal.pbio.0020146.txt
technical/plos/pmed.0020114.txt
technical/plos/pmed.0010028.txt
technical/plos/journal.pbio.0020350.txt
technical/plos/journal.pbio.0020190.txt
technical/plos/pmed.0010029.txt
technical/plos/pmed.0020115.txt
technical/plos/journal.pbio.0020147.txt
technical/plos/pmed.0020075.txt
technical/plos/pmed.0020061.txt
technical/plos/pmed.0020210.txt
technical/plos/pmed.0020238.txt
technical/plos/journal.pbio.0030051.txt
technical/plos/journal.pbio.0020068.txt
technical/plos/journal.pbio.0020054.txt
technical/plos/journal.pbio.0020040.txt
technical/plos/pmed.0010066.txt
technical/plos/journal.pbio.0030131.txt
technical/plos/journal.pbio.0020337.txt
technical/plos/pmed.0020198.txt
technical/plos/pmed.0010067.txt
technical/plos/journal.pbio.0020121.txt
technical/plos/pmed.0020007.txt
technical/plos/journal.pbio.0030050.txt
technical/plos/pmed.0020239.txt
technical/plos/journal.pbio.0020241.txt
technical/plos/pmed.0020005.txt
technical/plos/journal.pbio.0020043.txt
technical/plos/pmed.0020039.txt
technical/plos/pmed.0010071.txt
technical/plos/journal.pbio.0030127.txt
technical/plos/pmed.0010058.txt
technical/plos/pmed.0010070.txt
technical/plos/pmed.0010064.txt
technical/plos/pmed.0020158.txt
technical/plos/journal.pbio.0020042.txt
technical/plos/journal.pbio.0020297.txt
technical/plos/pmed.0020206.txt
technical/plos/pmed.0020212.txt
technical/plos/pmed.0020216.txt
technical/plos/journal.pbio.0030094.txt
technical/plos/journal.pbio.0020046.txt
technical/plos/pmed.0020028.txt
technical/plos/journal.pbio.0020052.txt
technical/plos/pmed.0020148.txt
technical/plos/pmed.0020160.txt
technical/plos/pmed.0010048.txt
technical/plos/pmed.0010060.txt
technical/plos/journal.pbio.0030137.txt
technical/plos/journal.pbio.0030136.txt
technical/plos/pmed.0010061.txt
technical/plos/pmed.0010049.txt
technical/plos/pmed.0020161.txt
technical/plos/journal.pbio.0020127.txt
technical/plos/pmed.0020149.txt
technical/plos/journal.pbio.0020133.txt
technical/plos/pmed.0020015.txt
technical/plos/journal.pbio.0020053.txt
technical/plos/journal.pbio.0020047.txt
technical/plos/pmed.0020203.txt
technical/plos/journal.pbio.0030056.txt
technical/plos/pmed.0020201.txt
technical/plos/journal.pbio.0030097.txt
technical/plos/pmed.0020017.txt
technical/plos/journal.pbio.0020125.txt
technical/plos/journal.pbio.0020440.txt
technical/plos/pmed.0010062.txt
technical/plos/pmed.0020189.txt
technical/plos/pmed.0020162.txt
technical/plos/pmed.0020016.txt
technical/plos/pmed.0020002.txt
technical/plos/pmed.0020200.txt
technical/plos/pmed.0020231.txt
technical/plos/journal.pbio.0020263.txt
technical/plos/pmed.0020027.txt
technical/plos/pmed.0020033.txt
technical/plos/journal.pbio.0020101.txt
technical/plos/pmed.0010047.txt
technical/plos/journal.pbio.0030105.txt
technical/plos/journal.pbio.0020302.txt
technical/plos/pmed.0010046.txt
technical/plos/pmed.0010052.txt
technical/plos/pmed.0020191.txt
technical/plos/journal.pbio.0020100.txt
technical/plos/pmed.0020146.txt
technical/plos/journal.pbio.0020262.txt
technical/plos/journal.pbio.0030065.txt
technical/plos/journal.pbio.0020276.txt
technical/plos/pmed.0020232.txt
technical/plos/pmed.0020226.txt
technical/plos/pmed.0020024.txt
technical/plos/pmed.0020018.txt
technical/plos/pmed.0020144.txt
technical/plos/pmed.0020150.txt
technical/plos/journal.pbio.0020116.txt
technical/plos/pmed.0020187.txt
technical/plos/pmed.0010050.txt
technical/plos/pmed.0010051.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0010045.txt
technical/plos/pmed.0020145.txt
technical/plos/pmed.0020019.txt
technical/plos/journal.pbio.0020063.txt
technical/plos/journal.pbio.0030076.txt
technical/plos/journal.pbio.0030062.txt
technical/plos/pmed.0020237.txt
technical/plos/journal.pbio.0020067.txt
technical/plos/pmed.0020009.txt
technical/plos/journal.pbio.0020073.txt
technical/plos/pmed.0020035.txt
technical/plos/pmed.0020021.txt
technical/plos/journal.pbio.0020113.txt
technical/plos/pmed.0020155.txt
technical/plos/pmed.0010069.txt
technical/plos/pmed.0010041.txt
technical/plos/pmed.0020182.txt
technical/plos/pmed.0020196.txt
technical/plos/journal.pbio.0020311.txt
technical/plos/journal.pbio.0030102.txt
technical/plos/journal.pbio.0020310.txt
technical/plos/pmed.0020197.txt
technical/plos/pmed.0010068.txt
technical/plos/pmed.0020140.txt
technical/plos/journal.pbio.0020112.txt
technical/plos/pmed.0020020.txt
technical/plos/pmed.0020034.txt
technical/plos/pmed.0020236.txt
technical/plos/journal.pbio.0020272.txt
technical/plos/pmed.0020208.txt
technical/plos/journal.pbio.0020064.txt
technical/plos/pmed.0020022.txt
technical/plos/pmed.0020036.txt
technical/plos/pmed.0010056.txt
technical/plos/pmed.0020195.txt
technical/plos/pmed.0010042.txt
technical/plos/pmed.0020181.txt
technical/plos/journal.pbio.0020306.txt
technical/plos/journal.pbio.0030129.txt
technical/plos/journal.pbio.0020307.txt
technical/plos/pmed.0020180.txt
technical/plos/pmed.0020194.txt
technical/plos/pmed.0020157.txt
technical/plos/journal.pbio.0020105.txt
technical/plos/pmed.0020023.txt
technical/plos/journal.pbio.0020071.txt
technical/plos/pmed.0020235.txt
technical/plos/journal.pbio.0020267.txt
technical/plos/pmed.0020209.txt
technical/plos/pmed.0020246.txt
technical/plos/journal.pbio.0020228.txt
technical/plos/journal.pbio.0020214.txt
technical/plos/pmed.0020050.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0010030.txt
technical/plos/pmed.0010024.txt
technical/plos/journal.pbio.0020348.txt
technical/plos/journal.pbio.0020406.txt
technical/plos/pmed.0010025.txt
technical/plos/pmed.0020086.txt
technical/plos/pmed.0020045.txt
technical/plos/journal.pbio.0020215.txt
technical/plos/pmed.0020247.txt
technical/plos/pmed.0020047.txt
technical/plos/journal.pbio.0020001.txt
technical/plos/pmed.0020090.txt
technical/plos/journal.pbio.0020161.txt
technical/plos/journal.pbio.0020439.txt
technical/plos/journal.pbio.0020404.txt
technical/plos/pmed.0010026.txt
technical/plos/journal.pbio.0020148.txt
technical/plos/pmed.0020085.txt
technical/plos/pmed.0020091.txt
technical/plos/journal.pbio.0020028.txt
technical/plos/journal.pbio.0020216.txt
technical/plos/pmed.0020278.txt
technical/plos/pmed.0020268.txt
technical/plos/journal.pbio.0020206.txt
technical/plos/journal.pbio.0020010.txt
technical/plos/journal.pbio.0020164.txt
technical/plos/pmed.0010022.txt
technical/plos/pmed.0010036.txt
technical/plos/journal.pbio.0020400.txt
technical/plos/journal.pbio.0020401.txt
technical/plos/pmed.0010023.txt
technical/plos/pmed.0020123.txt
technical/plos/pmed.0020094.txt
technical/plos/journal.pbio.0020213.txt
technical/plos/pmed.0020257.txt
technical/plos/journal.pbio.0020013.txt
technical/plos/pmed.0020055.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0010021.txt
technical/plos/pmed.0010034.txt
technical/plos/pmed.0010008.txt
technical/plos/pmed.0020120.txt
technical/plos/journal.pbio.0020172.txt
technical/plos/pmed.0020040.txt
technical/plos/pmed.0020068.txt
technical/plos/journal.pbio.0020012.txt
technical/plos/pmed.0020281.txt
technical/plos/pmed.0020242.txt
```
```
# code for example 2
owner@Owners-MacBook-Pro docsearch % find technical/biomed -mtime -3  
owner@Owners-MacBook-Pro docsearch % 
```

The command `find . -mtime` is used to locate files based on their last modification time within the current directory, searching for files that were modified a specified number of days ago. It is useful for tasks such as identifying recently modified files or performing actions on files that were changed within a specific timeframe.

`find . !`
```
# code for example 3
owner@Owners-MacBook-Pro docsearch % find technical/911report ! -name "preface.txt"
technical/911report
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-1.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/chapter-12.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```
```
# code for example 4
owner@Owners-MacBook-Pro docsearch % find technical/911report ! -name "chapter-*.txt"
technical/911report
technical/911report/preface.txt
```
The command `find . !` is used to exclude certain files or directories from the searhc within the current directory, providing a means to filter out specific files or directories. The is useful for specific searches that exclude particular files or directories based on conditions, and focus on searching for specific items or types of files.

`find . -size`
```
# code for example 5
owner@Owners-MacBook-Pro docsearch % find technical/biomed -size +70kb
technical/biomed/gb-2002-3-7-research0036.txt
technical/biomed/1472-6904-2-5.txt
technical/biomed/gb-2002-3-11-research0059.txt
technical/biomed/1472-6807-3-1.txt
technical/biomed/gb-2002-3-12-research0086.txt
technical/biomed/gb-2002-3-12-research0083.txt
technical/biomed/1476-511X-1-2.txt
technical/biomed/1471-2105-3-18.txt
technical/biomed/1471-2202-3-1.txt
technical/biomed/1472-6882-1-10.txt
technical/biomed/1471-2105-3-2.txt
technical/biomed/1476-069X-2-9.txt
```
```
# code for example 6
owner@Owners-MacBook-Pro docsearch % find technical/plos -size +30kb
technical/plos/pmed.0020059.txt
technical/plos/pmed.0020073.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020103.txt
technical/plos/pmed.0010028.txt
technical/plos/pmed.0020018.txt
technical/plos/pmed.0020182.txt
technical/plos/pmed.0020246.txt
technical/plos/pmed.0020045.txt
technical/plos/pmed.0010036.txt
```
The command `find . -size` is used to locate files within the current directory based on their size, allowing the ability to filter files based on size such as by exact sizes, ranges, or by different units (bytes, megabytes, kilobytes, etc). This is useful for managing space, identifying between large or small files, and targeting files that meest specific size requirements.

`find . -regex`
```
# code for example 7
owner@Owners-MacBook-Pro docsearch % find technical/911report -regex ".*/chapter-[2-8].txt"
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-8.txt
```
```
# code for example 8
owner@Owners-MacBook-Pro docsearch % find technical/biomed -regex ".*16\.txt$"
technical/biomed/1471-2121-3-16.txt
technical/biomed/1471-2091-2-16.txt
technical/biomed/1471-2156-3-16.txt
technical/biomed/1471-2202-4-16.txt
technical/biomed/1471-2458-2-16.txt
technical/biomed/gb-2003-4-2-r16.txt
technical/biomed/1471-2164-3-16.txt
technical/biomed/1472-6793-2-16.txt
technical/biomed/1471-2407-2-16.txt
technical/biomed/1471-2180-1-16.txt
technical/biomed/1471-2202-2-16.txt
technical/biomed/1471-2172-3-16.txt
technical/biomed/1471-2105-3-16.txt
technical/biomed/1471-2164-4-16.txt
technical/biomed/1471-2091-3-16.txt
technical/biomed/1471-2180-2-16.txt
technical/biomed/1471-2202-3-16.txt
technical/biomed/1471-2407-3-16.txt
```
The command `find . -regex` searches for files within the current directory using a regular expression pattern to match filenames, enabling complex and specific pattern-based searches to precisely locate files that match the defined criteria. This is useful for performing advanced and customizable file seraches, allowing for seraches that specify certain patterns for file names (e.g: files with a certain numerical range or files that begin/end with a certain patterm), providing greater flexibility in file selection during seraches.

## Sources 

__ChatGPT__

Prompt: List of find command-line options

Output:
The find command in Unix-like operating systems is a powerful tool used to search for files and directories in a directory hierarchy. Here is a list of some commonly used options with the find command:

-name: Searches for files or directories based on their name.

Example: find /path/to/search -name "file.txt"

-type: Filters based on the type of the file (e.g., directories, regular files, symbolic links).

Example: find /path/to/search -type f (for regular files)

-iname: Case-insensitive search by name.

Example: find /path/to/search -iname "file.txt"

-user: Searches for files owned by a specific user.

Example: find /path/to/search -user username

-group: Searches for files belonging to a specific group.

Example: find /path/to/search -group groupname

-size: Allows searching based on file size.

Example: find /path/to/search -size +1M (for files larger than 1 megabyte)

-mtime, -atime, -ctime: Search files based on modification, access, or change time.

Example: find /path/to/search -mtime -7 (for files modified within the last 7 days)

-exec: Executes a command on the found files.

Example: find /path/to/search -name "*.txt" -exec ls -l {} \;

-maxdepth and -mindepth: Restricts the depth of directory traversal.

Example: find /path/to/search -maxdepth 2 (limits the search to a depth of 2 directories)

-delete: Deletes the found files.

Example: find /path/to/search -name "file.txt" -delete

-print: Prints the found files to the standard output.

Example: find /path/to/search -name "file.txt" -print

-regex: Search files matching a regular expression.

Example: find /path/to/search -regex ".*\(\.txt\|\.doc\)"

-!: Perform a search exclusing certain criteria or patterms within a directory

Example: find /path/to/search ! -name "*.txt"

These additional options expand the functionality and control offered by the `find` command in Unix-like systems, providing various ways to refine searches, perform actions on the found files, and handle different scenarios effectively.Always refer to the `man find` command for more comprehensive information and usage examples.
