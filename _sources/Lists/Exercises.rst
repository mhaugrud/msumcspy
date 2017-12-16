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

.. question:: lists_ex_1
   :number: 1

   .. tabbed:: q1

        .. tab:: Question

           Draw a reference diagram for ``a`` and ``b`` before and after the third line of
           the following python code is executed:

           .. sourcecode:: python

               a = [1, 2, 3]
               b = a[:]
               b[0] = 5

        .. tab:: Answer

            Your diagram should show two variables referring to two different lists.  ``a`` refers to the original list with 1,2, and 3.
            ``b`` refers to a list with 5,2, and 3 since the zero-eth element was replaced with 5.



.. question:: lists_ex_2

   Create a list called ``myList`` with the following six items: 76, 92.3, "hello", True, 4, 76.  Do it with both append and with concatenation, one item at a time.

   .. activecode:: ex_9_2


.. question:: lists_ex_3

           Starting with the list in Exercise 2, write Python statements to do the following:

           a. Append "apple" and 76 to the list.
           #. Insert the value "cat" at index 3.
           #. Insert the value 99 at the start of the list.
           #. Find the index of "hello".
           #. Count the number of 76s in the list.
           #. Remove the first occurrence of 76 from the list.
           #. Remove True from the list using ``pop`` and ``index``.


           .. activecode:: ex_9_3


.. question:: lists_ex_4

   Create a list containing 100 random integers between 0 and 1000 (use iteration, append, and the random module).  Write a function called ``average`` that will take the list as a parameter and return the average.

   .. activecode:: ex_9_4

.. question:: lists_ex_5

           Write a Python function that will take a the list of 100 random integers between 0 and 1000 and return the maximum value.  (Note: there is a builtin function named ``max`` but pretend you cannot use it.)

           .. activecode:: ex_9_5

               import random

               def max(lst):



               print(max(lst))



.. question:: lists_ex_6

   Write a function ``sum_of_squares(xs)`` that computes the sum
   of the squares of the numbers in the list ``xs``.  For example,
   ``sum_of_squares([2, 3, 4])`` should return 4+9+16 which is 29:

   .. activecode:: ex_9_6

      def sum_of_squares(xs):
          # your code here

      ====
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(sum_of_squares([2,3,4]),29,"Tested sum_of_squares on input [2,3,4]")
              self.assertEqual(sum_of_squares([0,1,-1]),2,"Tested sum_of_squares on input [0,1,-1]")
              self.assertEqual(sum_of_squares([5,12,14]),365,"Tested sum_of_squares on input [5,12,14]")

      myTests().main()

.. question:: lists_ex_7

           Write a function to count how many odd numbers are in a list.

           .. activecode:: ex_9_7

              def countOdd(lst):
                  # your code here

              ====
              from unittest.gui import TestCaseGui

              class myTests(TestCaseGui):

                  def testOne(self):
                      self.assertEqual(countOdd([1,3,5,7,9]),5,"Tested countOdd on input [1,3,5,7,9]")
                      self.assertEqual(countOdd([1,2,3,4,5]),3,"Tested countOdd on input [-1,-2,-3,-4,-5]")
                      self.assertEqual(countOdd([2,4,6,8,10]),0,"Tested countOdd on input [2,4,6,8,10]")
                      self.assertEqual(countOdd([0,-1,12,-33]),2,"Tested countOdd on input [0,-1,12,-33]")

              myTests().main()




.. question:: lists_ex_8

   Sum up all the even numbers in a list.

   .. activecode:: ex_9_8

      def sumEven(lst):
          # your code here

      ====
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(sumEven([1,3,5,7,9]),0,"Tested sumEven on input [1,3,5,7,9]")
              self.assertEqual(sumEven([-1,-2,-3,-4,-5]),-6,"Tested sumEven on input [-1,-2,-3,-4,-5]")
              self.assertEqual(sumEven([2,4,6,7,9]),12,"Tested sumEven on input [2,4,6,7,9]")
              self.assertEqual(sumEven([0,1,12,33]),12,"Tested sumEven on input [0,1,12,33]")

      myTests().main()

