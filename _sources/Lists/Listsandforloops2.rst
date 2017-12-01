..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-17-
   :start: 1

.. index:: list; traversal, traversal; by index, accumulator, list; accumulator

List Traversal by Index
-----------------------

We can also use the indices to access the items in an iterative fashion.

.. activecode:: lir

    fruits = ["apple", "orange", "banana", "cherry"]

    for position in range(len(fruits)):     # by index
        print(fruits[position])


In this example, each time through the loop, the variable ``position`` is used as an index into the list, printing the ``position``-eth element. Note that we used ``len`` as the upper bound on the range so that we can iterate correctly no matter how many items are in the list.

.. note::
   This technique should only be used when necessary. Whenever possible, we should use :ref:`list_traverse`.

Since lists are mutable, it is often desirable to traverse a list, modifying each of its elements as you go.

.. activecode:: lis

    numbers = [1, 2, 3, 5, 8]
    print(numbers)

    for num in numbers:
        num = num ** 2

    print(numbers)

.. admonition:: Fix the program ...

   - Run the above activecode and notice that even though we calculate the squares of the numbers in the list, **the elements in the list are not changed**. This is an example of where we must traverse the list by index.

   - Edit line 4 to iterate over the indicies of the list (don't change ``num`` but use a range like shown in activecode lir).

   - Edit line 5 to use ``num`` as an index to the ``numbers`` list (do this on both sides of the = sign).

   - Run and you will see now contains the values ``[1, 4, 9, 25, 64]``.

Take a moment to think about ``range(len(numbers))`` until you understand how it works. We are interested here in both the *value* and its *index* within the list, so that we can assign a new value to it.


    
    
    

**Check your understanding**

.. mchoice:: mc9r
   :answer_a: Error, i is an integer and does not understand the upper method.
   :answer_b: Error, upper is not a list method - it is a string method.
   :answer_c: ["APPLE", "ORANGE", "BANANA", "CHERRY"]
   :correct: c
   :feedback_a: i is used as an index into the list.
   :feedback_b: upper is used on a list element, not on the list.
   :feedback_c: Yes, the for loop processes each item of the list making an upper case string and reassigning it to the same location in the list.
   
   What is printed by the following statements?
   
   .. code-block:: python

     fruits = ["apple", "orange", "banana", "cherry"]
     for i in range(len(fruits)):
         fruits[i] = fruits[i].upper()
     print(fruits)





