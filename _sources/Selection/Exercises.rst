..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: s-
   :start: 1

Exercises
---------

.. question:: selection_ex_1
   :number: 1


   What do these expressions evaluate to (``True`` or ``False``)? ::
      
         1.  3 == 3
         2.  3 != 3
         3.  3 >= 4
         4.  not (3 > 4)

   .. activecode:: ex_6_1


.. question:: selection_ex_2


   For each of the given conditions, type its **logical opposite**. Do not use the 
   ``not`` operator. ::
      
         1.  a > 7
         2.  a >= 7
         3.  a == 7  or  b == 3
         4.  a > 7  and  b != 3

   .. activecode:: ex_6_2



.. question:: selection_ex_3


            Write a function which is given an exam mark, and it returns a string --- the grade 
            for that mark --- according to this scheme:

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

            The square and round brackets denote closed and open intervals. A closed interval includes 
            the number; an open interval excludes it.  So 79.99999 gets grade C, but 80 gets grade B.


            .. activecode:: ex_6_3

                def getGrade(mark):
                    #your code here


                ====

                from unittest.gui import TestCaseGui
                import random
                class myTests(TestCaseGui):

                    def testOne(self):
                        self.assertEqual(getGrade(90),'A','Tested boundary of 90')
                        self.assertEqual(getGrade(80),'B','Tested boundary of 80')
                        self.assertEqual(getGrade(70),'C','Tested boundary of 70')
                        self.assertEqual(getGrade(60),'D','Tested boundary of 60')
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

   
   Write two boolean functions:

   - ``isPositive`` returns ``True`` if the argument is a positive number, otherwise, ``False``.
   - ``isNegative`` returns ``True`` if the argument is a negative number, otherwise, ``False``.

   .. activecode:: ex_6_4

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
              r = random.random()*100+1e-10
              self.assertEqual(isNegative(-r),True,"Tested isNegative with input of "+str(-r))
              self.assertEqual(isNegative(0),False,"Tested isNegative with input of 0")
              self.assertEqual(isNegative(r),False,"Tested isNegative with input of "+str(r))


      myTests().main()

.. question:: selection_ex_5

           Write a function called ``is_even(n)`` that takes an integer as an argument
           and returns ``True`` if the argument is an **even number** and ``False`` if
           it is **odd**.

           .. activecode:: ex_6_5

               def is_even(n):
                   # your code here

               ====

               from unittest.gui import TestCaseGui
               import random
               class myTests(TestCaseGui):
                    def testOne(self):
                        r = random.randrange(0,101,2)
                        self.assertEqual(is_even(r),True,"Tested on input of "+str(r))
                        r = random.randrange(1,101,2)
                        self.assertEqual(is_even(r),False,"Tested on input of "+str(r))
                        self.assertEqual(is_even(1),False,"Tested on input of 1")
                        self.assertEqual(is_even(0),True,"Tested on input of 0")

               myTests().main()


.. question:: selection_ex_6

   Now write the function ``is_odd(n)`` that returns ``True`` when ``n`` is odd
   and ``False`` otherwise.

   .. activecode:: ex_6_6

       def is_odd(n):
           # your code here


       ====
       from unittest.gui import TestCaseGui
       import random
       class myTests(TestCaseGui):
            def testOne(self):
                r = random.randrange(1,101,2)
                self.assertEqual(is_odd(r),True,"Tested on input of "+str(r))
                r = random.randrange(0,101,2)
                self.assertEqual(is_odd(r),False,"Tested on input of "+str(r))
                self.assertEqual(is_odd(1),True,"Tested on input of 1")
                self.assertEqual(is_odd(0),False,"Tested on input of 0")

       myTests().main()

.. question:: selection_ex_7


           Modify ``is_odd`` so that it uses a call to ``is_even`` to determine if its
           argument is an odd integer.

           .. activecode:: ex_6_7

               def is_even(n):
                   # type your code from exercise 5 here

               def is_odd(n):
                   # your code here

               ====
               from unittest.gui import TestCaseGui
               import random
               class myTests(TestCaseGui):
                    def testOne(self):
                        r = random.randrange(1,101,2)
                        self.assertEqual(is_odd(r),True,"Tested on input of "+str(r))
                        r = random.randrange(0,101,2)
                        self.assertEqual(is_odd(r),False,"Tested on input of "+str(r))
                        self.assertEqual(is_odd(1),True,"Tested on input of 1")
                        self.assertEqual(is_odd(0),False,"Tested on input of 0")

               myTests().main()




