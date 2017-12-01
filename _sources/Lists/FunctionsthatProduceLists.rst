..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-21-
   :start: 1

.. index:: list; accumulator, accumulator pattern

Functions That Produce Lists
----------------------------

The pure version of ``doubleStuff`` above made use of an 
important **pattern** for your toolbox. Whenever you need to
write a function that creates and returns a list, the pattern is
usually::

    initialize a result variable to be an empty list
    loop
       create a new element 
       append it to result
    return the result

Once again we see our accumulator pattern!

Let us show another use of this pattern.  Assume you already have a function
``is_prime(x)`` that can test if x is prime.  Now, write a function
to return a list of all prime numbers less than n::

   def primes_upto(n):
       """ Return a list of all prime numbers less than n. """
       result = []
       for i in range(2, n):
           if is_prime(i):
               result.append(i)
       return result


**Check your understanding**

.. mchoice:: mc9rr
   :answer_a: [4, 2, 8, 6, 5]
   :answer_b: [4, 2, 8, 6, 5, 5]
   :answer_c: [9, 7, 13, 11, 10]
   :answer_d: Error, you cannot concatenate inside an append.
   :correct: c
   :feedback_a: 5 is added to each item before the append is peformed.
   :feedback_b: There are too many items in this list.  Only 5 append operations are performed.
   :feedback_c: Yes, the for loop processes each item of the list.  5 is added before it is appended to blist.
   :feedback_d: 5 is added to each item before the append is performed.
   
   What is printed by the following statements?
   
   .. code-block:: python

     alist = [4, 2, 8, 6, 5]
     blist = [ ]
     for item in alist:
         blist.append(item+5)
     print(blist)



.. activecode:: liv
    
    numbers = [1, 2, 3, 5, 8]
    squares = []


    print(squares)

.. admonition:: Modify the program ...

   Type instructions on lines 3 and 4 that use the list accumulator pattern to fill the ``squares`` list with the squares of ``numbers``.

