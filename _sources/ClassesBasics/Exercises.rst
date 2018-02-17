
Exercises
---------

.. question:: cb_ex_1
   :number: 1

   Write two unit tests for the ``distFrom`` method. It is similar to ``distFromOrigin`` 
   except that it takes a ``Point`` as a parameter and computes the distance between that point 
   and itself. Do not implement the ``distFrom`` method. It currently returns an arbitrary value
   of 0. Your unit tests should check the value that is returned by ``distFrom`` in two 
   different instances where the expected result is not 0.

   .. actex:: ch_c1_01

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

   .. actex:: ch_c1_02

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
   comment ``# your new code goes here``, make two ``Point`` objects. Given that two points fall on 
   the circumference of a circle, find and display the center and radius of that circle.

   .. actex:: ch_c1_03

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

          def halfway(self, other):
              """ Create a point halfway between self and other """
              mx = (self.__x + other.__x) / 2
              my = (self.__y + other.__y) / 2
              return Point(mx, my)

          def distFrom(self, other):
              """ Return the distance from self to other """


      # your new code goes here


.. question:: cb_ex_4


   Write two unit tests for the ``add`` method that takes a ``Point`` as a parameter. It creates
   a new ``Point`` whose x attribute is the sum of the x attributes of itself and the parameter.
   Likewise for its y attribute. Do not implement the ``add`` method. It currently returns an 
   arbitrary ``Point`` of (0,0). Your unit tests should check the value that is returned by 
   ``add`` in two different instances where the expected result is not (0,0).

   .. actex:: ch_c1_04

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

          def add(self, other):
              """ Return a new point that is self added to other """
              return Point(0,0)

      if __name__ == "__main__":
          import test


.. question:: cb_ex_5

   Copy your unit tests from the above question. Then implement the ``add`` method.

   .. actex:: ch_c1_05

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

          def add(self, other):
              """ Return a new point that is self added to other """


      if __name__ == "__main__":
          import test


