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

A function can only return a single value. However, we may want to return multiple values. 
We may want to know some batsman's highest and lowest score, or we want to find the mean 
and the standard deviation, or we want to know the year, the month, and the day, or, if 
we're doing some ecological modeling, we may want to know the number of deer and the number 
of wolves on an island at a given time.

Since a tuple can hold multiple elements, we can overcome this limitation by using a **tuple**
as the return value.

For example, we could write a function that returns both the area and the circumference of a circle of radius r.
In the Functions chapter, we saw how to use a tuple as a function's return value. We also saw we can unpack the tuple into simple variables.

.. activecode:: tdg

    
    def circleInfo(r):
        """ Return (circumference, area) of a circle of radius r """
        c = 2 * 3.14159 * r
        a = 3.14159 * r * r
        return (c, a)

    (circum, area) = circleInfo(10)
    print('area =', area)
    print('circumference =', circum)
    
    t = circleInfo(10)
    print(t)




.. admonition:: Extend the program ...

   In line 13, use the index operator (two times) to print the two elements of the tuple.

