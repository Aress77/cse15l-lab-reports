# Part 1

### I am testing the `merge` method in `ListExamples.java`.

## 1. failure-inducing input

```
    @Test
    public void testMerge() {
        List<String> list1 = Arrays.asList("a", "v");
        List<String> list2 = Arrays.asList("e", "n", "t", "u");

        List<String> expected = Arrays.asList("a", "e", "n", "t", "u", "v");
        List<String> result = ListExamples.merge(list1, list2);

        assertEquals(expected, result);
    }
```

## 2. no failure input

```
    @Test
    public void testMergeNoFail() {
        List<String> list1 = Arrays.asList("a", "n", "t", "u");
        List<String> list2 = Arrays.asList("e");

        List<String> expected = Arrays.asList("a", "e", "n", "t", "u");
        List<String> result = ListExamples.merge(list1, list2);

        assertEquals(expected, result);
    }
```

## 3. The symptom

<img width="784" alt="Screen Shot 2024-05-05 at 4 27 42 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/2f741842-c2c6-4caf-b2d2-15c51a129394">


## 4. The bug

### Before Change

```
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
```
### After Change

```
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
      index2 += 1;
    }
    return result;
  }
```

## 5. Why? 

The origional code had `index1 += 1;` in the third while loop. But the third while loop is adding the remaining elements from list2, so the index that is incrementing should be `index2`.

# Part 2 `find`

## 1. -empty  
True if the current file or directory is empty. 
### Examples
```
ahri@Ahris-MacBook-Air lab3 % touch emptyFile.txt
ahri@Ahris-MacBook-Air lab3 % find . -empty
./.git/objects/info
./.git/refs/tags
./emptyFile.txt
```

```
ahri@Ahris-MacBook-Air Spring 2024 % find /Users/ahri/Documents/Spring\ 2024/CSE\ 15L/wavelet-main\ 2 -empty
ahri@Ahris-MacBook-Air Spring 2024 % 
```
This is useful when trying to find unwanted empty files without opening any files and checking individually.

## 2.    -quit   
Causes find to terminate immediately.
### Examples
```
ahri@Ahris-Air ~ % find . -empty -print -quit
./.config/rstudio/dictionaries/custom
```
```
ahri@Ahris-Air ~ % find /Users/ahri/Downloads -name "cse*" -print -quit
/Users/ahri/Downloads/cse11-pa6-starter-main.zip
```
This `-quit` command is useful when we want to find the first file or directory. The terminal will stop running after it finds the fitst element. 

## 3. -delete
Delete found files and/or directories.  Always returns true.  This executes from the current working directory as find recurses down the tree.  It will not attempt to delete a filename with a “/” character in its pathname relative to “.” for security reasons.  Depth-first traversal processing is implied by this option.  The -delete primary will fail to delete a directory if it is not empty.  Following symlinks is incompatible with this option.
### Examples
```
ahri@Ahris-Air lab3 % touch "emptyFile.txt"
ahri@Ahris-Air lab3 % ls
ArrayExamples.class     ArrayTests.java         LinkedList.class        ListExamples.java       StringChecker.class
ArrayExamples.java      FileExample.class       LinkedListExample.java  ListTests.java          emptyFile.txt
ArrayTests.class        FileExample.java        ListExamples.class      Node.class              lib
ahri@Ahris-Air lab3 % find . -name "empty*" -delete

ahri@Ahris-Air lab3 % ls
ArrayExamples.class     ArrayTests.java         LinkedList.class        ListExamples.java       StringChecker.class
ArrayExamples.java      FileExample.class       LinkedListExample.java  ListTests.java          lib
ArrayTests.class        FileExample.java        ListExamples.class      Node.class
ahri@Ahris-Air lab3 % 
```

```
ahri@Ahris-Air lab3 % ls
ArrayExamples.class     ArrayTests.java         LinkedList.class        ListExamples.java       StringChecker.class
ArrayExamples.java      FileExample.class       LinkedListExample.java  ListTests.java          lib
ArrayTests.class        FileExample.java        ListExamples.class      Node.class
ahri@Ahris-Air lab3 % find . -name "*.class" -delete
ahri@Ahris-Air lab3 % ls
ArrayExamples.java      FileExample.java        ListExamples.java       lib
ArrayTests.java         LinkedListExample.java  ListTests.java
ahri@Ahris-Air lab3 % 
```
This is useful because this command allows us to efficiently delete multiple files with same name/file type. 

## 4. -maxdepth n
Always true; descend at most n directory levels below the command line arguments.  If any -maxdepth primary is specified, it applies to the entire expression even if it would not normally be evaluated.  “-maxdepth 0” limits the whole search to the command line arguments.
### Examples
```
ahri@Ahris-Air ~ % find . -name "cse*" -maxdepth 2 -print
find: ./.Trash: Operation not permitted
./Downloads/cse11-pa6-starter-main.zip
./Downloads/cse11-pa7-starter-main.zip
./Downloads/cse12-pa3-Mazes-master
./Downloads/cse11-pa5-starter-main.zip
./Downloads/cse11-pa1-starter-main.zip
./Downloads/cse12-pa4-runtime-main.zip
./Downloads/cse12-pa4-runtime-main
```

```
ahri@Ahris-Air ~ % find ./Documents/Spring\ 2024 -maxdepth 1 -print 
./Documents/Spring 2024
./Documents/Spring 2024/.DS_Store
./Documents/Spring 2024/CSE 12
./Documents/Spring 2024/CSE 15L
```
It is useful when we do not want to search everything inside a directory. This command limits the depth of our searches. 

I used `man find` in terminal to find command line options for `find`.

