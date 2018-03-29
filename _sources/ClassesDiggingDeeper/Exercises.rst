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

   A square is a rectangle which has the same width and height. 

   * write the definition of the ``Square`` class as a subclass of ``Rectangle``
   * write its constructor method, with parameters for its starting point and its size (do not create 
     any new attributes). It could be called as follows:: 
   
        s = Square((30, 50), 70)

   Below the class definition,
 
   * instantiate a Square object
   * use methods get the following and print the results

      * the square 
      * its width
      * its height
      * its starting point
      * its area 
      * its perimeter
              
   .. activecode:: ch_c2_1

      class Rectangle:
          def __init__(self,start,width,height):
              self.__start = start
              self.__width = width
              self.__height = height
        
          def getWidth(self):
              return self.__width
    
          def getHeight(self):
              return self.__height
    
          def getStartPoint(self):
              return self.__start
    
          def __str__(self):
              return 'start={} w={} h={}'.format(self.__start,self.__width,self.__height)
    
          def area(self):
              return self.__width * self.__height
    
          def perimeter(self):
              return (self.__width + self.__height) * 2

  
   
                 
.. question:: cdd_ex_2

   Copy the code from the previous activecode. Change the Rectangle class 3 ``get`` methods 
   to be properties that perform same action as the methods. Add a ``size`` property to the 
   Square class. It returns the length of a side of the square. 

   In the code below the class defintions

   * delete the lines using the area and perimeter methods 
   * use the 4 properties instead of the get methods

   .. activecode:: ch_c2_2  
   
   
                    
   
.. question:: cdd_ex_3

   Copy the code from the previous question. Below the class definitions, delete all the instructions
   except where you instantiate a Square object. Create a Turtle object. 
   Use the Square properties to enable you to draw the square.

   .. activecode:: ch_c2_3
   
   
.. question:: cdd_ex_4

   Change the name of the ``scale`` method to be the magic method for multiplication. Change the 
   tests to use the ``*`` operator (since there is no longer a method named scale). The tests 
   should still pass.

   .. activecode:: ch_c2_4
   
      class Point:
          def __init__(self, initX, initY):
              self.__x = initX
              self.__y = initY

          @property
          def x(self):
              return self.__x

          @property
          def y(self):
              return self.__y

          def scale(self, val):
              """ Return a new point that is self multiplied by val """
              return Point(self.__x * val, self.__y * val)

      if __name__ == "__main__":
          import test
          a = Point(7, -3)
          b = a.scale(2)
          test.testEqual(b.x,14)
          test.testEqual(b.y,-6)
   

.. question:: cdd_ex_5

   Copy the code from the previous question. Make the magic method polymorphic. If the ``val`` parameter
   is a number, the method will operate the way it currently does.
   
   If the ``val`` parameter is a ``Point`` object, the method will return the dot product of the two vectors.
   To calculate the dot product, multiply the two x attributes and multiply the two y attributes. Return the
   sum of those two products. (You can do a web search on dot product if you want further information.) 

   Do not remove your previous tests. But, add another unit test (using the ``*`` operator) for the dot product.

   .. activecode:: ch_c2_5
   

