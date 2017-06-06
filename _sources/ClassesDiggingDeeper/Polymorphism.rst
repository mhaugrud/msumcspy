Polymorphism
------------

Distinguishing between Classes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We have often used the ``type`` function to see what kind of an object we are examining. Python also provides a similar Boolean function ``isinstance`` that requires two parameters: an object and a particular type. It then returns True if the object is of the specified type.

.. activecode:: c2b
    
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
    print(isinstance(a, float))
    print(isinstance(b, CAD))
    print(isinstance(c, CAD))



Polymorphism
~~~~~~~~~~~~

Our Account class has methods that enable us to make deposits and withdrawals. Our balance is in US dollars and our usual transactions are in US dollars. However, we may occasionally use other currencies. If a transaction in some other currency, we must convert that amount to an appropriate amount of US dollars.
Suppose we give the bank teller some Canadian currency to deposit in our account. The teller will convert it to US dollars and place that amount in our account. Lets extend the deposit method to make this happen in our class.


.. activecode:: c2c
    
    class CAD:
        USD = 0.75   # the value of a CAD in terms of a USD
        def __init__(self, amt):
            self.__amt = amt

        def getAmt(self):
            return self.__amt

        def exchange(self):
            return self.__amt * CAD.USD

    class Account:
        def __init__(self):
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            if isinstance(amount, CAD):
                amt = amount.exchange()
            else:
                amt = amount
            self.__balance += amt

    a = Account()
    a.deposit(CAD(100))
    print(a.getBalance())
    a.deposit(100)
    print(a.getBalance())


The deposit method first checks to see what is being deposited. If it is Canadian dollars, determine its value before adjusting the balance. Otherwise, just adjust the balance.

The deposit method is able to automatically do the right action. It can identify what is being deposited (US or Canadian dollars). The CAD class is able to make the exchange.

.. important::
   A method may need to perform differently when given inputs of different data types. This capacity is called **polymorphism**. A method has "many forms". The proper form is chosen automatically based on the input. This is the third principle of object-oriented programming.



