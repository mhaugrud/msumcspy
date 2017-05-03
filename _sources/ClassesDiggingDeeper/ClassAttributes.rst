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


.. admonition:: Mutable or Immutable?

   The Account class contains methods that alter the state of an Account object. However, the CAD and GBP classes contain no such methods. Why not? 

   Classes are designed to model real world things. Real bank accounts constantly change so our Account object must be mutable. A dollar, whether US or Canadian, never changes once it is printed. Therefore, our currency objects are also immutable.
