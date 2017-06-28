..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: turtle-8-
   :start: 1

.. index:: range function

The range Function
------------------

.. video:: advrange
   :controls:
   :thumb: ../_static/advrange.png

   http://media.interactivepython.org/thinkcsVideos/AdvancedRange.mov
   http://media.interactivepython.org/thinkcsVideos/AdvancedRange.webm

In our simple example from the last section (shown again below), we used a list of four integers to cause the iteration
to happen four times.  We said that we could have used any four values.  In fact, we even used four colors.

.. sourcecode:: python

   import turtle            # set up alex
   wn = turtle.Screen()
   alex = turtle.Turtle()

   for i in [0, 1, 2, 3]:   # repeat four times
       alex.forward(50)
       alex.left(90)

   wn.exitonclick()

It turns out that generating a sequence with a specific number of integers is a very common thing to do, especially when you
want to write simple ``for loop`` controlled iteration.  Even though you can use any four items, or any four integers for that matter, the conventional thing to do is to use a sequence of integers starting with 0.
In fact, these sequences are so popular that Python gives us special built-in ``range`` objects
that can deliver a sequence of values to
the ``for`` loop.  When called with one parameter, the sequence provided by ``range`` always starts with 0.  If you ask for ``range(4)``, then you will get 4 values starting with 0.  In other words, 0, 1, 2, and finally 3.  Notice that 4 is not included since we started with 0.  Likewise, ``range(10)`` provides 10 values, 0 through 9.

.. sourcecode:: python

      for i in range(4):
          # Executes the body with i = 0, then 1, then 2, then 3
      for x in range(10):
          # sets x to each of ... [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

.. note::

    Computer scientists like to count from 0!


So to repeat something four times, a good Python programmer would do this:

.. sourcecode:: python

    for i in range(4):
        alex.forward(50)
        alex.left(90)


The `range <http://docs.python.org/py3k/library/functions
.html?highlight=range#range>`_ function is actually a very powerful function
when it comes to
creating sequences of integers.  It can take one, two, or three parameters.  We have seen
the simplest case of one parameter such as ``range(4)`` which creates ``[0, 1, 2, 3]``.
But what if we really want to have the sequence ``[1, 2, 3, 4]``?
We can do this by using a two parameter version of ``range`` where the first parameter is the starting point and the second parameter is the ending point.  The evaluation of ``range(1,5)`` produces the desired sequence.  What happened to the 5?
In this case we interpret the parameters of the range function to mean
range(start,beyondLast), where beyondLast means an index past the last index we want.  In the 2-parameter version
of range, that is the last index included + 1.


.. note::

    Why in the world would range not just work like range(start,
    stop)?  Think about it like this.  Because computer scientists like to
    start counting at 0 instead of 1, ``range(N)`` produces a sequence of
    things that is N long, but the consequence of this is that the final
    number of the sequence is N-1.  In the case of start,
    stop it helps to simply think that the sequence begins with start and
    continues as long as the number is less than stop.

Here are a two examples for you to run. (It is rare in a program to print a range. But to do so, we nest the ``range`` in a ``list`` constructor.)


.. activecode:: tgh
    :nocanvas:

    print(list(range(4)))
    print(list(range(1, 5)))


.. admonition:: Extend the program ...

   On line 3, type a similar instruction to create a sequence starting at 10 and going up to 20 (including 20).

Codelens will help us to further understand the way range works.  In this case, the variable ``i`` will take on values
produced by the ``range`` function.

.. codelens:: rangeme

    for i in range(10):
       print(i)



Finally, suppose we want to have a sequence of even numbers.
How would we do that?  Easy, we add another parameter, a step,
that tells range what to count by.  For even numbers we want to start at 0
and count by 2's.  So if we wanted the first 10 even numbers we would use
``range(0,19,2)``.  The most general form of the range is
``range(start, beyondLast, step)``.  You can also create a sequence of numbers that
starts big and gets smaller by using a negative value for the step parameter.

.. activecode:: tgi
    :nocanvas:

    print(list(range(0, 19, 2)))
    print(list(range(0, 20, 2)))


    print(list(range(10, 0, -1)))



