Class Level Attributes
----------------------

Every Account object we create has its own balance attribute. This is known as an **instance attribute**.  We may wish to make an attribute that is shared by all instances of the class: a **class level attribute**. A class level attribute is declared within the class but not within any particular method definition. 
Just like instance attributes, class level attributes can be either public or private.


We can illustrate this with two simple classes to model various world currencies: the Canadian dollar (CAD) and the Great Britain Pound (GBP). They will include a class level attribute that represents the value of that currency relative to the US Dollar. They will also include a method to ``exchange`` that currency for the comparable number of US Dollars.
    
.. activecode:: oop2_1
    
    class CAD:
        """Canadian Dollar"""
        USD = 0.75   # the value of a CAD in terms of a USD
        def __init__(self, amt):
            self.__amt = amt

        def getAmt(self):
            return self.__amt

        def exchange(self):
            return self.__amt * CAD.USD

    class GBP:
        """Great Britain Pound"""
        USD = 1.25   # the value of a GBP in terms of a USD
        def __init__(self, amt):
            self.__amt = amt

        def getAmt(self):
            return self.__amt

        def exchange(self):
            return self.__amt * GBP.USD

    c = CAD(100) # 100 Canadian dollars
    print(c.getAmt(), 'Canadian dollars is worth')
    print(c.exchange(), 'US dollars')
    b = GBP(100) # 100 GB Pounds
    print(b.getAmt(), 'GB pounds is worth')
    print(b.exchange(), 'US dollars')

.. note::
   The Python version that is provided in this interactive text does not allow us to change the value of a class level attribute after it is created. However, we are not so limited if we run Python locally on our own computer.


Mutable or Immutable?
~~~~~~~~~~~~~~~~~~~~~



Distinquishing between Classes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We have often used the type function to see what kind of an object we are examining. Python also provides a similar Boolean function ``isinstance`` that requires two parameters: an object and a particular type. It then returns True if the object is of the specified type.

.. activecode:: oop2_2
    
    class CAD:
        """Canadian Dollar"""
        USD = 0.75   # the value of a CAD in terms of a USD
        def __init__(self, amt):
            self.__amt = amt

        def getAmt(self):
            return self.__amt

        def exchange(self):
            return self.__amt * CAD.USD

    class GBP:
        """Great Britain Pound"""
        USD = 0.75   # the value of a GBP in terms of a USD
        def __init__(self, amt):
            self.__amt = amt

        def getAmt(self):
            return self.__amt

        def exchange(self):
            return self.__amt * GBP.USD

    a = 100.0
    b = GBP(100)
    c = CAD(100)
    print(isinstance(a, float)
    print(isinstance(b, GBP))
    print(isinstance(c, CAD))

