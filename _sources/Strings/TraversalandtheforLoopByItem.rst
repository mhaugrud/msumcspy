..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: strings-10-
   :start: 1

.. index:: traversal; by item

Traversal and the ``for`` Loop: By Item
---------------------------------------

A lot of computations involve processing a collection one item at a time.  For strings this means that we would like to process one character at a time. Often we start at the beginning, select each character in turn, do something to it, and continue until the end. This pattern of processing is called a **traversal**.

We have previously seen that the ``for`` statement can iterate over a sequence of integers created by the ``range`` constructor.

.. activecode:: stl
    :nocanvas:

    for avalue in range(10):
        print(avalue)
      
Recall that the loop variable takes on each value in the sequence.  The body is performed once for each value.

Since a string is simply a sequence of characters, the ``for`` loop iterates over each character automatically.


.. activecode:: stm
    :nocanvas:

    for achar in "Go Spot Go":
        print(achar)

The loop variable ``achar`` is automatically reassigned each character in the string "Go Spot Go". We will refer to this type of sequence iteration as **iteration by item**.  Note that we to process the characters one at a time from left to right.

.. activecode:: stn
    :nocanvas:

    aString = input('enter a string')
    for achar in aString:
        print(achar)


**Check your understanding**

.. mchoice:: mc8j
   :answer_a: 10
   :answer_b: 11
   :answer_c: 12
   :answer_d: Error, the for statement needs to use the range function.
   :correct: c
   :feedback_a: Iteration by item will process once for each item in the sequence.
   :feedback_b: The blank is part of the sequence.
   :feedback_c: Yes, there are 12 characters, including the blank.
   :feedback_d: The for statement can iterate over a sequence item by item.


   How many times is the word HELLO printed by the following statements?
   
   .. code-block:: python

      s = "python rocks"
      for ch in s:
          print("HELLO")

   
   
   
.. mchoice:: mc8k
   :answer_a: 4
   :answer_b: 5
   :answer_c: 6
   :answer_d: Error, the for statement cannot use slice.
   :correct: b
   :feedback_a: Slice returns a sequence that can be iterated over.
   :feedback_b: Yes, The blank is part of the sequence returned by slice
   :feedback_c: Check the result of s[3:8].  It does not include the item at index 8.
   :feedback_d: Slice returns a sequence.


   How many times is the word HELLO printed by the following statements?
   
   .. code-block:: python

      s = "python rocks"
      for ch in s[3:8]:
          print("HELLO")


