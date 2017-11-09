..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-12-
   :start: 1

.. index:: clone, list; clone

Cloning Lists
-------------

If we want to modify a list and also keep a copy of the original, we need to be
able to make a copy of the list itself, not just the reference.

.. activecode:: li00
    
    a = [81, 82, 83]

    b = a
    print(a == b)
    print(a is b)

    b[0] = 5

    print(a)
    print(b)

.. admonition:: Edit the code ...

   When you run this activecode, you will see that changing an element in ``b`` affects ``a``. This is because ``b`` is an alias of ``a``.

   Change line 3 to ``b = [:]``. Now, when you run, notice ``a`` is no longer affected.

This process is sometimes called **cloning**, to avoid the ambiguity of the word copy.

The easiest way to clone a list is to use the slice operator.

Taking any slice of ``a`` creates a new list. In this case the slice happens to
consist of the whole list.

Now we are free to make changes to ``b`` without worrying about ``a``.  We can clearly see that ``a`` and ``b`` are entirely different list objects.


