..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-26-
   :start: 1

.. index:: tuple; composition, heterogeneous

Composition and Tuples
----------------------

Just like lists, the individual elements in a tuple can be of any type. This enables us to construct nested tuples.

For example, we could improve the information about our movie stars to hold the full date of birth rather than just the year, and we could have a list of some of her movies and dates that they were made, and so on:


.. activecode:: tdg2

   actress = ( ("Julia", "Roberts"), (8, "October", 1967),
               [ ("Duplicity", 2009),
                 ("Notting Hill", 1999),
                 ("Pretty Woman", 1990),
                 ("Erin Brockovich", 2000),
                 ("Eat Pray Love", 2010),
                 ("Mona Lisa Smile", 2003)],
               ("Atlanta", "Georgia") )
   
   print(type(actress[1]))
   print(actress[1])

Notice in this case that the tuple has just four elements, but each of those in turn can be another tuple, a list, or any other kind of Python value. This property is known as being **heterogeneous**, meaning that it can be composed of elements of different types.

.. admonition:: Extend the program ...

   - On line 13, make a loop that iterates over her list of movies.

   - On line 14 (the body of the loop), display only the title of the movie. Run.

   - On line 12, append the movie ('Oceans Twelve', 2004) to the list. Run and notice that, even though the tuple is immutable, we can change its list which is mutable.


