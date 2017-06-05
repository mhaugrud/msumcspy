..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: list-25-
   :start: 1

``list`` Type Constructor Function
----------------------------------
    
Python has a built-in type constructor function called 
``list`` that tries to make a list from whatever you give it.  For example, try the following:

.. activecode:: lix
    
    xs = list("Crunchy Frog")
    print(xs)


A list is made from the string "Crunchy Frog" by taking each character in the string and placing it in a list.  In general, any sequence can be turned into a list using this function.  The result will be a list containing the elements in the original sequence.  It is not legal to use the ``list`` constructor function on any argument that is not a sequence.

It is also important to point out that the ``list`` constructor function will place each element of the original sequence in the new list.  When working with strings, this is very different than the result of the ``split`` method.  Whereas ``split`` will break a string into a list of "words", ``list`` will always break it into a list of characters.
    
