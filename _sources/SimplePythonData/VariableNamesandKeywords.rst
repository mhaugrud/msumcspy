..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: data-5-
   :start: 1

.. index:: reserved word, underscore, identifier, case sensitive

Variable Names
--------------

**Variable names** or **identifers** can be arbitrarily long. They can contain letters (UPPER and lower case), digits, and the underscore character ( ``_``). They **must** begin with a letter or an underscore. Remember that Python is **case sensitive**, that is case matters. ``Bruce`` and ``bruce`` are different variables.

Although it is legal to use only uppercase letters in a name, by convention we don't unless the variable is used as a constant value. For example, ``FEET_PER_MILE = 5280``.

.. caution::

   Variable names can never contain spaces.

The underscore character is often used in names with multiple words, such as ``my_name`` or ``price_of_tea_in_china``.
There are some situations in which names beginning with an underscore have special meaning, so a safe rule for beginners is to start all names with a letter.

If you give a variable an illegal name, you get a syntax error.  In the example below, each of the variable names is illegal.

.. activecode:: sdn

    76trombones = "big parade"
    more$ = 1000000
    class = "Computer Science 101"
    print(76trombones, more$, class)


``76trombones`` is illegal because it does not begin with a letter.  ``more$`` is illegal because it contains an illegal character, the dollar sign. But what's wrong with ``class``?

It turns out that ``class`` is one of the Python **reserved words**. Reserved words define the language's syntax rules and structure, and they cannot be used as variable names.

.. admonition:: Fix the error ...

   Change the three variable names to legal names.

Python has thirty-something reserved words (and every now and again improvements to Python introduce or eliminate one or two):

======== ======== ======== ======== ======== ========
and      as       assert   break    class    continue
def      del      elif     else     except   exec
finally  for      from     global   if       import
in       is       lambda   nonlocal not      or
pass     raise    return   try      while    with
yield    True     False    None
======== ======== ======== ======== ======== ========

You might want to keep this list handy. If the interpreter complains about one of your variable names and you don't know why, see if it is on this list.

.. note::
   Computer scientists choose names for their variables that are **meaningful** to the human readers of the program --- they help the programmer document, or remember, what the variable is used for.

.. caution::

    Beginners sometimes confuse "meaningful to the human readers" with
    "meaningful to the computer".  So they'll wrongly think that because
    they've called some variable ``average`` or ``pi``, it will somehow
    automagically calculate an average, or automagically associate the variable
    ``pi`` with the value 3.14159.  No! The computer doesn't attach semantic
    meaning to your variable names.

    So you'll find some instructors who deliberately don't choose meaningful
    names when they teach beginners --- not because they don't think it is a
    good habit, but because they're trying to reinforce the message that you,
    the programmer, have to write some program code to calculate the average,
    or you must write an assignment statement to give a variable the value you
    want it to have.

**Check your understanding**

.. mchoice:: mc2e
   :answer_a: True
   :answer_b: False
   :correct: b
   :feedback_a: -  The + character is not allowed in variable names.
   :feedback_b: -  The + character is not allowed in variable names (everything else in this name is fine).

   True or False:  the following is a legal variable name in Python:   A_good_grade_is_A+



