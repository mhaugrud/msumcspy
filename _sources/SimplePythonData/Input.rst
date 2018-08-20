..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: data-8-
   :start: 1

.. index:: input, input; dialog

Input
-----

The example on the previous page (codelens cl_ch02_19) works fine but is very limited in that it only works with one value for ``total_secs``.  What if we want to rewrite the program so that it is more general?  One thing we could do is allow users to enter any value they wish for the number of seconds.  The program could then print the proper result for that starting value.

In order to do this, we need a way to get **input** from the user.  Luckily, in Python there is a built-in function to accomplish this task.  As you might expect, it is called ``input``.

.. youtube:: 2KYixkCBXSQ
    :divid: inputvid
    :height: 315
    :width: 560
    :align: left

|

.. sourcecode:: python

    name = input("Please enter your name: ")

The input function allows the user to provide a **prompt string**.  When the function is evaluated, the prompt is
shown. The user of the program can enter the name and press `return`. When this happens the text that has been entered is returned from the `input` function, and in this case assigned to the variable `name`.  Make sure you run this example a number
of times and try some different names in the input box that appears.

.. activecode:: sdu

    name = input("Please enter your name: ")
    print("Hello,", name)

It is very important to note that the ``input`` function returns a **string** value.  Even if you asked the user to enter their age, you would get back a string like ``"19"``.

.. admonition:: Prove it ...

   - On line 3, type a print statement to display the **type** of ``name``.
   - Run the program and enter your name. 
   - Run it again and enter a number. Notice the type is the same in either case.
  


It is your job, as the programmer, to take that string and make an int or a float from it, using the ``int`` or ``float`` constructor functions we saw earlier.

To modify the codelens example, we will add an input statement to allow the user to enter the number of seconds.  Then we will convert that string to an integer.  From there the process is the same as before.  To complete the example, we will print some appropriate output.

.. activecode:: sdv

    str_seconds = input("Please enter the number of seconds you wish to convert")
    total_secs = int(str_seconds)

    hours = total_secs // 3600
    secs_still_remaining = total_secs % 3600
    minutes =  secs_still_remaining // 60
    secs_finally_remaining = secs_still_remaining  % 60

    print("Hrs=", hours, "mins=", minutes, "secs=", secs_finally_remaining)


The variable ``str_seconds`` will refer to the string that is entered by the user. As we said above, even though this string may be ``7733``, it is still a string and not a number.  To construct an integer, we use the ``int`` function. The result is referred to by ``total_secs``.  Now, each time you run the program, you can enter a new value for the number of seconds to be converted.

.. admonition:: Modify the program ...

   In line 1 the input function is used which produces a string output. In line 2 we make an integer from this string. It is important to see that both of these steps must be performed. However, we generally combine them in one statement.

   - In line 1, change ``str_seconds`` to ``total_secs``, type ``int(`` between ``=`` and ``input``, and type ``)`` at the end of the line.

   - Comment out line 2.

   - The program still runs the same. What you did in line 1 is called **nesting**, putting one thing inside of another. Since the *input* function is inside of the *int* function, the *input* is executed first. Whatever the user types at the input prompt is then passed to the *int* function.

   - On line 10, type a print function to display the **sum** of these three terms: hours times 3600, minutes times 60, and sec_finally_remaining. If you typed this correctly, line 10 will display the number you entered in line 1.
   

**Check your understanding**

.. mchoice:: mc2i
   :answer_a: &lt;class 'str'&gt;
   :answer_b: &lt;class 'int'&gt;
   :answer_c: &lt;class 18&gt;
   :answer_d: 18
   :correct: a
   :feedback_a: All input from users is read in as a string.
   :feedback_b: Even though the user typed in an integer, it does not come into the program as an integer.
   :feedback_c: 18 is the value of what the user typed, not the type of the data.
   :feedback_d: 18 is the value of what the user typed, not the type of the data.

   What is printed when the following statements execute?

   .. code-block:: python

     n = input("Please enter your age: ")
     # user types in 18
     print ( type(n) )

.. clickablearea:: ca_id_ints
    :question: Click on all of the variables of type `int` in the code below
    :iscode:
    :feedback: Remember input returns a `str`

    :click-incorrect:seconds:endclick: = input("Please enter the number of seconds you wish to convert")
    
    :click-correct:hours:endclick: = int(seconds) // :click-incorrect:3600:endclick:
    :click-correct:secs_still_remaining:endclick: = :click-correct:total_secs:endclick: % 3600
    print(:click-correct:secs_still_remaining:endclick:)

.. clickablearea:: ca_id_str
    :question: Click on all of the variables of type `str` in the code below
    :iscode:
    :feedback: 

    :click-correct:seconds:endclick: = input(:click-incorrect:"Please enter the number of seconds you wish to convert":endclick:)
    
    :click-incorrect:hours:endclick: = int(:click-correct:seconds:endclick:) // :click-incorrect:3600:endclick:
    :click-incorrect:secs_still_remaining:endclick: = :click-incorrect:total_secs:endclick: % 3600
    print(:click-incorrect:secs_still_remaining:endclick:)



