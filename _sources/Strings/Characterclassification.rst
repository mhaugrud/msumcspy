..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: strings-17-
   :start: 1

Character classification
------------------------

It is often helpful to examine a character and test whether it is upper- or lowercase, or whether it is a character or a digit. The ``string`` module provides several constants that are useful for these purposes. One of these, ``string.digits`` is equivalent to "0123456789".  It can be used to check if a character is a digit using the ``in`` operator.

The string ``string.ascii_lowercase`` contains all of the ascii letters that the system considers to be lowercase. Similarly, ``string.ascii_uppercase`` contains all of the uppercase letters. ``string.punctuation`` comprises all the characters considered to be punctuation. Finally ``string.whitespace`` contains *invisible* characters like space, tab, and new line.

.. sourcecode:: python
    
    print(string.ascii_lowercase)
    print(string.ascii_uppercase)
    print(string.digits)
    print(string.punctuation)
    print(string.whitespace)

    

For more information consult the ``string`` module documentaiton (see `Global Module Index <http://docs.python.org/py3k/py-modindex.html>`_).



.. activecode:: scratch_08_04

   import string


.. admonition:: Modify the program ...

   Starting on line 2, print the five character sets (nothing will show for whitespace).


