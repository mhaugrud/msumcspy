..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: iter-8-
   :start: 1

Simple Tables
-------------

One of the things loops are good for is generating tabular data.  Before
computers were readily available, people had to calculate logarithms, sines and
cosines, and other mathematical functions by hand. To make that easier,
mathematics books contained long tables listing the values of these functions.
Creating the tables was slow and boring, and they tended to be full of errors.

When computers appeared on the scene, one of the initial reactions was, *"This is
great! We can use the computers to generate the tables, so there will be no
errors."* That turned out to be true (mostly) but shortsighted. Soon thereafter,
computers and calculators were so pervasive that the tables became obsolete.

Well, almost. For some operations, computers use tables of values to get an
approximate answer and then perform computations to improve the approximation.
In some cases, there have been errors in the underlying tables, most famously
in the table the Intel Pentium processor chip used to perform floating-point division.

Although a power of 2 table is not as useful as it once was, it still makes a good
example of iteration. The following program outputs a sequence of values in the
left column and 2 raised to the power of that value in the right column:

.. activecode:: ch07_table1

                                 #
                                 #
    
    print("n", '\t', "2**n")     #table column headings
    print("---", '\t', "-----")

    for x in range(13):          #generate values for columns
        print(x, '\t', 2 ** x)

The string ``'\t'`` represents a **tab character**. The backslash character in ``'\t'`` indicates the beginning of an **escape sequence**.  Escape sequences are used to represent invisible characters like tabs and newlines. The sequence ``\n`` represents a **newline**.

.. admonition:: Modify the program ...

   - On line 1, define a function that has one parameter ``n``.
   - On line 2, write its body: It returns ``2 ** n``.
   - Edit line 8 to call your function with ``x``.
   - The same table will be produced as before.

An escape sequence can appear anywhere in a string.  In this example, the tab escape sequence is the only thing in the string. How do you think you represent a backslash in a string?

As characters and strings are displayed on the screen, an invisible marker called the **cursor** keeps track of where the next character will go. After a ``print`` function is executed, the cursor normally goes to the beginning of the next
line.

The tab character shifts the cursor to the right until it reaches one of the tab stops. Tabs are useful for making columns of text line up, as in the output of the previous program.
Because of the tab characters between the columns, the position of the second column does not depend on the number of digits in the first column.




.. index::
    single: local variable
    single: variable; local

**Check your understanding**

.. mchoice:: test_question7_7_1
  :answer_a: A tab will line up items in a second column, regardless of how many characters were in the first column, while spaces will not.
  :answer_b: There is no difference
  :answer_c: A tab is wider than a sequence of spaces
  :answer_d: You must use tabs for creating tables.  You cannot use spaces.
  :correct: a
  :feedback_a: Assuming the size of the first column is less than the size of the tab width.
  :feedback_b: Tabs and spaces will sometimes make output appear visually different.
  :feedback_c: A tab has a pre-defined width that is equal to a given number of spaces.
  :feedback_d: You may use spaces to create tables.  The columns might look jagged, or they might not, depending on the width of the items in each column.

  What is the difference between a tab (``'\t'``) and a sequence of spaces?

Nested Iteration
^^^^^^^^^^^^^^^^

Nested iteration simply means that we will place one iteration construct inside of another.  We will call these two
iterations the **outer iteration** and the **inner iteration**.
To see how this works, consider the iteration below.

.. sourcecode:: python

    for i in range(5):
        print(i)

We have seen this enough times to know that the value of ``i`` will be 0, then 1, then 2, and so on up to 4.
The ``print`` will be performed once for each pass.
However, the body of the loop can contain any statements including another iteration (another ``for`` statement).  For example,

.. sourcecode:: python

    for i in range(5):
        for j in range(3):
            print(i, j)

The ``for i`` iteration is the `outer iteration` and the ``for j`` iteration is the `inner iteration`.  Each pass through
the outer iteration will result in the complete processing of the inner iteration from beginning to end.  This means that
the output from this nested iteration will show that for each value of ``i``, all values of ``j`` will occur.

Here is the same example in activecode.  Try it.  Note that the value of ``i`` stays the same while the value of ``j`` changes.  The inner iteration, in effect, is moving faster than the outer iteration.

.. activecode:: nested1

    for i in range(5):
        for j in range(3):
            print(i, j)

Another way to see this in more detail is to examine the behavior with codelens.  Step through the iterations to see the
flow of control as it occurs with the nested iteration.  Again, for every value of ``i``, all of the values of ``j`` will occur.  You can see that the inner iteration completes before going on to the next pass of the outer iteration.

.. codelens:: nested2

    for i in range(5):
        for j in range(3):
            print(i, j)


**Check your understanding**

.. mchoice:: test_question7_8_3_1
   :answer_a: Output a
   :answer_b: Output b
   :answer_c: Output c
   :answer_d: Output d
   :correct: a
   :feedback_a: i will start with a value of 0 and then j will iterate from 0 to 1.  Next, i will be 1 and j will iterate from 0 to 1.  Finally, i will be 2 and j will iterate from 0 to 1.
   :feedback_b: The inner for-loop controls the second digit (j).  The inner for-loop must complete before the outer for-loop advances.
   :feedback_c: The inner for-loop controls the second digit (j).  Notice that the inner for-loop is over the list [0, 1].
   :feedback_d: The outer for-loop runs 3 times (0, 1, 2) and the inner for-loop runs twice for each time the outer for-loop runs, so this code prints exactly 6 lines.

   What will the following nested for-loop print?  (Note, if you are having trouble with this question, review CodeLens 3).

   .. code-block:: python

      for i in range(3):
          for j in range(2):
              print(i, j)

   ::

      a.

      0	0
      0	1
      1	0
      1	1
      2	0
      2	1

      b.

      0   0
      1   0
      2   0
      0   1
      1   1
      2   1

      c.

      0   0
      0   1
      0   2
      1   0
      1   1
      1   2

      d.

      0   1
      0   1
      0   1