.. admonition:: Extend the program ...

   - On line 3, type a comment explaining why the first two statements produce the same result.
   - On line 4, type a similar instruction to display the **odd** numbers between 0 and 20.


Try it in codelens.
 
.. codelens:: rangeme2
 
    for i in range(10, 0, -1):
        print(i)


**Check your understanding**

.. mchoice:: mc3k
  :answer_a: Range should generate a list that stops before 10.
  :answer_b: Range should generate a list that starts at 10 (including 10).
  :answer_c: Range should generate a list that stops at 10 (including 10).
  :answer_d: Range should generate a list using every 10th number between the start and the stopping number.
  :correct: a
  :feedback_a: Range will generate the sequence 3, 5, 7, 9.
  :feedback_b: The first argument (3) tells range what number to start at.
  :feedback_c: Range will always stop at the number before (not including) the specified ending point for the sequence.
  :feedback_d: The third argument (2) tells range how many numbers to skip between each element in the sequence.

  In the command range(3, 10, 2), what does the second argument (10) specify?

.. mchoice:: mc3l
  :answer_a: range(2, 5, 8)
  :answer_b: range(2, 8, 3)
  :answer_c: range(2, 10, 3)
  :answer_d: range(8, 1, -3)
  :correct: c
  :feedback_a: This command generates a sequence with just the number 2 because the first parameter (2) tells range where to start, the second parameter tells range where to end (before 5) and the third parameter tells range how many numbers to skip between elements (8).  Since 10 >= 5, there is only one number in this sequence.
  :feedback_b: This command generates the sequence 2, 5 because 8 is not less than 8 (the beyondLast parameter).
  :feedback_c: The first parameter is the starting point, the second is the beyondLast parameter, and the third is the amount to increment by.
  :feedback_d: This command generates the sequence 8, 5, 2 because it starts at 8, ends before 1, and steps by 3 going down.

  What command correctly generates the sequence 2, 5, 8?

.. mchoice:: mc3m
  :answer_a: It will generate a sequence starting at 0, with every number included up to but not including the argument it was passed.
  :answer_b: It will generate a sequence starting at 1, with every number up to but not including the argument it was passed.
  :answer_c: It will generate a sequence starting at 1, with every number including the argument it was passed.
  :answer_d: It will cause an error: range always takes exactly 3 arguments.
  :correct: a
  :feedback_a: Yes, if you only give one number to range it starts with 0 and ends before the number specified incrementing by 1.
  :feedback_b: Range with one parameter starts at 0.
  :feedback_c: Range with one parameter starts at 0, and never includes its ending element (which is the argument it was passed).
  :feedback_d: If range is passed only one argument, it interprets that argument as the end of the list (not inclusive).

  What happens if you give range only one argument?  For example: range(4)

.. mchoice:: mc3n
  :answer_a: range(5, 25, 5)
  :answer_b: range(20, 3, -5)
  :answer_c: range(20, 5, 4)
  :answer_d: range(20, 5, -5)
  :correct: b
  :feedback_a: The step 5 is positive, while the given sequence is decreasing.  This answer creates the reversed, increasing sequence.
  :feedback_b: Yes: If we take steps of -5, not worrying about the ending, we get 20, 25, 10, 5, 0, .... The limit 3 is past the 5, so the range sequence stops with the 5. 
  :feedback_c: The step 5 is positive so the sequence would need to increase from 20 toward 4.  That does not make sense and the sequence would be empty.
  :feedback_d: the sequence can never include the second parameter (5).  The second parameter must always be past the end of the range sequence.

  Which range function call will produce the sequence 20, 15, 10, 5?


.. mchoice:: mc3o
  :answer_a: No other value would give the same sequence.
  :answer_b: The only other choice is 14.
  :answer_c: 11, 13, or 14 
  :correct: c
  :feedback_a: The sequence produced has steps of 4: 2, 6, 10.  The next would be 14, but it is not before the limit 12.  There are other limit choices past 10, but not past 14. 
  :feedback_b: 14 would work:  It is also past 10, and not past 14, but there are other integers with the same properties. 
  :feedback_c: Yes, any integer past 10, and not past the next step at 14 would work.
  
  What could the second parameter (12) in range(2, 12, 4) be replaced with and generate exactly the same sequence?


