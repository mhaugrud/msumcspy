..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-29-
   :start: 1

.. index:: enumerate

Iterables and Enumerate
-----------------------

We have seen that we can iterate over the elements of the various Python collections such as strings, lists, and tuples. For that reason, these collection are called **iterables**. The simplest way to iterate is use a ``for`` loop and iterate by item. However, there are circumstances where we need to iterate by index even though it is more complicated. 

``enumerate`` gives us a way to iterate by item but still have access to the index. ``enumerate`` constructs ``(index, value)`` tuples for each item in the collection. We can then iterate over this collection of tuples by item.

.. activecode:: tdh

   for (index, ch) in enumerate("Crunchy Frog"):
       print(index, ch)

   julia = ("Julia", "Roberts", 1967, "Pretty Woman", 1990, "Actress", "Atlanta, Georgia")
   for (idx, field) in enumerate(julia):
       print(idx, field)

   fruit = ["apple", "orange", "banana", "cherry"]
   for (i, f) in enumerate(fruit):
       fruit[i] = f.upper()

   print(fruit)
       
   




