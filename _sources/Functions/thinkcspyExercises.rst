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


   Use the drawsquare function we wrote in this chapter in a program to draw the image shown below. Assume each side is 20 units. (Hint: notice that the turtle has already moved away from the ending point of the last square when the program ends.)

   .. image:: Figures/five_squares.png

   .. activecode:: ex_5_1
      :nocodelens:

      import turtle

      def drawSquare(t, sz):
         """Get turtle t to draw a square of sz side"""

         for i in range(4):
            t.forward(sz)
            t.left(90)

      wn = turtle.Screen()
      wn.bgcolor("lightgreen")

      alex = turtle.Turtle()
      alex.color("hotpink")






      wn.exitonclick()



.. question:: functions_ex_2

   Write a program to draw this using the drawSquare function. Assume the innermost square is 20 units per side, and each successive square is 20 units bigger, per side, than the one inside it.

   .. image:: Figures/nested_squares.png


   .. activecode:: ex_5_2
      :nocodelens:


.. question:: functions_ex_3


   Write a non-fruitful function ``drawPoly(someturtle, somesides, somesize)`` which makes a turtle draw a regular polygon. When called with ``drawPoly(tess, 8, 50)``, it will draw a shape like this:

   .. image:: Figures/regularpolygon.png

   .. activecode:: ex_5_3
      :nocodelens:


      import turtle

      def drawPoly(t, num_sides, side_length):


.. question:: functions_ex_4

   Write a non-fruitful function ``drawEquitriangle(someturtle, somesize)`` which calls ``drawPoly`` from the previous question to have its turtle draw a equilateral triangle.

   .. activecode:: ex_5_4
      :nocodelens:


.. question:: functions_ex_5

   Draw this pretty pattern using the drawSquare function (there are 20 squares).

   .. image:: Figures/tess08.png

   .. activecode:: ex_5_5
      :nocodelens:


.. question:: functions_ex_6

   The two spirals in this picture differ only by the turn angle.  Draw both.

   .. image:: Figures/tess_spirals.png
      :height: 240

   .. activecode:: ex_5_6
      :nocodelens:

      import turtle

      def drawSpiral(t, angle):



.. question:: functions_ex_7


   Write a fruitful function ``sumTo(n)`` that returns the sum of all integer numbers up to and including `n`.   So ``sumTo(10)`` would be ``1+2+3...+10`` which would return the value 55.  Use the equation  (n * (n + 1)) / 2.

   .. activecode:: ex_5_7

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



.. question:: functions_ex_8

   Write a function `areaOfCircle(r)` which returns the area of a circle of radius `r`. Make sure you use the math module in your solution.

   .. activecode:: ex_5_8

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


   Write a non-fruitful function to draw a five pointed star, where the length of each side is 100 units.

   .. image:: Figures/star.png

   .. activecode:: ex_5_9
      :nocodelens:

      import turtle

      def drawFivePointStar(t):


.. question:: functions_ex_10

   Extend your program above.  Draw five stars, but between each, pick up the pen, move forward by 350 units, turn right by 144, put the pen down, and draw the next star. You'll get something like this (note that you will need to move to the left before drawing your first star in order to fit everything in the window):

   .. image:: Figures/five_stars.png

   What would it look like if you didn't pick up the pen?

   .. activecode:: ex_5_10
      :nocodelens:


.. question:: functions_ex_11


   Extend the star function to draw an n pointed star.  (Hint: n must be an odd number greater or equal to 3).

   .. activecode:: ex_5_11
      :nocodelens:

      import turtle

      def drawStar(t, n):


.. question:: functions_ex_12

   Write a function called drawSprite that will draw a sprite.  The function will need parameters for the turtle, the number of legs, and the length of the legs.  Invoke the function to create a sprite with 15 legs of length 120.

   .. activecode:: ex_5_12
      :nocodelens:


.. question:: functions_ex_13

   Rewrite the function ``sumTo(n)`` that returns the sum of all integer numbers up to and including `n`. This time use the accumulator pattern.

   .. activecode:: ex_5_13

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



.. question:: functions_ex_14

   Write a function called ``mySqrt`` that will approximate the square root of a number, call it n, by using Newton's algorithm.
   Newton's approach is an iterative guessing algorithm where the initial guess is n/2 and each subsequent guess is computed using the formula:  newguess = (1/2) * (oldguess + (n/oldguess)).

    .. activecode:: ex_5_14

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


   Write a function called ``myPi`` that will return an approximation of PI (3.14159...).  Use the `Leibniz <http://en.wikipedia.org/wiki/Leibniz_formula_for_%CF%80>`_ approximation.

   .. activecode:: ex_5_15

      def myPi(iters):
          # Calculate an approximation of PI using the Leibniz
          # approximation with iters number of iterations

          # your code here



.. question:: functions_ex_16

   Write a function called `myPi` that will return an approximation of PI (3.14159...).  Use the `Madhava <http://en.wikipedia.org/wiki/Madhava_of_Sangamagrama>`_ approximation.

   .. activecode:: ex_5_16

      def myPi(iters):
          # Calculate an approximation of PI using the Madhava
          # approximation with iters number of iterations

          #your code here

.. question:: functions_ex_17

   Write a function called `fancySquare` that will draw a square with fancy corners (spites on the corners).  You should implement and use the `drawSprite` function from above.  For an even more interesting look, how about adding small triangles to the ends of the sprite legs.

   .. activecode:: ex_5_17
      :nocodelens:

      import turtle

      def drawSprite(t, numlegs, leglength):

