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

Screen Clicks
-------------

We can bind a mouse click to a ``Screen`` object.

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


Turtle Clicks
-------------

We can also bind a mouse click to an individual ``Turtle`` object.

.. code-block:: python

    import turtle

    def main():
        def h_a(x, y):
            wn.title('a clicked at {} {}'.format(x,y))
            a.forward(25)


        def h_b(x, y):
            wn.title('b clicked at {} {}'.format(x,y))
            b.forward(25)

        wn = turtle.Screen()
        wn.title("Handle mouse clicks on turtles!")

        a = turtle.Turtle()
        a.shape('turtle')
        b = turtle.Turtle()
        b.penup()
        b.goto(0,50)
        b.pendown()
        b.shape('turtle')

        a.onclick(h_a)        # associate a left button click on turtle a
        b.onclick(h_b)        # associate a left button click on turtle b

    main()

Generalizing Turtle Clicks
--------------------------

In the previous example we wrote handler functions specifically for each turtle. Now we show how to write
a general function that can be employed by any turtle object. (This topic will be discussed in more detail
in a future chapter.)

First we create our own version of a ``Turtle``. ``MyTurtle`` is able to do anything that a standard ``Turtle`` 
from the turtle module can do. Next, we define a new function (a method) for ``MyTurtle``.

.. code-block:: python

    import turtle

    class MyTurtle(turtle.Turtle):
        '''my version of a Turtle that is able to respond to the fwd message'''
        def fwd(t, x, y):
            t.forward(25)

    def main():
        wn = turtle.Screen()
        wn.title("Handle mouse clicks on turtles!")

        a = MyTurtle()
        a.shape('turtle')
        b = MyTurtle()
        b.penup()
        b.goto(0,50)
        b.pendown()
        b.shape('turtle')

        a.onclick(a.fwd)        # associate a left button click on MyTurtle a
        b.onclick(b.fwd)        # associate a left button click on MyTurtle b

    main()

The handler functions in the previous section (13.4.2) has 2 parameters, the ``x`` and ``y`` coordinates
of the mouse click. The ``fwd`` method in this example has another parameter ``t``. It indicates which
``MyTurtle`` was clicked.

