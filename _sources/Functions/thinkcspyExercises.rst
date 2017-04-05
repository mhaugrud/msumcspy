..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".


Exercises
---------

.. question:: functions_ex_1

   :number: 1

   .. tabbed:: q1

        .. tab:: Question

            Use the drawsquare function we wrote in this chapter in a program to draw
            the image shown below.
            Assume each side is 20 units.
            (Hint: notice that the turtle has already moved away from the ending point of the last
            square when the program ends.)

            .. image:: Figures/five_squares.png

            .. actex:: ex_5_1

                import turtle

                def drawSquare(t, sz):
                    """Get turtle t to draw a square of sz side"""

                    for i in range(4):
                        t.forward(sz)
                        t.left(90)

                wn = turtle.Screen()
                wn.bgcolor("lightgreen")

                alex = turtle.Turtle()
                alex.color("pink")

                drawSquare(alex,20)

                wn.exitonclick()


        .. tab:: Answer

            .. activecode:: q1_answer

                import turtle

                def drawSquare(t, sz):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: a2ac86a8d0524fc6830aefb785199048

.. question:: functions_ex_2

   Write a program to draw this. Assume the innermost square is 20 units per side,
   and each successive square is 20 units bigger, per side, than the one inside it.

    .. image:: Figures/nested_squares.png


    .. actex:: ex_5_2


.. question:: functions_ex_3

   .. tabbed:: q3

        .. tab:: Question

            Write a non-fruitful function ``drawPoly(someturtle, somesides, somesize)`` which makes a turtle
            draw a regular polygon.
            When called with ``drawPoly(tess, 8, 50)``, it will draw a shape like this:

            .. image:: Figures/regularpolygon.png

            .. actex:: ex_5_3


        .. tab:: Answer

            .. activecode:: q3_answer

                import turtle

                def drawPoly(t, num_sides, side_length):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: ba2f11265c524c7581bf7cf25d23bf3a

.. question:: functions_ex_4

   Draw this pretty pattern.

   .. image:: Figures/tess08.png

   .. actex:: ex_5_4

.. question:: functions_ex_5

   .. tabbed:: q5

        .. tab:: Question

            The two spirals in this picture differ only by the turn angle.  Draw both.

            .. image:: Figures/tess_spirals.png
               :height: 240

            .. actex:: ex_5_5

        .. tab:: Answer

            .. activecode:: q5_answer

                import turtle

                def drawSpiral(t, angle):


        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: c587119991344db988f8fb37c8c9a31e

.. question:: functions_ex_6

   Write a non-fruitful function ``drawEquitriangle(someturtle, somesize)`` which calls ``drawPoly`` from the
   previous question to have its turtle draw a equilateral triangle.

   .. actex:: ex_5_6


.. question:: functions_ex_7

   .. tabbed:: q7

        .. tab:: Question

            Write a fruitful function ``sumTo(n)`` that returns the sum of all integer numbers up to and
            including `n`.   So ``sumTo(10)`` would be ``1+2+3...+10`` which would return the value 55.  Use the
            equation  (n * (n + 1)) / 2.

            .. actex:: ex_5_7

                def sumTo(n):
                    # your code here

                ====
                from unittest.gui import TestCaseGui

                class myTests(TestCaseGui):

                    def testOne(self):
                        self.assertAlmostEqual(sumTo(15),120.0,0,"Tested sumTo on input 15")
                        self.assertAlmostEqual(sumTo(0),0.0,0,"Tested sumTo on input 0")
                        self.assertAlmostEqual(sumTo(25),325.0,0,"Tested sumTo on input 25")
                        self.assertAlmostEqual(sumTo(7),28.0,0,"Tested sumTo on input 7")

                myTests().main()


        .. tab:: Answer

            .. activecode:: q7_answer

                from test import testEqual

                def sumTo(n):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: d6ba37a51d09845f39c96d4d4ef1d6f45

.. question:: functions_ex_8

   Write a function `areaOfCircle(r)` which returns the area of a circle of radius `r`.  Make sure you use the math module in your solution.

    .. actex:: ex_5_8

        def areaOfCircle(r):
            # your code here

        ====
        from unittest.gui import TestCaseGui

        class myTests(TestCaseGui):

            def testOne(self):
                self.assertAlmostEqual(areaOfCircle(5.0),78.53981633974483,5,"Tested input: areaOfCircle(5.0)")
                self.assertEqual(areaOfCircle(5.0),78.53981633974483,"Tested input: areaOfCirlce(5.0)")
                self.assertEqual(areaOfCircle(0),0.0,"Tested input: areaOfCirlce(0)")
                self.assertAlmostEqual(areaOfCircle(31415.926535897932),3100627668.0299816,5,"Tested input: areaOfCirlce(31415.926535897932)")


        myTests().main()


