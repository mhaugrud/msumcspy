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

.. question:: selection_ex_1
   :number: 1


            What do these expressions evaluate to?

            #.  ``3 == 3``
            #.  ``3 != 3``
            #.  ``3 >= 4``
            #.  ``not (3 < 4)``

            .. activecode:: ex_6_1




.. question:: selection_ex_2

   Give the **logical opposites** of these conditions.  You are not allowed to use the ``not`` operator.

   #.  ``a > b``
   #.  ``a >= b``
   #.  ``a >= 18  and  day == 3``
   #.  ``a >= 18  or  day != 3``

   .. activecode:: ex_6_2

.. question:: selection_ex_3


            Write a function which is given an exam mark, and it returns a string --- the grade for that mark --- according to this
            scheme:

            .. table::

               =======   =====
               Mark      Grade
               =======   =====
               >= 90     A
               [80-90)   B
               [70-80)   C
               [60-70)   D
               < 60      F
               =======   =====

            The square and round brackets denote closed and open intervals.
            A closed interval includes the number, and open interval excludes it.   So 79.99999 gets grade C , but 80 gets grade B.

            Test your function by printing the mark and the grade for a number of different marks.

            .. activecode:: ex_6_3

                def getGrade(grade):
                    #your code here


                ====

                from unittest.gui import TestCaseGui
                import random
                class myTests(TestCaseGui):

                    def testOne(self):
                        self.assertEqual(getGrade(90),'A','Tested getGrade on input of 90')
                        self.assertEqual(getGrade(80),'B','Tested getGrade on input of 80')
                        self.assertEqual(getGrade(70),'C','Tested getGrade on input of 70')
                        self.assertEqual(getGrade(60),'D','Tested getGrade on input of 60')
                        r = random.random()*10
                        self.assertEqual(getGrade(90+r),'A','Tested getGrade on input of '+str(90+r))
                        r = random.random()*10
                        self.assertEqual(getGrade(80+r),'B','Tested getGrade on input of '+str(80+r))
                        r = random.random()*10
                        self.assertEqual(getGrade(70+r),'C','Tested getGrade on input of '+str(70+r))
                        r = random.random()*10
                        self.assertEqual(getGrade(60+r),'D','Tested getGrade on input of '+str(60+r))
                        r = random.random()*60
                        self.assertEqual(getGrade(r),'F','Tested getGrade on input of '+str(r))


                myTests().main()


.. question:: selection_ex_4

   Modify the turtle bar chart program from the previous chapter so that the bar for any value
   of 200 or more is filled with red, values between [100 and 200) are filled yellow,
   and bars representing values less than 100 are filled green.

   .. activecode:: ex_6_4
      :nocodelens:

.. question:: selection_ex_5

   .. tabbed:: q5

        .. tab:: Question

            In the turtle bar chart program, what do you expect to happen if one or more
            of the data values in the list is negative?   Go back and try it out.  Change the
            program so that when it prints the text value for the negative bars, it puts
            the text above the base of the bar (on the 0 axis).

            .. actex:: ex_6_5
               :nocodelens:

        .. tab:: Answer

            .. activecode:: answer_ex_6_5
                    :nocodelens:

                    import turtle

                    def drawBar(t, height):
                        """ Get turtle t to draw one bar, of height. """
                        t.begin_fill()               # start filling this shape
                        if height < 0:
                            t.write(str(height))
                        t.left(90)
                        t.forward(height)
                        if height >= 0:
                            t.write(str(height))
                        t.right(90)
                        t.forward(40)
                        t.right(90)
                        t.forward(height)
                        t.left(90)
                        t.end_fill()                 # stop filling this shape



                    xs = [48, -50, 200, 240, 160, 260, 220]  # here is the data
                    maxheight = max(xs)
                    minheight = min(xs)
                    numbars = len(xs)
                    border = 10

                    tess = turtle.Turtle()           # create tess and set some attributes
                    tess.color("blue")
                    tess.fillcolor("red")
                    tess.pensize(3)

                    wn = turtle.Screen()             # Set up the window and its attributes
                    wn.bgcolor("lightgreen")
                    if minheight > 0:
                        lly = 0
                    else:
                        lly = minheight - border

                    wn.setworldcoordinates(0-border, lly, 40*numbars+border, maxheight+border)


                    for a in xs:
                        drawBar(tess, a)

                    wn.exitonclick()



        .. tab:: Discussion

            .. disqus::
                :shortname: interactivepython
                :identifier: disqus_0118bd02de23462bafdb51beb4c85e44

