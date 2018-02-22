
Exercises
---------

.. question:: cb_ex_1
   :number: 1

   Write two unit tests for the ``distFrom`` method. It is similar to ``distFromOrigin`` 
   except that it takes a ``Point`` as a parameter and computes the distance between that point 
   and itself. Do not implement the ``distFrom`` method. It currently returns an arbitrary value
   of 0. Your unit tests should check the value that is returned by ``distFrom`` in two 
   different instances where the expected result is not 0.

   .. activecode:: ch_c1_1

      class Point:

          def __init__(self, initX, initY):
              """ Create a new point at the given coordinates """
              self.__x = initX
              self.__y = initY

          def getX(self):
              """ Get its x coordinate """
              return self.__x

          def getY(self):
              """ Get its y coordinate """
              return self.__y

          def __str__(self):
              """ Return a string representation of the point """
              return "({}, {})".format(self.__x, self.__y)

          def halfway(self, other):
              """ Create a point halfway between self and other """
              mx = (self.__x + other.__x) / 2
              my = (self.__y + other.__y) / 2
              return Point(mx, my)

          def distFromOrigin(self):
              """ Return the distance from self to (0,0) """  
              return (self.__x**2 + self.__y**2)**0.5

          def distFrom(self, other):
              """ Return the distance from self to other """
              return 0

      if __name__ == "__main__":
          import test


.. question:: cb_ex_2

   Copy your unit tests from the above question. Then implement the ``distFrom`` method.

   .. activecode:: ch_c1_2

      class Point:

          def __init__(self, initX, initY):
              """ Create a new point at the given coordinates """
              self.__x = initX
              self.__y = initY

          def getX(self):
              """ Get its x coordinate """
              return self.__x

          def getY(self):
              """ Get its y coordinate """
              return self.__y

          def __str__(self):
              """ Return a string representation of the point """
              return "({}, {})".format(self.__x, self.__y)

          def halfway(self, other):
              """ Create a point halfway between self and other """
              mx = (self.__x + other.__x) / 2
              my = (self.__y + other.__y) / 2
              return Point(mx, my)

          def distFromOrigin(self):
              """ Return the distance from self to (0,0) """  
              return (self.__x**2 + self.__y**2)**0.5

          def distFrom(self, other):
              """ Return the distance from self to other """


      if __name__ == "__main__":
          import test


.. question:: cb_ex_3

   Copy your implementation of the ``distFrom`` method from the previous question. Then, below the 
   comment ``# your new code goes here``, instantiate two ``Point`` objects. Given that two points 
   fall on the circumference of a circle, find and display the center and radius of that circle.

   .. activecode:: ch_c1_3

      class Point:

          def __init__(self, initX, initY):
              """ Create a new point at the given coordinates """
              self.__x = initX
              self.__y = initY

          def getX(self):
              """ Get its x coordinate """
              return self.__x

          def getY(self):
              """ Get its y coordinate """
              return self.__y

          def __str__(self):
              """ Return a string representation of the point """
              return "({}, {})".format(self.__x, self.__y)

          def halfway(self, other):
              """ Create a point halfway between self and other """
              mx = (self.__x + other.__x) / 2
              my = (self.__y + other.__y) / 2
              return Point(mx, my)

          def distFrom(self, other):
              """ Return the distance from self to other """


      # your new code goes here


.. question:: cb_ex_4


   Write two unit tests for the ``scale`` method that takes a number as a parameter. It creates
   a new ``Point`` whose x is the x of the original point multiplied by the parameter.
   Likewise for its y attribute. Do not implement the ``add`` method. It currently returns an 
   arbitrary ``Point`` of (0,0). Your unit tests should check the value that is returned by 
   ``scale`` in two different instances where the expected result is not (0,0).

   .. activecode:: ch_c1_4

      class Point:

          def __init__(self, initX, initY):
              """ Create a new point at the given coordinates """
              self.__x = initX
              self.__y = initY

          def getX(self):
              """ Get its x coordinate """
              return self.__x

          def getY(self):
              """ Get its y coordinate """
              return self.__y

          def __str__(self):
              """ Return a string representation of the point """
              return "({}, {})".format(self.__x, self.__y)

          def scale(self, val):
              """ Return a new point that is self multiplied by val """
              return Point(0,0)

      if __name__ == "__main__":
          import test


.. question:: cb_ex_5

   Copy your unit tests from the above question. Then implement the ``scale`` method.

   .. activecode:: ch_c1_5

      class Point:

          def __init__(self, initX, initY):
              """ Create a new point at the given coordinates """
              self.__x = initX
              self.__y = initY

          def getX(self):
              """ Get its x coordinate """
              return self.__x

          def getY(self):
              """ Get its y coordinate """
              return self.__y

          def __str__(self):
              """ Return a string representation of the point """
              return "({}, {})".format(self.__x, self.__y)

          def scale(self, val):
              """ Return a new point that is self multiplied by val """


      if __name__ == "__main__":
          import test


.. question:: cb_ex_6

        
   We can represent a rectangle by knowing three things: the location of its lower left corner (its starting
   point), its width, and its height. Write a class definition and constructor method for a Rectangle class 
   (after the definition for the Point class) using this idea.  To instantiate a Rectangle object at location 
   (4,5) with width 6 and height 5, we would do the following::
          
      r = Rectangle(Point(4, 5), 6, 5)
              
   .. activecode:: ch_c1_6

      class Point:
          def __init__(self, initX, initY):
              """ Create a new point at the given coordinates """
              self.__x = initX
              self.__y = initY

          def __str__(self):
              """ Return a string representation of the point """
              return "({}, {})".format(self.__x, self.__y)

      # your code goes here

  
   
                 
.. question:: cb_ex_7

   Copy the code from the previous activecode. Then add these accessor methods to the Rectangle class: 
   ``getWidth``, ``getHeight``, ``getStartPoint`` (it returns a Point object), and ``__str__``. After 
   the class definitions, instantiate a Rectangle object and use these four methods with it, displaying 
   the results. 

   .. activecode:: ch_c1_7  
   
   
                    

.. question:: cb_ex_8


   Copy the code from the previous activecode. Then add a method ``area`` to the Rectangle class 
   that returns the area of a Rectangle instance::
        
      r = Rectangle(Point(3, 8), 10, 5)
      testEqual(r.area(), 50)

   After the class definitions, instantiate a Rectangle object, use the area method, and display the result.

   .. activecode:: ch_c1_8


.. question:: cb_ex_9

   Copy the code from the previous activecode. Then write a ``perimeter`` method in the Rectangle class so 
   that returns the perimeter of a Rectangle instance::
   
      r = Rectangle(Point(-1, -2), 10, 5)
      testEqual(r.perimeter(), 30)
      
   After the class definitions, instantiate a Rectangle object, use the perimeter method, and display the result.

   .. activecode:: ch_c1_9