.. question:: functions_ex_9

   .. tabbed:: q9

        .. tab:: Question

            Write a non-fruitful function to draw a five pointed star, where the length of each side is 100 units.

            .. image:: Figures/star.png

            .. actex:: ex_5_9

        .. tab:: Answer

            .. activecode:: q9_answer

                import turtle

                def drawFivePointStar(t):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: e757873187bb4581bffecdad449b5f61

.. question:: functions_ex_10

   Extend your program above.  Draw five stars, but between each, pick up the pen,
   move forward by 350 units, turn right by 144, put the pen down, and draw the next star.
   You'll get something like this (note that you will need to move to the left before drawing your first star in order to fit everything in the window):

   .. image:: Figures/five_stars.png

   What would it look like if you didn't pick up the pen?

   .. actex:: ex_5_10


.. question:: functions_ex_11

   .. tabbed:: q11

        .. tab:: Question

            Extend the star function to draw an n pointed star.  (Hint: n must be an odd number greater or
            equal to 3).

            .. actex:: ex_5_11


        .. tab:: Answer

            .. activecode:: q11_answer

                import turtle

                def drawStar(t, n):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: f2f8ff1b301e4d99bd4ac52e68c8c1ed

.. question:: functions_ex_12

   Write a function called drawSprite that will draw a sprite.  The function will need parameters for
   the turtle, the number of legs, and the length of the legs.  Invoke the function to create a sprite
   with 15 legs of length 120.

   .. actex:: ex_5_12


.. question:: functions_ex_13

   .. tabbed:: q13

        .. tab:: Question

            Rewrite the function ``sumTo(n)`` that returns the sum of all integer numbers up to and
            including `n`.   This time use the accumulator pattern.

            .. actex:: ex_5_13

                def sumTo(n):
                    # your code here

                ====
                from unittest.gui import TestCaseGui

                class myTests(TestCaseGui):

                    def testOne(self):
                        self.assertEqual(sumTo(15),120,"Tested sumTo on input 15")
                        self.assertEqual(sumTo(0),0,"Tested sumTo on input 0")
                        self.assertEqual(sumTo(25),325,"Tested sumTo on input 25")
                        self.assertEqual(sumTo(7),28,"Tested sumTo on input 7")

                myTests().main()


        .. tab:: Answer

            .. activecode:: q13_answer

                def sumTo(n):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: eda665389fda49a584b128cc30515595

.. question:: functions_ex_14

   Write a function called ``mySqrt`` that will approximate the square root of a number, call it n, by using
   Newton's algorithm.
   Newton's approach is an iterative guessing algorithm where the initial guess is n/2 and each subsequent guess
   is computed using   the formula:  newguess = (1/2) * (oldguess + (n/oldguess)).

    .. actex:: ex_5_14

        def mySqrt(n):
            # your code here

        ====
        from unittest.gui import TestCaseGui

        class myTests(TestCaseGui):

            def testOne(self):
                self.assertAlmostEqual(mySqrt(4.0),2.0,0,"Tested mySqrt on input 4.0")
                self.assertAlmostEqual(mySqrt(9.0),3.0,4,"Tested accuracy of mySqrt on input 3.0")
                self.assertAlmostEqual(mySqrt(36.0),6.0,5,"Tested accuracy of mySqrt on input 6.0")
                self.assertAlmostEqual(mySqrt(100.0),10.0,4,"Tested accuracy of mySqrt on input 10.0. Try iterating more times.")

        myTests().main()


.. question:: functions_ex_15

   .. tabbed:: q15

        .. tab:: Question

            Write a function called ``myPi`` that will return an approximation of PI (3.14159...).  Use the `Leibniz <http://en.wikipedia.org/wiki/Leibniz_formula_for_%CF%80>`_ approximation.

            .. actex:: ex_5_15

                def myPi(iters):
                    # Calculate an approximation of PI using the Leibniz
                    # approximation with iters number of iterations

                    # your code here


        .. tab:: Answer

            .. activecode:: q15_answer

                def myPi(iters):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: b699e4b7bad44db6bd788c795c124b23

.. question:: functions_ex_16

   Write a function called `myPi` that will return an approximation of PI (3.14159...).  Use the `Madhava <http://en.wikipedia.org/wiki/Madhava_of_Sangamagrama>`_ approximation.

    .. actex:: ex_5_16

        def myPi(iters):
            # Calculate an approximation of PI using the Madhava
            # approximation with iters number of iterations

            #your code here

.. question:: functions_ex_17

   .. tabbed:: q17

        .. tab:: Question

            Write a function called `fancySquare` that will draw a square with fancy corners (spites on the corners).  You should
            implement and use the `drawSprite` function from above.  For an even more interesting look, how about adding small
            triangles to the ends of the sprite legs.

            .. actex:: ex_5_17

        .. tab:: Answer

            .. activecode:: q17_answer

                import turtle

                def drawSprite(t, numlegs, leglength):

        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: db5d8808bf5749579718bdd2088b539f
