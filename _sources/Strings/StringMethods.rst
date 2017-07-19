..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: strings-5-
   :start: 1

.. index:: string; method, dot notation

``string`` Methods
------------------

We previously saw that each turtle instance has its own attributes and 
a number of methods that can be applied to the instance.  For example,
we wrote ``tess.right(90)`` when we wanted the turtle object ``tess`` to perform the ``right`` method to turn
to the right 90 degrees.  The "dot notation" is the way we connect the name of an object to the name of a method
it can perform.  

Strings are also objects.  Each string instance has its own attributes and methods.  The most important attribute of the string is the collection of characters.  There are a wide variety of methods.  Try the following program.

.. activecode:: stv

    ss = "Hello, World"
    print('line 2:', ss.upper())

    tt = ss.lower()
    print('line 4:', tt)


In this example, ``upper`` is a method that can be invoked on any string object to create a new string in which all the 
characters are in uppercase.  ``lower`` works in a similar fashion changing all characters in the string to lowercase.  (The original string ``ss`` remains unchanged.  A new string ``tt`` is created.)

.. admonition:: Modify the program ...

   - In line 1, change ``Hello World`` to your full name.

   - On lines 3 and 6, print the string ``ss``. Notice it does not change. Remember **strings are immutable**.


In addition to ``upper`` and ``lower``, the following table provides a summary of some other useful string methods.  There are a few activecode examples that follow so that you can try them out.

==========  ==============      ==================================================================
Method      Parameters          Description
==========  ==============      ==================================================================
upper       none                Returns a string in all uppercase
lower       none                Returns a string in all lowercase
capitalize  none                Returns a string with first character capitalized, the rest lower

strip       none                Returns a string with the leading and trailing whitespace removed
lstrip      none                Returns a string with the leading whitespace removed
rstrip      none                Returns a string with the trailing whitespace removed
count       item                Returns the number of occurrences of item
replace     old, new            Replaces all occurrences of old substring with new

center      width               Returns a string centered in a field of width spaces
ljust       width               Returns a string left justified in a field of width spaces
rjust       width               Returns a string right justified in a field of width spaces

find        item                Returns the leftmost index where the substring item is found
rfind       item                Returns the rightmost index where the substring item is found
index       item                Like find except causes a runtime error if item is not found
rindex      item                Like rfind except causes a runtime error if item is not found
==========  ==============      ==================================================================

You should experiment with these
methods so that you understand what they do.  Note once again that the methods that return strings do not
change the original.  You can also consult the `Python documentation for strings <http://docs.python.org/py3k/library/stdtypes.html#index-21>`_.

.. activecode:: stw

    ss = "    Hello, World    "

    els = ss.count("l")
    print(els)

    print("***" + ss.strip() + "***")
    print("***" + ss.lstrip() + "***")
    print("***" + ss.rstrip() + "***")

    news = ss.replace("o", "***")
    print(news)


.. activecode:: stx


    food = "banana bread"
    print(food.capitalize())
    size = 25
    print("*" + food.center(size) + "*")
    print("*" + food.ljust(size) + "*")     # stars added to show bounds
    print("*" + food.rjust(size) + "*")

    print('line  8:', food.find("e"))
    print('line  9:', food.find("na"))
    print('line 10:', food.find("b"))

    print('line 12:', food.rfind("e"))
    print('line 13:', food.rfind("na"))
    print('line 14:', food.rfind("b"))

    print('line 16:', food.index("e"))

.. admonition:: Modify the program ...

   - On line 11, type a line similar to line 10 that results in ``6`` being displayed.

   - On line 7, make a string from the interger variable ``size`` (recall how you can make a string from an integer with ``str``). Use the rjust method on that string to right justify it in a field 5 characters wide and print the resulting string. Notice the number 25 is preceded by 3 spaces.


**Check your understanding**

.. mchoice:: mc8m
   :answer_a: 0
   :answer_b: 2
   :answer_c: 3
   :correct: c
   :feedback_a: There are definitely o and p characters.
   :feedback_b: There are 2 o characters but what about p?
   :feedback_c: Yes, add the number of o characters and the number of p characters.


   What is printed by the following statements?
   
   .. code-block:: python
   
      s = "python rocks"
      print(s.count("o") + s.count("p"))




.. mchoice:: mc8n
   :answer_a: yyyyy
   :answer_b: 55555
   :answer_c: n
   :answer_d: Error, you cannot combine all those things together.
   :correct: a
   :feedback_a: Yes, s[1] is y and the index of n is 5, so 5 y characters.  It is important to realize that the index method has precedence over the repetition operator.  Repetition is done last.
   :feedback_b: Close.  5 is not repeated, it is the number of times to repeat.
   :feedback_c: This expression uses the index of n
   :feedback_d: This is fine, the repetition operator used the result of indexing and the index method.


   What is printed by the following statements?
   
   .. code-block:: python
   
      s = "python rocks"
      print(s[1] * s.index("n"))


