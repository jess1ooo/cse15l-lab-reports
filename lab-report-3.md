Part 1: 

   (1).
   @Test
    public void testFilterFail() {
        List<String> inputList = new ArrayList<>();
        inputList.add("apple");
        inputList.add("banana");
        inputList.add("orange");

        StringChecker alwaysTrueChecker = s -> true;

        List<String> filteredList = ListExamples.filter(inputList, alwaysTrueChecker);

        assertEquals(inputList, filteredList);
    }

(2).
   @Test
    public void testFilterPass() {
        List<String> inputList = new ArrayList<>();
        inputList.add("apple");
        inputList.add("banana");
        inputList.add("orange");

        StringChecker alwaysFalseChecker = s -> false;

        List<String> filteredList = ListExamples.filter(inputList, alwaysFalseChecker);

        assertTrue(filteredList.isEmpty());
    }
  
(3). ![Image](sc1.png)
   
(4). The bug
   before -
![Image](bug1.png)
after -
![Image](bug2.png)
terminal after -
![Image](pass4.png)

(5).In the 'filter' method the elements were being added incorrectly because they weren't only being added to the end of the list, they were also being added to the beginning so the list was reversed. The erasure of the index 0 part ensures that the order is correct because it is only adding to the end of the list. 

Part 2: 
grep functions

(1). grep -i
* ![Image](-i1.png)
  - This command ignores the case. It's useful when you're searching for something regardless of case. Here it is ignoring the case of "txt" in the 'biomed' directory. It's printing all the instances its found thhe word "txt". 
  - source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
* ![Image](-i2.png)
  - This command ignores the case. It's useful when you're searching for something regardless of case. In this instance the command is  searching for a pattern in files and directories recursively while ignoring the case of the pattern for the word "as". It's useful when you're searching for something regardless of case. Here it is ignoring the case of "txt" in the 'biomed' directory.
  - source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix

(2). grep -v
* ![Image](-v1.png)
  - This command finds lines that don't match, it essentially prints lines that don't contain the specified pattern. Here that pattern is the word "unwieldly". The command is printing all the lines that don't have the word "unwieldly" from the directory '911report', file 'preface.txt'. It'd be useful when you are trying to avoid something on purpose. 
  - source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
* ![Image](-v2.png)
  - This command finds lines that don't match, it essentially prints lines that don't contain the specified pattern. Here that pattern is the word "unwieldly". The command is printing all the lines that don't have the word "We" from the directory '911report', file 'preface.txt'. It'd be useful when you are trying to avoid something on purpose. 
  - source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix

(3). grep -n
* ![Image](n1.png)
  - This command is printing the line number of the pattern it is searching for. Here that pattern is the word "ATTACK". It's useful for when you're looking for something specifically.
  - source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
* ![Image](n2.png)
  - This command is printing what line the word "Between" is found in the file 'chapter-1.txt' from the directory '911report'. It's useful for when you're looking for something specifically.
  - source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix

(4). grep -l
* ![Image](-l1.png)
  - This command prints the name of each  file that has the pattern you are searching for. Here that pattern is "THREAT". It's useful when you only want to know which files contain the matching pattern.
  -  source: https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/
* ![Image](-l2.png)
  -  This command prints the name of each  file that has the pattern you are searching for. Here that pattern is "location". It's useful when you only want to know which files contain the matching pattern.
  - source: https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/

