..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: iter-5-
   :start: 1

The 3n + 1 Sequence
-------------------

As another example of indefinite iteration, let's look at a sequence that has fascinated mathematicians for many years.
The rule  for creating the sequence is to start from
some positive integer, call it ``n``, and to generate
the next term of the sequence from ``n``, either by halving ``n``,
whenever ``n`` is even, or else by multiplying it by three and adding 1 when it is odd.  The sequence
terminates when ``n`` reaches 1.

This Python function captures that algorithm.  Try running this program several times supplying different values for n.

.. activecode:: ch07_indef1

    def seq3np1(n):
        """ Print the 3n+1 sequence from n, terminating when it reaches 1."""
        while n != 1:
            print(n)
            if n % 2 == 0:        # n is even
                n = n // 2
            else:                 # n is odd
                n = n * 3 + 1
        print(n)                  # the last print is 1

    seq3np1(3)




The condition for this loop is ``n != 1``.  The loop will continue running until
``n == 1`` (which will make the condition false).

Each time through the loop, the program prints the value of ``n`` and then
checks whether it is even or odd using the remainder operator. If it is even, the value of ``n`` is divided
by 2 using integer division. If it is odd, the value is replaced by ``n * 3 + 1``.
Try some other examples.

Since ``n`` sometimes increases and sometimes decreases, there is no obvious
proof that ``n`` will ever reach 1, or that the program terminates. For some
particular values of ``n``, we can prove termination. For example, if the
starting value is a power of two, then the value of ``n`` will be even each
time through the loop until it reaches 1.

You might like to have some fun and see if you can find a small starting
number that needs more than a hundred steps before it terminates.



Particular values aside, the interesting question is whether we can prove that
this sequence terminates for *all* positive values of ``n``. So far, no one has been able
to prove it *or* disprove it!

Think carefully about what would be needed for a proof or disproof of the hypothesis
*"All positive integers will eventually converge to 1"*.  With fast computers we have
been able to test every integer up to very large values, and so far, they all
eventually end up at 1.  But this doesn't mean that there might not be some
as-yet untested number which does not reduce to 1.

You'll notice that if you don't stop when you reach one, the sequence gets into
its own loop:  1, 4, 2, 1, 4, 2, 1, 4, and so on.  One possibility is that there might
be other cycles that we just haven't found.



**Check your understanding**

.. mchoice:: test_question7_4_1
   :answer_a: Yes.
   :answer_b: No.
   :answer_c: No one knows.
   :correct: c
   :feedback_a: The 3n+1 sequence has not been proven to terminate for all values of n.
   :feedback_b: It has not been disproven that the 3n+1 sequence will terminate for all values of n.  In other words, there might be some value for n such that this sequence does not terminate. We just have not found it yet.
   :feedback_c: That this sequence terminates for all values of n has not been proven or disproven so no one knows whether the while loop will always terminate or not.

   Consider the code that prints the 3n+1 sequence in ActiveCode box 6.  Will the while loop in this code always terminate for any positive integer value of n?

Experimenting With the 3n+1 Sequence
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. activecode:: seq3nlab1

    def seq3np1(n):
        """ Print the 3n+1 sequence from n, terminating when it reaches 1."""

        while n != 1:
            print(n)
            if n % 2 == 0:        # n is even
                n = n // 2
            else:                 # n is odd
                n = n * 3 + 1
        print(n)                  # the last print is 1

    seq3np1(3)

.. admonition:: Extend the program ...

   - Count the number of iterations it takes to stop. Our program currently **prints** the values in the sequence until it stops at 1.  Remember that one of the interesting questions is `How many items are in the sequence before stopping at 1?`.  To determine this, we will need to count them.

      - First, comment out (or delete) the print statements that currently exist.  Now we will need a local variable to keep track of the count.  It would make sense to call it `count`.  It will need to be initialized to 0 since before we begin the loop.

      - Once inside the loop, we will need to update ``count`` by 1 (increment), so that we can keep track of the number of iterations.  It is very important that you put these statements in the right place.  Notice that the previous location of the print statements can be very helpful in determining the location.

      - When the loop terminates (we get to 1), **return** the value of ``count``.

      - This demonstrates an important pattern of computation called a **counter** (note that it is a type of accumulator). The variable ``count`` is initialized to 0 and then incremented each time the loop body is executed. When the loop exits, ``count`` contains the result --- the total number of times the loop body was executed.

      - Since the function now returns a value, we will need to call the function inside of a print statement in order to see the result.

   - Repeat the call to ``seq3np1`` using a range of values, up to and including an upper bound.

      - Now that we have a function that can return the number of iterations required to get to 1, we can use it to check a wide range of starting values.  In fact, instead of just doing one value at a time, we can call the function iteratively, each time passing in a new value.

      - Create a simple for loop using a loop variable called ``start`` that provides values from 1 up to 50.  Call the ``seq3np1`` function once for each value of ``start``.  Modify the print statement to also print the value of ``start``.



