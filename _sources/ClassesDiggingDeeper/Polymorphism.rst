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

Our Fraction class has a method that enables us to add two fractions. However, we may want to add an integer
to a fraction. Lets extend the ``__add__`` method to make this happen in the Fraction class.


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
            if isinstance(val,int):
                other = Fraction(val,1)
            else:
                other = val

            newnum = self.__num * other.__den + self.__den * other.__num
            newden = self.__den * other.__den
            common = gcd(newnum, newden)
            return Fraction(newnum // common, newden // common)

    a = Fraction(2,3)
    b = Fraction(1,2)
    print(a + b)
    print(b + 2)


The ``__add__`` method automatically does the right action. It first checks to see what kind of 
object ``val`` is. If it is an int, it creates a Fraction that has ``val`` as its numerator 
and 1 as its denominator. After this is done, we have two Fractions that we are able to add.

Notice that ``val`` can be either a fraction or an int but ``self`` must be a fraction. That means 
the object to the left of the + sign (in lines 28 and 29) must be a Fraction.

.. important::
   A method may need to operate differently when given different data types. This capacity is called 
   **polymorphism**. A method has "many forms". The proper form is chosen automatically based on the 
   input. This is the fourth principle of object-oriented programming.



