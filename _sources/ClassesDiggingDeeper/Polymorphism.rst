.. index:: isinstance, function; isinstance

Polymorphism
------------

Distinguishing Between Classes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We have often used the ``type`` function to see what kind of an object we are examining. Python also 
provides a similar Boolean function ``isinstance`` that requires two parameters: an object and a 
particular type. It then returns True if the object is of the specified type (or types).

.. activecode:: c2t
    
    class Fraction:
        def __init__(self, top, bottom):
            self.__num = top        # the numerator is on top
            self.__den = bottom     # the denominator is on the bottom

        def __str__(self):
            return '{}/{}'.format(self.__num, self.__den)


    a = 100
    b = 1.23
    c = Fraction(6,5)
    print(isinstance(a, int))
    print(isinstance(b, float))
    print(isinstance(c, Fraction))
    print(isinstance(a, (int,float)))
    print(isinstance(c, (int,float)))


.. index:: polymorphism

Polymorphism
~~~~~~~~~~~~

Since the beginning of the course we have seen an operator or method work differently when used
with different types of objects. For example, the plus operator performs arithmetic addition with 
integers and floats. However, with strings, it does concatenation. Even though different operations
are performed, the actions are reasonably similar.

Our Fraction class has a method that enables us to add two fractions. Lets extend this ``__add__`` 
method so we can also add an integer to a fraction.


.. activecode:: c2u
    
    def gcd(m, n):
        while m % n != 0:
            oldm = m
            oldn = n
            m = oldn
            n = oldm % oldn
        return n

    class Fraction:
        def __init__(self, top, bottom):
            self.__num = top        # the numerator is on top
            self.__den = bottom     # the denominator is on the bottom

        def __str__(self):
            return '{}/{}'.format(self.__num, self.__den)

        def __add__(self,val):
            if isinstance(val,Fraction):
                other = val
            elif isinstance(val,int):
                other = Fraction(val,1)

            newnum = self.__num * other.__den + self.__den * other.__num
            newden = self.__den * other.__den
            common = gcd(newnum, newden)
            return Fraction(newnum // common, newden // common)

    a = Fraction(2,3)
    b = Fraction(1,2)
    print(a + b)
    print(b + 2)


The ``__add__`` method automatically performs the right action. It first checks to see what kind 
of object ``val`` is. If it is an integer, we must first make a Fraction. By using ``val`` as the 
numerator and 1 as the denominator, we have a fraction that has the same value as ``val``. Now 
we have two Fractions that we are able to add as previously.

Notice that ``val`` can be either a fraction or an integer but ``self`` must be a fraction. That 
means the object to the left of the + sign (in lines 30 and 31) must be a Fraction.

.. important::
   A method may need to operate differently when given different types of objects. This capacity is 
   called **polymorphism**. A method has "many forms". The proper form is chosen automatically based 
   on the type of objects involved. This is the fourth principle of object-oriented programming.



