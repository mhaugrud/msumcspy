..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-28-
   :start: 1

.. index:: tuple; returning

Tuples as Return Values
-----------------------

In the Functions chapter, we saw how to use a tuple as a function's return value. We also saw we can unpack the tuple into simple variables.

.. activecode:: tdg

    
    def circleInfo(r):
        """ Return (circumference, area) of a circle of radius r """
        c = 2 * 3.14159 * r
        a = 3.14159 * r * r
        return (c, a)

    (circum, area) = circleInfo(10)
    print(circum, area)
    
    t = circleInfo(11)
    print(t)




.. admonition:: Extend the program ...

   In line 11, use the index operator (two times) to print the two elements of the tuple.

.. note::
   This workspace is provided for your convenience. You can use this activecode window to try out anything you like.

   .. activecode:: tdh

