A Point Class
-------------

Here is an example of a class that models Cartesian coordinates in 2-dimensional space.
    

.. activecode:: c1l

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


    p = Point(3, 4)
    print(p)
    print(p.getX())
    print(p.getY())
    q = Point(5, 12)
    print(q)
    print(q.getX())
    print(q.getY())

       

We would like to add a new method to the ``Point`` class ``distFromOrigin``. It calculates the 
distance between itself and the origin (0,0). We start by having this this method return an
arbitrary value of 0. Then we write unit tests that provide examples of what it should return.

.. activecode:: c1m

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
            """ Return a string representation of self """
            return "({}, {})".format(self.__x, self.__y)

        def distFromOrigin(self):
            """ Return the distance between self and (0,0) """
            return 0


    if __name__ == "__main__":
        import test
        a = Point(-4,3)
        test.testEqual(a.distFromOrigin(), 5)

        b = Point(1,1)
        test.testEqual(b.distFromOrigin(), 2**0.5)


.. admonition:: Write the method ...

   Do not change the tests.

   Write the body of the ``distFromOrigin`` method.


In the following example, we see a method that returns a ``Point`` object. The ``halfway`` 
method creates a new ``Point`` that is between itself and another ``Point``.

.. activecode:: c1n

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

  
    p = Point(3, 4)
    q = Point(5, 12)
    print(p)
    print(q)

    mid = p.halfway(q)

    print(mid)
    print(mid.getX())
    print(mid.getY())

The resulting Point, ``mid``, has an x value of 4 and a y value of 8.  Since ``mid`` is a 
``Point`` object, it can be used just like any other ``Point``.

Here we see a unit test for the ``halfway`` method.

.. activecode:: c1o

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

    if __name__ == "__main__":
        import test
        p = Point(3, 4)
        q = Point(5, 12)
        mid = p.halfway(q)
        test.testEqual(mid.getX(),4)
        test.testEqual(mid.getY(),8)



