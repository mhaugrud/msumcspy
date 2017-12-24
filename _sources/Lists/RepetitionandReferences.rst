..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-13-
   :start: 1

Repetition and References
-------------------------

We have already seen the repetition operator working on strings as well as lists.  For example, 

.. activecode:: li1

    origlist = [45, 76, 34, 55]
    print(origlist * 3)

With a list, the repetition operator creates copies of the references.  Although this may seem simple 
enough, when we allow a list to refer to another list, a subtle problem can arise.

Consider the following extension on the previous example.

.. activecode:: li2

    origlist = [45, 76, 34, 55]
    print(origlist * 3)

    newlist = [origlist] * 3

    print(newlist)

``newlist`` is a list of three references to ``origlist`` that were created by the repetition operator. 
The reference diagram is shown below.



.. image:: Figures/refrep1.png
   :alt: Repetition of a nested list



.. activecode:: li3

    origlist = [45, 76, 34, 55]

    newlist = [origlist] * 3

    print(newlist)



    print(newlist)

.. admonition:: Modify the program ...

   Now, what happens if we modify a value in ``origlist``?

   - On line 7, type ``origlist[1] = 99``
   - Run and notice ``newlist`` shows the change in three places.

This can easily be seen by noting that in the reference diagram, there is only one ``origlist``, 
so any changes to it appear in all three references from ``newlist``. This is an example of 
how aliases can create subtle, hard to find semantic errors in a program.

.. image:: Figures/refrep2.png
   :alt: Same reference

Here is the same example in codelens.  Step through the code paying particular attention to the result 
of executing the assignment statement ``origlist[1] = 99``.

.. codelens:: cl_reprefstep
    :showoutput:

    origlist = [45, 76, 34, 55]

    newlist = [origlist] * 3

    print(newlist)

    origlist[1] = 99

    print(newlist)

**Check your understanding**

.. mchoice:: mc9u
   :answer_a: [4, 2, 8, 999, 5, 4, 2, 8, 6, 5]
   :answer_b: [4, 2, 8, 999, 5]
   :answer_c: [4, 2, 8, 6, 5]
   :correct: c
   :feedback_a: print(alist) not print(blist)
   :feedback_b: blist is changed, not alist.
   :feedback_c: Yes, alist was unchanged by the assignment statement. blist was a copy of the references in alist.
   
   What is printed by the following statements?
   
   .. code-block:: python

     alist = [4, 2, 8, 6, 5]
     blist = alist * 2
     blist[3] = 999
     print(alist)


.. mchoice:: mc9v
   :answer_a: [4, 2, 8, 999, 5, 4, 2, 8, 999, 5]
   :answer_b: [[4, 2, 8, 999, 5], [4, 2, 8, 999, 5]]
   :answer_c: [4, 2, 8, 6, 5]
   :answer_d: [[4, 2, 8, 999, 5], [4, 2, 8, 6, 5]]
   :correct: b
   :feedback_a: [alist] * 2 creates a list containing alist repeated 2 times
   :feedback_b: Yes, blist contains two references, both to alist.
   :feedback_c: print(blist)
   :feedback_d: blist contains two references, both to alist so changes to alist appear both times.
   
   What is printed by the following statements?
   
   .. code-block:: python

     alist = [4, 2, 8, 6, 5]
     blist = [alist] * 2
     alist[3] = 999
     print(blist)





