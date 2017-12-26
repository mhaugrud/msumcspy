..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: gui-6-
   :start: 1

Keyboard Events
===============

In GUI programming, we respond to various **events**, such a keyboard presses or mouse clicks.
This is accomplished by associating a specific **event handler** function with the event. 


.. code-block:: python

   import turtle

   def main():
       # The next four functions are our "event handlers"
       def h1():
           t.forward(30)

       def h2():
           t.left(45)

       def h3():
           t.right(45)

       def h4():
           wn.bye()                         # Close down the turtle window

       wn = turtle.Screen()
       wn.title("Handling keypresses!")
       t = turtle.Turtle()

       # associate keypresses to the handlers we've defined
       wn.onkey(h1, "Up")     # up arrow
       wn.onkey(h2, "Left")   # left arrow
       wn.onkey(h3, "Right")  # right arrow
       wn.onkey(h4, "q")      # quit

       # Now we need to tell the window to start listening for events,
       # If any of the keys that we're monitoring is pressed, its
       # handler will be called.
       wn.listen()

   main()

.. note::
   The four event handler functions are nested in the main function. This enables the handlers to see main's
   variables. This is important since we cannot pass arguments to these handler functions. A function thus 
   nested is called a **closure**.

