..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: gui-2-
   :start: 1


Text Input and Output
=====================

We have used the ``input`` and ``print`` functions in our previous programs. These functions
perform their actions in the Python Shell Window.

The ``turtle`` module provides similar capabilities utilizing dialog boxes and the turtle ``Screen``.


.. code-block:: python

   import turtle

   def main():
       wn = turtle.Screen()
       wn.title("text example")
       t = turtle.Turtle()
       t.penup()               # so turtle will not leave a trail
       name = wn.textinput('Text Input','What is your name?')
       t.write(name, True)     # True causes turtle to move as characters are displayed
       numb = wn.numinput('Numeric Input','Enter a number')
       t.write(numb, True)
       t.write(type(numb))     # notice what is displayed!!!        

   main()

Notice ``textinput`` and ``numinput`` are ``Screen`` methods and write is a ``Turtle`` method.

