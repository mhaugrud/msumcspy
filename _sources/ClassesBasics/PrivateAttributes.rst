
Private Attributes
------------------

Each Account object has a balance attribute. What would happen if we tried to change it directly instead of 
using the deposit or withdraw methods? Could we get into an illegal state that way?


.. activecode:: c1g
    
    class Account:
        '''Account class to model bank accounts'''
        
        def __init__(self, name):
            '''Create a new account for owner name and a zero balance'''
            self.owner = name
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            '''increase balance by a positive amount'''
            if amount >= 0:
                self.balance += amount

        def withdraw(self, amount):
            '''reduce balance by amount but do not an allow overdraft'''
            if self.balance >= amount:
                self.balance -= amount

    p = Account('Jan')
    print(p.getBalance())
    p.balance = -12345     # trying to directly change the attribute
    print(p.getBalance())  # notice what is displayed

.. caution::

   This is definitely a problem. We provided methods that prevent an Account getting into an illegal state. 
   But this was easily circumvented by directly accessing the attribute. This could be done since balance is 
   a **public** attribute. Public attributes can be directly manipulated **outside** of the class definition.

.. index:: attribute; private, dunder

We can prevent this by using **private** atttibutes. To make an attribute private, preface its name with two 
underscore characters ``__balance``. We read this as dunder (double underscore) balance.
    
.. activecode:: c1h
    
    class Account:
        '''Account class to model bank accounts'''
        
        def __init__(self, name):
            '''Create a new account for owner name and a zero balance'''
            self.__owner = name
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            '''increase balance by a positive amount'''
            if amount >= 0:
                self.__balance += amount

        def withdraw(self, amount):
            '''reduce balance by amount but do not an allow overdraft'''
            if self.__balance >= amount:
                self.__balance -= amount

    p = Account('Jan')
    print(p.getBalance())
    p.__balance = -12345
    print(p.getBalance())

Now the balance is not affected. Private attributes prevent anyone from directly accessing them 
**outside** of the class definition. 

.. index:: information hiding

.. important::

   The second principle of object-oriented programming is **a class is responsible for maintaining the 
   integrity of its objects**. The methods in a well designed class ensure an object will never get into 
   an illegal state. This is accomplished in three ways: 
 
   #. We utilize **information hiding** --- making the attributes private. The only way to access 
      private attributes is through the methods that are provided in the class definition. 
      This protects the attributes from misuse outside of the class. 

   #. The constructor method (__init__) must initialize all the attributes to a legal state.

   #. We must carefully check that our mutator methods never cause an object to go into an illegal state. 
      This includes checking the arguments and the attributes. Recall how this was done in the ``deposit`` 
      and ``withdraw`` methods.

.. note::
   In contrast to other programming languages like C++ and Java, Python only partially supports 
   information hiding. The reason for this is that the designers of the Python language believe 
   programmers should be mature enough to know that directly accessing attributes outside of the 
   class definition is irresponsible. 

