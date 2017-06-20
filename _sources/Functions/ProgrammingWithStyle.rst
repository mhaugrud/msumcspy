..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. index:: style, readability, pythonic, docstring

Programming With Style
----------------------

**Readability** is very important to programmers, since in practice programs are read and modified far more often then they are written.  

.. All the code examples
.. in this book will be consistent with the *Python Enhancement Proposal 8*
.. (`PEP 8 <http://www.python.org/dev/peps/pep-0008/>`__), a style guide developed by the Python community.

We'll have more to say about style as our programs become more complex, but here are a few general rules:

* all statements should be within a function
* use 4 spaces for indentation
* imports should all go at the top of the file
* keep function definitions together
* use blank lines to separate logical sections of a program (function definitions, algorithm steps, etc.)
* keep top level statements, including function calls, together at the bottom of the program

**Pythonic** is a term that means *in the spirit of the Python programming language*.
If we program in Python, we should use the language in the way its designers intended.
Here are some links on writing Pythonic programs.

* `The Zen of Python <https://www.python.org/dev/peps/pep-0020/>`_.
* `Style Guide for Python <https://www.python.org/dev/peps/pep-0008/>`_.
* `Docstring Conventions <https://www.python.org/dev/peps/pep-0257/>`_.
