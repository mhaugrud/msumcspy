.. index:: decorator, class; method, method; class

Decorators and Properties
-------------------------

The exchange rate between Canadian and US dollars changes frequently. We need a method to change 
the class level attribute. This is accomplished with a **class level method** (instead of a 
regular instance method). It affects the class as a whole, not a particular object of the class.
The ``changeRate`` method in the following example is a **class level method**. Notice that we
call this method with the class name.
    
.. activecode:: c2a1
    
    class CAD:
        """Canadian Dollar"""
        __USD = 0.75   # the value of a CAD in terms of a USD (private)
        def __init__(self, amt):
            self.__amount = amt

        def getAmount(self):
            return self.__amount

        def exchange(self):
            return self.__amount * CAD.__USD # using class attribute

        @staticmethod
        def changeRate(rate):
            CAD.__USD = rate # change the class exchange rate

    c = CAD(100) # 100 Canadian dollars
    print(c.getAmount(), 'Canadian dollars is worth')
    print(c.exchange(), 'US dollars')
    print('changing the exchange rate')
    CAD.changeRate(0.8)
    print(c.exchange(), 'US dollars')


.. note::
   ``@staticmethod`` is called a **decorator** (a tool to extend the behavior of a method or 
   function).

.. index:: property

Properties
~~~~~~~~~~

In many of the previous examples we have used a **getter** method (for example, the CAD ``getAmount`` 
method) to return the value of an attribute.

A **property** is a type of decorator that enables us to access an attribute in a more natural fashion.
This leads to code that is more readable and more easily understood.


.. activecode:: c2a2
    
    class CAD:
        """Canadian Dollar"""
        def __init__(self, amt):
            self.__amount = amt

        @property
        def amount(self):
            return self.__amount


    c = CAD(100)
    print(c.amount)
    d = CAD(50)
    print(c.amount + d.amount)


.. note::
   Properties typically have the same name as the attribute they work with.

We can also use a property to change the value of an attribute. In this case it acts as a **setter** method.

.. activecode:: c2a3
    
    class CAD:
        """Canadian Dollar"""
        def __init__(self, amt):
            self.__amount = amt

        @property
        def amount(self):
            return self.__amount

        @amount.setter
        def amount(self, amt):
            if amt >= 0:
               self.__amount = amt


    c = CAD(100)
    print(c.amount)
    c.amount = c.amount - 20
    print(c.amount)
    c.amount = -10 # notice the object does not go to an illegal state
    print(c.amount)
    

.. note::
   The above example illustrates how we can write a setter property. However, ``CAD`` objects should be
   immutable so it is not proper to include this property.