.. question:: selection_ex_8

   Write a function that takes a year as a parameter and returns ``True`` if the year is a leap year, 
   ``False`` otherwise. A year is a *leap year* if it is evenly divisible by 400. If it is evenly 
   divisible by 100 (and not 400), it is not a leap year. Finally, if it is evenly divisible by 4, 
   it is a leap year.

   .. activecode:: ex_6_8

      def isLeap(year):
          # your code here

      ====
      from unittest.gui import TestCaseGui
      import random

      class myTests(TestCaseGui):
          def testOne(self):
              self.assertEqual(isLeap(1800),False,"Tested isLeap on an input of 1800")
              self.assertEqual(isLeap(1900),False,"Tested isLeap on an input of 1900")
              self.assertEqual(isLeap(2000),True,"Tested isLeap on an input of 2000")
              y = 2000
              while y == 2000:
                  y = random.randint(490,510) * 4
              self.assertEqual(isLeap(y),True,"Tested isLeap on an input of "+str(y))
              y = random.randint(490,510) * 4 + 1
              self.assertEqual(isLeap(y),False,"Tested isLeap on an input of "+str(y))
              y = random.randint(490,510) * 4 + 2
              self.assertEqual(isLeap(y),False,"Tested isLeap on an input of "+str(y))
              y = random.randint(490,510) * 4 + 3
              self.assertEqual(isLeap(y),False,"Tested isLeap on an input of "+str(y))
              self.assertEqual(isLeap(2100),False,"Tested isLeap on an input of 2100")


      myTests().main()


.. question:: selection_ex_9

   "Thirty days has September, April, June, and November. All the rest have thirty-one except February, 
   it's different, son." Write the function ``daysInMonth``. It has two parameters: the month (1 to 12) 
   and the year. It returns how many days are in the specified month. Since the number days in February 
   depends on whether or not it is a leap year, ``daysInMonth`` must call the ``isLeap`` function.

   .. activecode:: ex_6_9

      def isLeap(y):
          # type your code from exercise 8 here


      def daysInMonth(month, year):
          # your code goes here


      ====
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):
          def testOne(self):
              self.assertEqual(daysInMonth(1,2001),31,"January")
              self.assertEqual(daysInMonth(3,2002),31,"March")
              self.assertEqual(daysInMonth(4,2003),30,"April")
              self.assertEqual(daysInMonth(5,2004),31,"May")
              self.assertEqual(daysInMonth(6,2005),30,"June")
              self.assertEqual(daysInMonth(7,2006),31,"July")
              self.assertEqual(daysInMonth(8,2007),31,"August")
              self.assertEqual(daysInMonth(9,2008),30,"September")
              self.assertEqual(daysInMonth(10,2009),31,"October")
              self.assertEqual(daysInMonth(11,2010),30,"November")
              self.assertEqual(daysInMonth(12,2011),31,"December")
              self.assertEqual(daysInMonth(2,2000),29,"February - leap year")
              self.assertEqual(daysInMonth(2,2012),29,"February - leap year")
              self.assertEqual(daysInMonth(2,2013),28,"February - not leap year")
              self.assertEqual(daysInMonth(2,2100),28,"February - not leap year")

      myTests().main()


.. question:: selection_ex_10

   Write a function ``is_rightangled`` which, given the length of three sides of a triangle,
   will determine whether the triangle is right-angled.  Assume that the third argument to the
   function is always the longest side.  It will return ``True`` if the triangle
   is right-angled, or ``False`` otherwise.

   Hint: floating point arithmetic is not always exactly accurate, so it is not safe to 
   test floating point numbers for equality. If a good programmer wants to know whether
   ``x`` is equal or close enough to ``y``, s/he would probably code it as

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

            .. activecode:: ex_6_12


.. question:: selection_ex_13


            Implement the ``addup`` function. It returns the sum of all positive integers that are not 
            evenly divisible by 2 or 3, up to and including its parameter ``n``.

            .. activecode:: ex_6_13

                def addup(n):
                    # your code here


                ====
                from unittest.gui import TestCaseGui
                import random
                def myad(n):
                    tot = 0
                    for x in range(1,n+1):
                        if x%2 != 0 and x%3 != 0:
                            tot += x
                    return tot

                class myTests(TestCaseGui):
                    def testOne(self):
                        self.assertEqual(addup(4),1,"Tested 4")
                        a = random.randint(5,99)
                        self.assertEqual(addup(a),myad(a),"Tested "+str(a))
                        b = a
                        while b == a:
                            b = random.randint(5,99)
                        self.assertEqual(addup(b),myad(b),"Tested "+str(b))
                        c = a
                        while c == a or c == b:
                            c = random.randint(5,99)
                        self.assertEqual(addup(c),myad(c),"Tested "+str(c))

                myTests().main()


