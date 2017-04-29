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

Tuples as Return Values
-----------------------

A function can only return a single value. However, we may want to return multiple values. We may want to
know some batsman's highest and lowest score, or we want to find the mean and the standard 
deviation, or we want to know the year, the month, and the day, or, if we're doing
some ecological modeling, we may want to know the number of rabbits and the number
of wolves on an island at a given time.

We can overcome this limitation by using a tuple as the return value.  A tuple is a group of items, separated by commas, and surrounded by parentheses. For example, (9,11,2001) or ('December',25).  A single tuple can hold multiple elements. 

For example, we could write a function that returns both the area and the circumference
of a circle of radius r.

.. activecode:: chp09_tuple3

    
    def circleInfo(r):
        """ Return (circumference, area) of a circle of radius r """
        c = 2 * 3.14159 * r
        a = 3.14159 * r * r
        return (c, a)

    result = circleInfo(10)
    (circum, area) = circleInfo(10)
    print(result, circum, area)




.. note::

    This workspace is provided for your convenience.  You can use this activecode window to try out anything you like.

    .. activecode:: scratch_09_07

