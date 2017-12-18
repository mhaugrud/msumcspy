..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: gui-12-
   :start: 1

Custom Icons
============

We constantly use icons GUI's. The ``turtle`` module has several standard shapes we can use for turtles.
However, we may wish to incorporate our own shapes for icons. 

First, we need a picture that we will ultimately use as a shape. It must be stored in the .gif format.
Here is one, rocket.gif. Right click and save it on your computer in the same folder as your .py scripts.


.. image:: Figures/rocket.gif
   :alt: rocket.gif


Put the following code in the same folder as rocket.gif


.. code-block:: python

    import turtle

    def main():
        def h(x, y):
            t.forward(30)

        wn = turtle.Screen()
        wn.title("Custom shapes")
        wn.register_shape('rocket.gif')
        t = turtle.Turtle()
        a.left(90)
        a.shape('rocket.gif')

        a.onclick(h)

    main()


