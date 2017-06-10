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


.. question:: turtle_ex_1
   :number: 1


   Write a program that prints ``We like Python's turtles!`` 100 times.
   ~~~~


   .. activecode::  ex_3_1
      :nocanvas:


.. question:: turtle_ex_2

   .. shortanswer:: turtle_reflect

      Turtle objects have methods and attributes. For example, a turtle has a position and when you move the turtle forward, the position changes.  Think about the other methods shown in the summary above.  Which attibutes, if any, does each method relate to?  Does the method change the attribute?

.. question:: turtle_ex_3


   Write a program that uses a for loop to print
      |  ``One of the months of the year is January``
      |  ``One of the months of the year is February``
      |  ``One of the months of the year is March``
      |  etc ...
   ~~~~


   .. activecode:: ex_3_3


.. question:: turtle_ex_4


   Assume you have a list of numbers ``12, 10, 32, 3, 66, 17, 42, 99, 20``

   a. Write a loop that prints each of the numbers on a new line.
   b. Write a loop that prints each number and its square on a new line.
   ~~~~

   .. activecode:: ex_3_4

.. question:: turtle_ex_5


   Use ``for`` loops to make a turtle draw these regular polygons
(regular means all sides the same lengths, all angles the same):

   * An equilateral triangle
   * A square
   * A hexagon (six sides)
   * An octagon (eight sides)
   ~~~~


   .. activecode:: ex_3_5
      :nocodelens:


.. question:: turtle_ex_6


   Write a program that asks the user for the number of sides, the length of the side, the color, and the fill color of a regular polygon.  The program should draw the polygon and then fill it in.
   ~~~~

   .. activecode:: ex_3_6
      :nocodelens:

.. question:: turtle_ex_7


   A drunk pirate makes a random turn and then takes 100 steps forward, makes another random turn, takes another 100 steps, turns another random amount, etc.  A social science student records the angle of each turn before the next 100 steps are taken.  Her experimental data is ``160, -43, 270, -97, -43, 200, -940, 17, -86``. (Positive angles are counter-clockwise.)  Use a turtle to draw the path taken by our drunk friend.  After the pirate is done walking, print the current heading.
   ~~~~

   .. activecode:: ex_3_7
      :nocodelens:


.. question:: turtle_ex_8

   On a piece of scratch paper, trace the following program and show the drawing.  When you are done, press ``run`` and check your answer.
   ~~~~
   import turtle
   wn = turtle.Screen()
   tess = turtle.Turtle()
   tess.speed(6)
   tess.right(90)
   tess.left(3600)
   tess.right(-90)
   tess.left(3600)
   tess.left(3645)
   tess.forward(-100)

   .. activecode:: ex_3_8
      :nocodelens:

.. question:: turtle_ex_9


   Write a program to draw a shape like this:

   .. image:: Figures/star.png
   ~~~~

   .. activecode:: ex_3_9
      :nocodelens:


.. question:: turtle_ex_10

   Write a program to draw a face of a clock that looks something like this:

   .. image:: Figures/tess_clock1.png
   ~~~~

   .. activecode:: ex_3_10
      :nocodelens:

.. question:: turtle_ex_11

   Write a program to draw some kind of picture.  Be creative and experiment with the turtle methods provided in :ref:`turtle_methods`.
   ~~~~

   .. activecode:: ex_3_11
      :nocodelens:


.. question:: turtle_ex_12

   Create a turtle and assign it to a variable.  When you print its type, what do you get?
   ~~~~

   .. activecode:: ex_3_12
      :nocodelens:


.. question:: turtle_ex_13

   A sprite is a simple spider shaped thing with n legs coming out from a center point. The angle between each leg is 360 / n degrees.

   Write a program to draw a sprite where the number of legs is provided by the user.
   ~~~~

   .. activecode:: ex_3_13
      :nocodelens:





