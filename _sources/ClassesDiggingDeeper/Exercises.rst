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

.. question:: cdd_ex_1
   :number: 1

   First copy your definitions of the Point and Rectangle classes from the exercises in the last chapter.
   A square is a rectangle which has the same width and height. Write the definition of the ``Square``
   class as a subclass of ``Rectangle`` and its constructor method. Do not create any new attributes. It
   could be called as follows:: 
   
      r = Square(Point(4, 5), 6)
              
   .. activecode:: ch_c2_1


  
   
                 
.. question:: cdd_ex_2

   Copy the code from the previous activecode. Then add the following accessor method to the 
   Square class: ``getSize``. It returns the length of a side of the square. 

   .. activecode:: ch_c2_2  
   
   
                    
.. question:: cdd_ex_3

   Copy the code from the previous activecode. After the classes, instantiate a Square object. Use the 
   ``getSize``, ``getWidth``, and ``getHeight`` methods with it and display the results. (They should 
   all produce the same value.) Use the ``__str__``, ``getStartPoint``, ``area``, and ``perimeter`` 
   methods with it and display the results.

   .. activecode:: ch_c2_3  
   
   
.. question:: cdd_ex_4

   Copy the code from question 2. After the classes, instantiate a Square object. Create a Turtle object. 
   Use the Square accessor methods to enable you to draw the square.

   .. activecode:: ch_c2_4
   
   
.. question:: cdd_ex_5

   Copy the code from question 5 of the exercises from the last chapter (it includes the ``scale`` method for 
   the Point class). 
   
   Change the scale method to be the magic method for multiplication. Change the tests to use the ``*`` 
   operator. The tests should still pass.

   .. activecode:: ch_c2_5
   

   
.. question:: cdd_ex_6

   Copy the code from the previous question. Make this magic method polymorphic. If the ``val`` parameter
   is a number, the method will operate the way it currently does.
   
   If the ``val`` parameter is a ``Point`` object, the method will return the dot product of the two vectors.
   To calculate the dot product multiply the two x attributes, multiply the two y attributes, then add those
   two products.

   Include a unit test for the dot product.

   .. activecode:: ch_c2_6
   

