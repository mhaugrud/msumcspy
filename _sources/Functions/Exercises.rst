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


   Use the drawsquare function we wrote in this chapter in a program to draw the image shown below. Assume each side is 20 units. (Notice where the turtle is when the program ends.)

   .. image:: Figures/five_squares.png

   .. activecode:: ex_5_1
      :nocodelens:

      import turtle

      def drawSquare(t, sz):
         """Get turtle t to draw a square with sides sz long"""

         for i in range(4):
            t.forward(sz)
            t.left(90)

      wn = turtle.Screen()
      wn.bgcolor("lightgreen")

      alex = turtle.Turtle()
      alex.color("hotpink")
      alex.pensize(3)




      wn.exitonclick()


.. question:: functions_ex_2


   Use the drawsquare function we wrote in this chapter in a program to draw the image shown below. Assume each side is 20 units. (Notice where the turtle is when the program ends.)

   .. image:: Figures/five_squaresv.png

   .. activecode:: ex_5_2
      :nocodelens:

      import turtle

      def drawSquare(t, sz):
         """Get turtle t to draw a square with sides sz long"""

         for i in range(4):
            t.forward(sz)
            t.left(90)

      wn = turtle.Screen()
      wn.bgcolor("lightgreen")

      alex = turtle.Turtle()
      alex.color("hotpink")
      alex.pensize(3)




      wn.exitonclick()


.. question:: functions_ex_3

   Write a program to draw this using the drawSquare function. Assume the innermost square is 20 units per side, and each successive square is 20 units bigger, per side, than the one inside it. (Notice where the turtle is when the program ends.)

   .. image:: Figures/nested_squares.png


   .. activecode:: ex_5_3
      :nocodelens:


.. question:: functions_ex_4


   Write a function ``drawPoly(aturtle, num_sides, side_length)`` which makes a turtle draw a regular polygon (all sides are the same length and all angles are the same size). Include a proper docstring. It can be called with any number of sides. Here are some examples:

   ``drawPoly(fred, 3, 100)``, would draw:

   .. image:: Figures/equitri.png

   ``drawPoly(tess, 8, 50)``, would draw:

   .. image:: Figures/regularpolygon.png

   .. activecode:: ex_5_4
      :nocodelens:


      import turtle

      def drawPoly(aturtle, num_sides, side_length):
          ''' '''



.. question:: functions_ex_5


   Call the ``drawPoly`` from the previous question within a loop to produce the regular polygons from a triangle to an octagon:


   .. image:: Figures/multipoly.png

   .. activecode:: ex_5_5
      :nocodelens:



      
.. question:: functions_ex_6

   Write a non-fruitful function ``drawEquitriangle(someturtle, somesize)`` which calls ``drawPoly`` from a previous question to have its turtle draw an equilateral triangle.

   .. activecode:: ex_5_6
      :nocodelens:

      import turtle

      def drawPoly(aturtle, num_sides, side_length):
          ''' '''


      drawEquitriangle(someturtle, somesize):
          ''' '''



.. question:: functions_ex_7

   Draw this pretty pattern using the drawSquare function (there are 20 squares).

   .. image:: Figures/tess08.png

   .. activecode:: ex_5_7
      :nocodelens:


.. question:: functions_ex_8

   The two spirals in this picture differ only by the turn angle.  Draw both.

   .. image:: Figures/tess_spirals.png
      :height: 240

   .. activecode:: ex_5_8
      :nocodelens:

      import turtle

      def drawSpiral(t, angle):


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

   Write a function called `fancySquare` that will draw a square with fancy corners (spites on the corners).  You should implement and use the `drawSprite` function from above.  For an even more interesting look, how about adding small triangles to the ends of the sprite legs.

   .. activecode:: ex_5_13
      :nocodelens:

      import turtle

      def drawSprite(t, numlegs, leglength):


.. question:: functions_ex_14


   Write a fruitful function ``sumTo(n)`` that returns the sum of all positive integers up to and including `n`.   So ``sumTo(10)`` is ``1+2+3...+10`` which returns the value 55.  Use the equation  (n * (n + 1)) / 2.

   .. activecode:: ex_5_14

      def sumTo(n):
          # your code here

      ====
      from unittest.gui import TestCaseGui
      import random
      class myTests(TestCaseGui):

         def testOne(self):
             self.assertAlmostEqual(sumTo(0),0.0,0,"Tested sumTo on input 0")
             n = random.randint(1,30)
             self.assertAlmostEqual(sumTo(n),n*(n+1)/2,0,"Tested input "+str(n))
             n = random.randint(1,30)
             self.assertAlmostEqual(sumTo(n),n*(n+1)/2,0,"Tested input "+str(n))
             n = random.randint(1,30)
             self.assertAlmostEqual(sumTo(n),n*(n+1)/2,0,"Tested input "+str(n))

      myTests().main()


