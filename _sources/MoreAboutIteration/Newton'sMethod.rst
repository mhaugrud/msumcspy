..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: iter-6-
   :start: 1

.. index:: Newton

Newton's Method
---------------

Loops are often used in programs that compute numerical results by starting with an approximate answer and iteratively improving it.

For example, one way of computing square roots is Newton's method.  Suppose that you want to know the square root of ``n``. If you start with almost any approximation, you can compute a better approximation with the following formula:

.. sourcecode:: python

    better =  1/2 * (approx + n/approx)

Execute this algorithm a few times using your calculator.  Can you see why each iteration brings your estimate a little closer?  One of the amazing properties of this particular algorithm is how quickly it converges to an accurate answer.

The following implementation of Newton's method requires two parameters.  The first is the value whose square root will be approximated.  The second is the number of times to iterate the
calculation yielding a better result.

.. activecode:: itl

    def newtonSqrt(n, howmany):
        approx = 0.5 * n
        for i in range(howmany):
            betterapprox = 0.5 * (approx + n/approx)
            approx = betterapprox
        return betterapprox

    print(newtonSqrt(100, 10))
    print(newtonSqrt(4, 10))
    print(newtonSqrt(1, 10))


.. admonition:: Modify the program ...

   All three of the calls to ``newtonSqrt`` in the previous example produce the correct square root for the first parameter.  However, were 10 iterations required to get the correct answer? Experiment with different values for the number of repetitions (the 10 on lines 8, 9, and 10). For each of these calls, find the **smallest** value for the number of repetitions that will produce the **correct** result.


Repeating more than the required number of times is a waste of computing resources. So definite iteration is not a good solution to this problem.

In general, Newton's algorithm will eventually reach a point where the new approximation is no better than the previous.  At that point, we could simply stop. In other words, by repeatedly applying this formula until the better approximation gets close
enough to the previous one, we can write a function for computing the square root that uses the number of iterations necessary and no more.

This implementation, as shown below, uses a ``while`` condition to execute until the approximation is no longer changing.  Each time through the loop we compute a "better" approximation using the formula described earlier.  As long as the "better" is different, we try again.  Step through the program and watch the approximations get closer and closer.

.. activecode:: itm

    def sqrt(n):
        approx = 0.5 * n
        better = 0.5 * (approx + n/approx)
        while better != approx:
            approx = better
            better = 0.5 * (approx + n/approx)
        return approx

    print(sqrt(100))

.. note::

	The ``while`` statement shown above uses comparison of two floating point numbers in the condition.  Since floating point numbers are themselves approximation of real numbers in mathematics, it is often better to compare for a result that is within some small threshold of the value you are looking for.

.. index:: accumulator pattern

The Accumulator Pattern Revisited
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Newton's method to calculate square roots is an example of an algorithm that repeats as long as it can improve the result. It's just a variation of our accumulator pattern. Many algorithms work this way and so require the use of indefinite iteration.

Here is another accumulator pattern program. It adds up the reciprocals of powers of two.

.. image:: Figures/sum2n.PNG


You may have studied this sequence in a math class and learned that the sum approaches but never reaches 2.0. That is true in theory. However, when we implement this summation in a program, we see something different. 

.. activecode:: itn

    def sumTo():
        """ Return the sum of reciprocals of powers of 2 """

        theSum  = 0
        aNumber = 0
        while theSum < 2.0:
            theSum = theSum + 1/2**aNumber
            aNumber = aNumber + 1

        return theSum

    print(sumTo())


.. admonition:: Modify the program ...

   If the sum never reaches 2.0, the loop would never terminate. But the loop does stop! How many repetitions did it make before it stopped?

   On line 9 (not indented), print the value of ``aNumber`` and you will see.

   But **why** did it reach 2.0? Are those math teachers wrong?



