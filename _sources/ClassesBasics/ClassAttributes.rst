Class Level Attributes
----------------------

Every Account object we create has its own balance attribute. This is known as an **instance attribute**.  We may wish to make an attribute that is shared by all instances of the class: a **class level attribute**. A class level attribute is declared within the class but not within any particular method definition. 

Perhaps we would like a counter to keep track of how many Accounts we have. After we have created this attribute, we can refer to it by prefacing its name with the name of the class ``Account.__counter``.  As each new Account is instantiated, we can increment this attribute. We could even use that counter to assign a number to identify a particular Account. Below the constructor and str methods are modified to utilize the class attribute.


.. activecode:: oop_11
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        __counter = 0
        def __init__(self):
            """ Create a new account with zero balance"""
            self.__balance = 0.00
            Account.__counter += 1
            self.__number = Account.__counter

        def getBalance(self):
            return self.__balance

        def __str__(self):
            return "Account {0} of {1} ${2:,.2f}".format(self.__number,Account.__counter,self.__balance)

    p = Account()
    q = Account()
    r = Account()
    print(p)
    print(q)
    print(r)

As with instance attributes, class level attributes may be private or public.

Lets now write a simple class to model the Canadian dollar (CAD). We will include a class level attribute that represents the value of the CAD relative to the US Dollar. We will also include a method to exchange CAD for the comparable number of US Dollars.
    
.. activecode:: oop_12
    
    class CAD:
        """Canadian Dollar"""
        USD = 0.75   # the value of a CAD in terms of a USD
        def __init__(self, amt):
            """ Create a new account with zero balance"""
            self.__amt = amt

        def getAmt(self):
            return self.__amt

        def exchange(self):
            return self.__amt * CAD.USD

    cad = CAD(100) # 100 Canadian dollars
    print(cad.getAmt(), 'Canadian dollars is worth')
    print(cad.exchange(), 'US dollars')

