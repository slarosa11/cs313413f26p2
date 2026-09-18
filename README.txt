COMP 313/413 Project 2 Report Template

TestList.java and TestIterator.java

	TODO also try with a LinkedList - does it make any difference?

		There is no behavioral/observable difference in the way they implement List. The tests/assertions pass the same. The only difference between ArrayList and LinkedList is performance/runtime, as shown below.

TestList.java

	testRemoveObject()

		list.remove(5); // what does this method do?

			The element at position/index 5 is what is removed.
			The remove(int index) overload removes by index, not value.

		list.remove(Integer.valueOf(5)); // what does this one do?

			The element that is equal to the value of 5 is what is removed.
			The remove(Object o) overload removes by value rather than position.

TestIterator.java

	testRemove()

		i.remove(); // what happens if you use list.remove(77)?

			Here, it is modifying a list while an Iterator is looping over it. This causes an error/exception

TestPerformance.java

	State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000)
	to get the running time in milliseconds and how the test running times were recorded.

	SIZE 10
				#1   #2   #3   #4
        testArrayListAddRemove:  72 72 70 70
        testLinkedListAddRemove: 28 37 29 31
	testArrayListAccess:     16 44 16 48
        testLinkedListAccess:    16 17 16 19

	SIZE 100
				 #1   #2   #3   #4
        testArrayListAddRemove:  87 84 79 98
        testLinkedListAddRemove: 36 31 28 34
	testArrayListAccess:     38 45 53 51
        testLinkedListAccess:    37 32 29 30

	SIZE 1000
				 #1   #2   #3   #4
        testArrayListAddRemove:  173 228 206 206
        testLinkedListAddRemove: 37 38 36 31
	testArrayListAccess:     39 36 67 54
        testLinkedListAccess:    305 397 319 327

	SIZE 10000
				 #1   #2   #3   #4
        testArrayListAddRemove:  1390 1397 1525 1534
        testLinkedListAddRemove: 30 36 40 32
	testArrayListAccess:     56 51 59 43
        testLinkedListAccess:    3935 4123 4188 4330

	listAccess - which type of List is better to use, and why?

		ArrayList seems to be better as it runtime stays relatively consistent even as SIZE increases, whereas LinkedListAccess gets noticeably slower.

	listAddRemove - which type of List is better to use, and why?

		LinkedList appears to be better, since for listAddRemove, the runtime stays relatively consistent whereas the runtime gets much slower for ArrayList as SIZE grows.