.. question:: lists_ex_9

           Sum up all the negative numbers in a list.

           .. activecode:: ex_9_9

              def sumNegatives(lst):
                  # your code here

              ====
              from unittest.gui import TestCaseGui

              class myTests(TestCaseGui):

                  def testOne(self):
                      self.assertEqual(sumNegatives([-1,-2,-3,-4,-5]),-15,"Tested sumNegatives on input [-1,-2,-3,-4,-5]")
                      self.assertEqual(sumNegatives([1,-3,5,-7,9]),-10,"Tested sumNegatives on input [1,-3,5,-7,9]")
                      self.assertEqual(sumNegatives([-2,-4,6,-7,9]),-13,"Tested sumNegatives on input [-2,-4,6,-7,9]")
                      self.assertEqual(sumNegatives([0,1,2,3,4]),0,"Tested sumNegatives on input [0,1,2,3,4]")

              myTests().main()




.. question:: lists_ex_10

   Count how many words in a list have length 5.

   .. activecode:: ex_9_10

      def countWords(lst):
          # your code here

.. question:: lists_ex_11

           Sum all the elements in a list up to but not including the first even number.

           .. activecode:: ex_9_11

              def sumUntilEven(lst):
                  # your code here

              ====
              from unittest.gui import TestCaseGui

              class myTests(TestCaseGui):

                  def testOne(self):
                      self.assertEqual(sumUntilEven([1,2,3,4,5]),1,"Tested sumUntilEven on input [1,2,3,4.5]")
                      self.assertEqual(sumUntilEven([1,3,5,7,9]),25,"Tested sumUntilEven on input [1,3,5,7,9]")
                      self.assertEqual(sumUntilEven([2,4,6,7,9]),0,"Tested sumUntilEven on input [2,4,6,7,9]")

              myTests().main()



.. question:: lists_ex_12

   Count how many words occur in a list up to and including the first occurrence of the word "sam".

   .. activecode:: ex_9_12

      def count(lst):
          # your code here



.. question:: lists_ex_13

           Although Python provides us with many list methods, it is good practice and very instructive to think about how they are implemented.  Implement a Python function that works like the following:

           a. count
           #. in
           #. reverse
           #. index
           #. insert


           .. activecode:: ex_9_13

              def count(obj, lst):



              def is_in(obj, lst):  # cannot be called in() because in is a reserved keyword



              def reverse(lst):



              def index(obj, lst):



              def insert(obj, index, lst):



              lst = [0, 1, 1, 2, 2, 3, 4, 5, 6, 7, 8, 9]
              print(count(1, lst))
              print(is_in(4, lst))
              print(reverse(lst))
              print(index(2, lst))
              print(insert('cat', 4, lst))


.. question:: lists_ex_14

   Write a function ``replace(s, old, new)`` that replaces all occurences of
   ``old`` with ``new`` in a string ``s``::

      test(replace('Mississippi', 'i', 'I'), 'MIssIssIppI')

      s = 'I love spom!  Spom is my favorite food.  Spom, spom, spom, yum!'
      test(replace(s, 'om', 'am'),
             'I love spam!  Spam is my favorite food.  Spam, spam, spam, yum!')

      test(replace(s, 'o', 'a'),
             'I lave spam!  Spam is my favarite faad.  Spam, spam, spam, yum!')

   *Hint*: use the ``split`` and ``join`` methods.

   .. activecode:: ex_9_14

      def replace(s, old, new):
          # your code here

      ====
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(replace('Mississippi','i','I'), 'MIssIssIppI',"Tested replace on input 'Mississippi','i','I'")
              self.assertEqual(replace('Bookkeeper','e','A'),
'BookkAApAr',"Tested failed on input 'Bookkeeper','e','A'")
              self.assertEqual(replace('Deeded','e','q'),
'Dqqdqd',"Tested failed on input 'Deeded','e','q'")

      myTests().main()



.. question:: lists_ex_15

   Write the body of the ``isPal`` function. It determines if a list is the same forwards as backwards.



   .. activecode:: ex_9_15

      def isPal(alist):
          # your code goes here


      ====
      from unittest.gui import TestCaseGui
      import random
      import string

      class myTests(TestCaseGui):

          def testOne(self):
              a = random.sample(string.ascii_uppercase,3)
              b = a[:]
              m = random.sample(string.ascii_uppercase,1)
              c = a+m+b
              self.assertEqual(isPal(c),True,"Tested on",c)
              a = random.sample(string.ascii_uppercase,7)
              self.assertEqual(isPal(a),False,"Tested on ",a)
              a = random.sample(string.ascii_uppercase,4)
              b = a[:]
              c = a+b
              self.assertEqual(isPal(c),True,"Tested on ",c)
              a = random.sample(string.ascii_uppercase,8)
              self.assertEqual(isPal(a),False,"Tested on ",a)
              
      myTests().main()

              


