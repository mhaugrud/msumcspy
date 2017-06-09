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

.. question:: spd_ex_1
   :number: 1



            Evaluate the following numerical expressions in your head, then use the active code window to check your results:

            #. ``5 ** 2``
            #. ``2 * 5``
            #. ``15 / 12``
            #. ``12 / 15``
            #. ``15 // 12``
            #. ``12 // 15``
            #. ``15 % 12``
            #. ``12 % 15``
            #. ``5 % 2``
            #. ``2 % 5``
            #. ``6 % 6``
            #. ``0 % 6``
            #. ``2 + (3 - 1) * 10 / 5 * (2 + 3)``

            .. activecode:: ex_2_1

               print(5 ** 2)



.. question:: spd_ex_2

   .. tabbed:: q7

      .. tab:: Question

         Write a small program to simulate a bank account:

         #. The bank balance begins at 0
         #. Display the bank balance with a message stating this is the current balance
         #. Prompt the user to enter the amount to deposit (a floating point number)
         #. Update the bank balance by increasing it by the deposit amount
         #. Display the bank balance with a message stating this the the current balance
         #. Prompt the user to enter the amount to withdraw (a floating point number)
         #. Update the bank balance by decreasing it by the withdrawal amount
         #. Display the bank balance with a message stating this the the current balance

         .. actex:: ex_2_2

      .. tab:: Sample Output

         Current balance = 0
         Deposit how much? 234.56
         Current balance = 234.56
         Withdraw how much? 123.45
         Current balance = 111.11

.. question:: spd_ex_3


            Many people keep time using a 24 hour clock (11 is 11am and 23 is 11pm, 0 is midnight).
            If it is currently 13 and you set your alarm to go off in 50 hours, it will be 15 (3pm).
            Write a Python program to solve the general version of the above problem.
            Ask the user for the time now (in hours), and then ask for the number of hours to wait for the alarm.
            Your program should output what the time will be on the clock when the alarm goes off.

            .. activecode:: ex_2_3



.. question:: spd_ex_4

   It is possible to name the days 0 through 6 where day 0 is Sunday and day 6 is Saturday.  If you go on a wonderful holiday
   leaving on day number 3 (a Wednesday) and you return home after 10 nights.
   Write a general version of the program which asks for the starting day number, and
   the length of your stay, and it will tell you the number of day of the week you will return on.

   .. activecode:: ex_2_4



.. question:: spd_ex_5


            Take the sentence: *All work and no play makes Jack a dull boy.*             Store each word in a separate variable, then print out the sentence on             one line using ``print``.

            .. activecode:: ex_2_5


.. question:: spd_ex_6

   Add parenthesis to the expression ``6 * 1 - 2`` to change its value from 4 to -6.

   .. activecode:: ex_2_6


.. question:: spd_ex_7



            The formula for computing the final amount if one is earning
            compound interest is given on Wikipedia as

            .. image:: Figures/compoundInterest.png
                :alt: formula for compound interest

            Write a Python program that assigns the principal amount of 10000 to
            variable `P`, assign to `n` the value 12, and assign to `r` the interest
            rate of 8% (0.08).  Then have the program prompt the user for the number of years,
            `t`, that the money will be compounded for.  Calculate and print the final
            amount after `t` years.

            .. activecode:: ex_2_7




.. question:: spd_ex_8

   Write a program that will compute the area of a circle.  Prompt the user to enter the radius and print a nice message
   back to the user with the answer.

   .. activecode:: ex_2_8


.. question:: spd_ex_9


            Write a program that will compute the area of a rectangle.  Prompt the user to enter the width and height of the rectangle.
            Print a nice message with the answer.

            .. activecode:: ex_2_9


.. question:: spd_ex_10

   Write a program that will compute MPG for a car.  Prompt the user to enter the number of miles driven and the number of
   gallons used.  Print a nice message with the answer.

   .. activecode:: ex_2_10


.. question:: spd_ex_11


            Write a program that will convert degrees celsius to degrees fahrenheit.

            .. activecode:: ex_2_11


.. question:: spd_ex_12

   Write a program that will convert degrees fahrenheit to degrees celsius.

   .. activecode:: ex_2_12
