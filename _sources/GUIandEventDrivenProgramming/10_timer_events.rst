..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: gui-10-
   :start: 1


Timer Events
============


.. code-block:: python

   import turtle

   def main():
       def h1():
           t.forward(100)
           t.left(56)
           wn.ontimer(h1, 1000)   # wait 1000 milliseconds then restart handler

       wn = turtle.Screen()
       wn.title("Using a timer to get events!")

       t = turtle.Turtle()
       h1()

main()

