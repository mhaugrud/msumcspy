..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-16-
   :start: 1

Append Versus Concatenate
-------------------------

The ``append`` method adds a new item to the end of a list.  It is also possible to add a new item to the 
end of a list by using the concatenation operator.  However, you need to be careful.

Consider the following example.  The original list has 3 integers.  We want to add the word "cat" to the 
end of the list.

.. activecode:: li4a

    origlist = [45, 32, 88]
    print(origlist)

    origlist.append("cat")
    print(origlist)



Here we have used ``append`` which simply modifies the list.  In order to use concatenation, we need to 
write an assignment statement that uses the accumulator pattern::

    origlist = origlist + ["cat"]

Note that the word "cat" needs to be placed in a list since the concatenation operator needs two lists 
to do its work.

.. activecode:: li4b

    origlist = [45, 32, 88]
    print(origlist)

    origlist = origlist + ["cat"]
    print(origlist)

It is also important to realize that with ``append``, the original list is simply modified.  
On the other hand, with concatenation, an entirely new list is created.

.. admonition:: Prove it ...

   - Return to activecode 1, at the top of this page. On lines 3 and 6, type ``print(id(origlist))`` 
   and run. ``id`` is a function that reports where in memory an item is stored. You will see ``id``
   produces the same number in each case, indicating ``origlist`` we did not create a new list.
   - Return to activecode 2. On lines 3 and 6, type ``print(id(origlist))`` and run. Notice ``id``
   produces different numbers in the two cases, indicating a new list was created.

   The point is that ``append`` is a much more efficient operation and thus should be used instead
   of concatenation (unless we actually want a new list).



**Check you understanding**

.. mchoice:: mc9w
   :answer_a: [4, 2, 8, 6, 5, 999]
   :answer_b: Error, you cannot concatenate a list with an integer.
   :correct: b
   :feedback_a: You cannot concatenate a list with an integer.
   :feedback_b: Yes, in order to perform concatenation you would need to write alist+[999].  You must have two lists.
   
   What is printed by the following statements?
   
   .. code-block:: python

     alist = [4, 2, 8, 6, 5]
     alist = alist + 999
     print(alist)


