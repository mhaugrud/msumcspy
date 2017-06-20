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

.. index:: list; traversal, traversal; by item

.. _list_traverse:

List Traversal by Item
----------------------

We can perform **list traversal** by iterating over the items in a list.


.. activecode:: lik

    fruits = ["apple", "orange", "banana", "cherry"]

    for afruit in fruits:     # by item
        print(afruit)

It almost reads like natural language: For (every) fruit in (the list of) fruits, print (the name of the) fruit.

.. admonition:: Extend the program ...

   - On line 5, make a **nested** loop to iterate over the characters in ``afruit``.

   - On line 6, print the current character from ``afruit``.
