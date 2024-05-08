1.
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

2.
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
3. ![Image](sc1.png)
4. The bug
   before -
![Image](bug1.png)
after -
![Image](bug2.png)
terminal after -
![Image](pass4.png)
5.In the 'filter' method the elements were being added incorrectly because they weren't only being added to the end of the list, they were also being added to the beginning so the list was reversed. The erasure of the index 0 part ensures that the order is correct because it is only adding to the end of the list. 

