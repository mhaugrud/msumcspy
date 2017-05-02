Polymorphism
------------

Our Account class has methods that enable us to make deposits and withdrawals. Our balance is in US dollars and our usual transactions are in US dollars. However, we may occasionally use other currencies. If a transaction in some other currency, we must convert that amount to an appropriate amount of US dollars.
Suppose we give the bank teller some Canadian currency to deposit in our account. The teller will convert it to US dollars and place that amount in our account. Lets extend the deposit method to make this happen in our clas


We can illustrate this with two simple classes to model various world currencies: the Canadian dollar (CAD) and the Great Britain Pound (GBP). They will include a class level attribute that represents the value of that currency relative to the US Dollar. They will also include a method to ``exchange`` that currency for the comparable number of US Dollars.
    
.. activecode:: oop2_3
    
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
            """ Create a new account with zero balance"""
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            if isinstance(amount, CAD):
                amt = amount.exchange()
            else:
                amt = amount
            self.balance += amt

    a = Account()
    a.deposit(CAD(100))
    print(a.getBalance())
    a.deposit(100)
    print(a.getBalance())


The deposit method first checks to see what is being deposited. If it is Canadian dollars, determine its value before adjusting the balance. Otherwise, just adjust the balance.

The deposit method is able to automatically do the right action. It can identify what is being deposited (US or Canadian dollars). The CAD class is able to make the exchange.

.. important::
   A method may need to perform differently when given inputs of different data types. This capacity is called **polymorphism**. A method has "many forms". The proper form is chosen automatically based on the input. This is the third principle of object-oriented programming.



