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

.. question:: cb_ex_1
   :number: 1

   Add a ``distanceFromPoint`` method that works similar to ``distanceFromOrigin`` except that it
           takes a ``Point`` as a parameter and
           computes the distance between that point and self.

   .. actex:: classes_q1

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
              return "x={}, y={}".format(self.__x, self.__y)

          def halfway(self, target):
              """ Create a point halfway between 2 points """  
              mx = (self.__x + target.__x) / 2
              my = (self.__y + target.__y) / 2
              return Point(mx, my)


.. question:: cb_ex_2

   Add a method ``reflect_x`` to Point which returns a new Point, one which is the
   reflection of the point about the x-axis.  For example,
   ``Point(3, 5).reflect_x()`` is (3, -5)

   .. actex:: ch_cl_02

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
                      return "x={}, y={}".format(self.__x, self.__y)

                  def halfway(self, target):
                      """ Create a point halfway between 2 points """  
                      mx = (self.__x + target.__x) / 2
                      my = (self.__y + target.__y) / 2
                      return Point(mx, my)

              if __name__ == "__main__":
                  import test


.. question:: cb_ex_3


   .. actex:: classes_q3


.. question:: cb_ex_4

   The equation of a straight line is  "y = ax + b", (or perhaps "y = mx + c").
   The coefficients a and b completely describe the line.  Write a method in the
   Point class so that if a point instance is given another point, it will compute the equation
   of the straight line joining the two points.  It must return the two coefficients as a tuple
   of two values.  For example,   ::

      >>> print(Point(4, 11).get_line_to(Point(6, 15)))
      >>> (2, 3)

   This tells us that the equation of the line joining the two points is "y = 2x + 3".
   When will your method fail?

   .. actex:: ch_cl_04

.. question:: cb_ex_5

           Add a method called ``move`` that will take two parameters, call them ``dx`` and ``dy``.  The method will
           cause the point to move in the x and y direction the number of units given. (Hint: you will change the values of the
           state of the point)

           .. actex:: classes_q5


.. question:: cb_ex_6

   Given three points that fall on the circumference of a circle, find the center and radius of the circle.

   .. actex:: classes_q6

