Private Attributes
------------------

Each Account object has a balance attribute. What would happen if we tried to change it directly instead of using the deposit or withdraw methods? Could we get into an illegal state that way?


.. activecode:: oop1_7
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            if amount >= 0:
                self.balance += amount

        def withdraw(self, amount):
            if self.balance >= amount:
                self.balance -= amount

    p = Account()
    print(p.getBalance())
    p.balance = -12345
    print(p.getBalance())

This is definitely a problem. We provided methods that prevent an Account getting into an illegal state. But this was easily circumvented by directly accessing the attribute. This could be done since balance is a **public** attribute. Public attributes can be directly manipulated **outside** of the class definition.

We can prevent this by using **private** atttibutes. To make an attribute private, preface its name with two underscore characters ``__balance``. We read this as dunder (double underscore) balance.
    
.. activecode:: oop1_8
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            if amount >= 0:
                self.__balance += amount

        def withdraw(self, amount):
            if self.__balance >= amount:
                self.__balance -= amount

    p = Account()
    print(p.getBalance())
    p.__balance = -12345
    print(p.getBalance())

Now the balance is not affected. Private attributes prevent anyone from directly accessing them **outside** of the class definition. 

.. important::
   The only way to access private attributes is through the methods that are provided in the class definition. This protects the attributes from misuse. **Information hiding** is the second central principle of object-oriented programming. 

.. note::
    In contrast to other programming languages like C++ and Java, Python only partially supports information hiding.
