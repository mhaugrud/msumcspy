..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: gui-7-
   :start: 1

Mouse Events
============

When we first studied the ``turtle`` module, we used the ``exitonclick``
method to respond to a mouse click. Now we will see how to write our own
mouse handler functions.


.. code-block:: python

import turtle

def main():
   def h1(x, y):
      t.goto(x, y)

   def h2(x, y):
       wn.bye()          # close the window and stop the program

   wn = turtle.Screen()
   wn.title("Handle mouse clicks on the window!")

   t = turtle.Turtle()

   wn.onclick(h1)        # associate a left button click on the window
   wn.onclick(h2, btn=3) # 3 indicates right mouse button

main()


.. note::
   The handler functions each have 2 parameters: the x and y coordinates that were clicked.
   When we use the ``onclick`` method, we only specify the name of the handler function, since the
   x and y parameters are automatically supplied. Once again, the handler functions are nested in the 
   main function so they can see main's variables.