.. question:: selection_ex_6

   Write two boolean functions:

   - ``isPositive`` returns ``True`` if the argument is a positive number, otherwise, ``False``.
   - ``isNegative`` returns ``True`` if the argument is a negative number, otherwise, ``False``.

   .. activecode:: ex_6_6

      def isPositive(n):
          # your code here


      def isNegative(n):
          # your code here

      ====

      from unittest.gui import TestCaseGui
      import random
      class myTests(TestCaseGui):
          def testOne(self):
              r = random.random()*100+1e-10
              self.assertEqual(isPositive(r),True,"Tested isPositive with input of "+str(r))
              self.assertEqual(isPositive(0),False,"Tested isPositive with input of 0")
              self.assertEqual(isPositive(-r),False,"Tested isPositive with input of "+str(-r))
              r = random.random()*100*1e-10
              self.assertEqual(isNegative(r),True,"Tested isNegative with input of "+str(-r))
              self.assertEqual(isNegative(0),False,"Tested isNegative with input of 0")
              self.assertEqual(isNegative(r),False,"Tested isNegative with input of "+str(r))


      myTests().main()

.. question:: selection_ex_7

           Write a function called ``is_even(n)`` that takes an integer as an argument
           and returns ``True`` if the argument is an **even number** and ``False`` if
           it is **odd**.

           .. activecode:: ex_6_7

               def is_even(n):
                   # your code here

               ====

               from unittest.gui import TestCaseGui
               import random
               class myTests(TestCaseGui):
                    def testOne(self):
                        r = random.randrange(0,101,2)
                        self.assertEqual(is_even(r),True,"Tested is_even on input of "+str(r))
                        r = random.randrange(1,101,2)
                        self.assertEqual(is_even(r),False,"Tested is_even on input of "+str(r))
                        self.assertEqual(is_even(1),False,"Tested is_even on input of 1")
                        self.assertEqual(is_even(0),True,"Tested is_even on input of 0")

               myTests().main()


.. question:: selection_ex_8

   Now write the function ``is_odd(n)`` that returns ``True`` when ``n`` is odd
   and ``False`` otherwise.

   .. activecode:: ex_6_8

       def is_odd(n):
           # your code here


       ====
       from unittest.gui import TestCaseGui
       import random
       class myTests(TestCaseGui):
            def testOne(self):
                r = random.randrange(1,101,2)
                self.assertEqual(is_odd(r),True,"Tested is_even on input of "+str(r))
                r = random.randrange(0,101,2)
                self.assertEqual(is_odd(r),False,"Tested is_even on input of "+str(r))
                self.assertEqual(is_odd(1),True,"Tested is_odd on input of 1")
                self.assertEqual(is_odd(0),False,"Tested is_odd on input of 0")

       myTests().main()

.. question:: selection_ex_9


           Modify ``is_odd`` so that it uses a call to ``is_even`` to determine if its
           argument is an odd integer.

           .. activecode:: ex_6_9

               def is_odd(n):
                   # your code here

               ====
               from unittest.gui import TestCaseGui
               import random
               class myTests(TestCaseGui):
                    def testOne(self):
                        r = random.randrange(1,101,2)
                        self.assertEqual(is_odd(r),True,"Tested is_even on input of "+str(r))
                        r = random.randrange(0,101,2)
                        self.assertEqual(is_odd(r),False,"Tested is_even on input of "+str(r))
                        self.assertEqual(is_odd(1),True,"Tested is_odd on input of 1")
                        self.assertEqual(is_odd(0),False,"Tested is_odd on input of 0")

               myTests().main()




.. question:: selection_ex_10

   Write a function ``is_rightangled`` which, given the length of three sides of a triangle,
   will determine whether the triangle is right-angled.  Assume that the third argument to the
   function is always the longest side.  It will return ``True`` if the triangle
   is right-angled, or ``False`` otherwise.

   Hint: floating point arithmetic is not always exactly accurate,
   so it is not safe to test floating point numbers for equality.
   If a good programmer wants to know whether
   ``x`` is equal or close enough to ``y``, they would probably code it up as

   .. sourcecode:: python

      if  abs(x - y) < 0.001:      # if x is approximately equal to y
          ...


   .. activecode:: ex_6_10

      def is_rightangled(a, b, c):
          # your code here

      ====
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):
          def testOne(self):
              self.assertEqual(is_rightangled(1.5,2.0,2.5),True,"Tested is_rightangled on inputs of 1.5, 2.0 and 2.5")
              self.assertEqual(is_rightangled(4.0,8.0,16.0),False,"Tested is_rightangled on inputs of 4.0, 8.0 and 16.0")
              self.assertEqual(is_rightangled(4.1,8.2,9.1678787077),True,"Tested is_rightangled on inputs of 4.1, 8.2 and 9.1678787077")
              self.assertEqual(is_rightangled(4.1,8.2,9.16787),True,"Tested is_rightangled on inputs of 4.1, 8.2, and 9.16787")
              self.assertEqual(is_rightangled(4.1,8.2,9.168),False,"Tested is_rightangled on inputs of 4.1, 8.2 and 9.168")
              self.assertEqual(is_rightangled(0.5,0.4,0.64031),True,"Tested is_rightangled on inputs of 0.5, 0.4 and 0.64031")

      myTests().main()

.. question:: selection_ex_11


            Extend the above program so that the sides can be given to the function in any order.

            .. activecode:: ex_6_11

                def is_rightangled(a, b, c):
                    # your code here


                ====
                from unittest.gui import TestCaseGui

                class myTests(TestCaseGui):
                    def testOne(self):
                        self.assertEqual(is_rightangled(1.5,2.5,2.0),True,"Tested is_rightangled on inputs of 1.5, 2.5 and 2.0")
                        self.assertEqual(is_rightangled(16.0,4.0,8.0),False,"Tested is_rightangled on inputs of 16.0, 4.0 and 8.0")
                        self.assertEqual(is_rightangled(4.1,8.2,9.1678787077),True,"Tested is_rightangled on inputs of 4.1, 8.2 and 9.1678787077")
                        self.assertEqual(is_rightangled(4.1,9.16787,8.2),True,"Tested is_rightangled on inputs of 4.1, 9.16787 and 8.2")
                        self.assertEqual(is_rightangled(4.1,8.2,9.168),False,"Tested is_rightangled on inputs of 4.1, 8.2 and 9.168")
                        self.assertEqual(is_rightangled(0.5,0.64031,0.4),True,"Tested is_rightangled on inputs of 0.5, 0.64031 and 0.4")

                myTests().main()


.. question:: selection_ex_12

   A year is a **leap year** if it is divisible by 4 unless it is a century that is not divisible by 400.
   Write a function that takes a year as a parameter and returns ``True`` if the year is a leap year, ``False`` otherwise.

   .. activecode:: ex_6_12

      def isLeap(year):
          # your code here

      ====
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):
          def testOne(self):
              self.assertEqual(isLeap(1944),True,"Tested isLeap on an input of 1944")
              self.assertEqual(isLeap(2011),False,"Tested isLeap on an input of 2011")
              self.assertEqual(isLeap(1986),False,"Tested isLeap on an input of 1986")
              self.assertEqual(isLeap(1800),False,"Tested isLeap on an input of 1800")
              self.assertEqual(isLeap(1900),False,"Tested isLeap on an input of 1900")
              self.assertEqual(isLeap(2000),True,"Tested isLeap on an input of 2000")
              self.assertEqual(isLeap(2056),True,"Tested isLeap on an input of 2056")

      myTests().main()

.. question:: selection_ex_13#.


            Implement the calculator for the date of Easter.

            The following algorithm computes the date for Easter Sunday for any year between 1900 to 2099.

            Ask the user to enter a year.
            Compute the following:



                1. a = year % 19
                #. b = year % 4
                #. c = year % 7
                #. d = (19 * a + 24) % 30
                #. e = (2 * b + 4 * c + 6 * d + 5) % 7
                #. dateofeaster = 22 + d + e


            Special note: The algorithm can give a date in April.  Also, if the year is one of four special
            years (1954, 1981, 2049, or 2076) then subtract 7 from the date.

            Your program should print an error message if the user provides a date that is out of range.

            .. activecode:: ex_6_13


