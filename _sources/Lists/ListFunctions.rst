..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-22-
   :start: 1

.. index:: list; functions, min, max, sum

List Functions
--------------

We have frequently used the ``len`` function. Python has several similar functions that take a list (actually any type collection that is iterable) as an argument. These functions evaluate the elements of the collection and produce some statistic.

======  ===========
Name    Description
======  ===========
len     the number of items in the collection 
sum     the total of the elements in the collection
max     the largest value in the collection
min     the smallest value in the collection
all     are all the values in the collection True?
any     is at least one value in the collection True?
======  ===========


.. activecode:: li6

    mylist = [6,3,1,5,8,7]
    print(max(mylist))



    boolist = [False,True,True,True]
    print(all(boolist))



.. admonition:: Extend the program ...

   - On line 3, use a list function to display the smallest value in the list
   - On line 4, use a list function to display the total of the values in the list
   - On line 8, use a list function to display whether at least one value in the list is True
   - On line 7, pass a **slice** that includes all but the first element of boolist (the result will now be True)

