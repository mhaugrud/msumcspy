.. index:: unit test, equivalence class

Unit Testing
------------

When we write functions that return values, we intend to use them over and over again. However, we want to be 
certain that they return the correct result. To be more certain these functions work correctly we write unit tests.

To write a **unit test**, we must know the correct result when calling the function with a specific input. 

.. activecode:: fnj

    def square(x):
        '''raise x to the second power'''
        return x * x
    
    import test
    print('testing square function')
    test.testEqual(square(10), 100)


``test.testEqual`` is a function that allows us to perform a unit test. It takes two parameters. The first is a call to the function we want to test (square in this example) with a particular input (10 in this example). The second parameter is the correct result that should be produced (100 in this example). ``test.testEqual`` compares what the function returns with the correct result and displays whether the unit test passes or fails.

.. admonition:: Extend the program ...

   On line 8, write another unit test (that should pass) for the square function.

.. note::
   When we write unit tests, we should consider **equivalence classes** for the function. That is, inputs that result in significantly different results.

   For example, consider a function that is to calculate the square root of an input. There are two equivalence classes: 1) the input is zero or larger, 2) the input is less than zero.

   It is important to have at least one test for each equivalence class. 

   Semantic errors are often caused by imroperly handling the boundaries between equivalence classes. The boundary for the square root problem is zero. It is important to have a test for each boundary.