.. question:: functions_ex_15

   Rewrite the function ``sumTo(n)`` that returns the sum of all positive integers up to and including `n`. This time use the accumulator pattern.

   .. activecode:: ex_5_15

      def sumTo(n):
          # your code here

      ====
      from unittest.gui import TestCaseGui
      import random

      class myTests(TestCaseGui):

         def testOne(self):
             self.assertAlmostEqual(sumTo(0),0.0,0,"Tested sumTo on input 0")
             n = random.randint(1,30)
             self.assertAlmostEqual(sumTo(n),n*(n+1)/2,0,"Tested input "+str(n))
             n = random.randint(1,30)
             self.assertAlmostEqual(sumTo(n),n*(n+1)/2,0,"Tested input "+str(n))
             n = random.randint(1,30)
             self.assertAlmostEqual(sumTo(n),n*(n+1)/2,0,"Tested input "+str(n))

      myTests().main()




.. question:: functions_ex_16

   Write a function `volOfCylinder(r,h)` which returns the volume of a cylinder of radius `r` and height `h`. Make sure you use the math module in your solution.

   .. activecode:: ex_5_16

      import math
      def volOfCylinder(r,h):
          # your code here

      ====
      from unittest.gui import TestCaseGui
      import random
      import math
      class myTests(TestCaseGui):

         def testOne(self):
             a = random.randint(1,30)
             b = random.randint(1,30)
             self.assertAlmostEqual(volOfCylinder(a,b),a*a*b*math.pi,5,"Tested inputs: "+str(a)+" and "+str(b))
             a = random.randint(1,30)
             b = random.randint(1,30)
             self.assertAlmostEqual(volOfCylinder(a,b),a*a*b*math.pi,5,"Tested inputs: "+str(a)+" and "+str(b))
             a = random.randint(1,30)
             b = random.randint(1,30)
             self.assertAlmostEqual(volOfCylinder(a,b),a*a*b*math.pi,5,"Tested inputs: "+str(a)+" and "+str(b))
             a = random.randint(1,30)
             b = random.randint(1,30)
             self.assertAlmostEqual(volOfCylinder(a,b),a*a*b*math.pi,5,"Tested inputs: "+str(a)+" and "+str(b))


      myTests().main()


.. question:: functions_ex_17


   Use the accumulator pattern to write a function called ``fact`` that will return the factorial of a positive integer. Factorial is the product of positive integers up to and including the argument. So ``fact(5)`` is ``1*2*3*4*5`` which return the value 120.

   .. activecode:: ex_5_17

      def fact(n):
          #your code here

      ====
      from unittest.gui import TestCaseGui
      import random
      import math
      class myTests(TestCaseGui):

         def testOne(self):
             self.assertEqual(fact(1),1,"Tested input: 1")
             a = random.randint(1,7)*2
             self.assertEqual(fact(a),math.factorial(b),"Tested input: "+str(a))
             b = random.randint(1,7)*2+1
             self.assertEqual(fact(b),math.factorial(b),"Tested input: "+str(b))
             c = a
             while c == a or c == b:
                 c = random.randint(1,15)
             self.assertEqual(fact(c),math.factorial(c),"Tested input: "+str(c))


      myTests().main()


.. question:: selection_ex_18

   Write a function ``findHypot``.  The function will be given the length of two sides of a right-angled triangle and it should return
   the length of the hypotenuse.  (Hint:  ``x ** 0.5`` will return the square root, or use ``sqrt`` from the math module)

   .. activecode:: ex_5_18

      def findHypot(a,b):
          # your code here

      ====
      from unittest.gui import TestCaseGui
      import random
      import math

      class myTests(TestCaseGui):
          def testOne(self):
              a = random.randint(1,30)
              b = random.randint(1,30)
              self.assertAlmostEqual(findHypot(a,b),math.hypot(a,b),5,"Tested inputs "+str(a)+" and "+str(b))
              a = random.randint(1,30)
              b = random.randint(1,30)
              self.assertAlmostEqual(findHypot(a,b),math.hypot(a,b),5,"Tested inputs "+str(a)+" and "+str(b))
              a = random.randint(1,30)
              b = random.randint(1,30)
              self.assertAlmostEqual(findHypot(a,b),math.hypot(a,b),5,"Tested inputs "+str(a)+" and "+str(b))
              a = random.randint(1,30)
              b = random.randint(1,30)
              self.assertAlmostEqual(findHypot(a,b),math.hypot(a,b),5,"Tested inputs "+str(a)+" and "+str(b))

      myTests().main()


