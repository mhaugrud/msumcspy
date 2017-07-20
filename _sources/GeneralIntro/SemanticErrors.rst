..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: intro-
   :start: 1

.. index:: semantic error, logic error, error; semantic, error; logic

Semantic Errors
---------------

The third type of error is the **semantic error** or **logic error**. If there is a semantic error
in your program, it will run successfully in the sense that the computer will
not generate any error messages.  However, your program will not do the right thing. It will do
something else. Specifically, it will do what you told it to do.

The problem is that the program you wrote is not the program you wanted to
write. The meaning of the program (its semantics) is wrong.  Identifying
semantic errors can be tricky because it requires you to work backward by
looking at the output of the program and trying to figure out what it is doing.

**Check your understanding**

.. mchoice:: mc1n
   :answer_a: Attempting to divide by 0.
   :answer_b: Forgetting a closing parenthesis character where one is required.
   :answer_c: Dividing the gallons consumed by the miles driven when calculating the MPG of a vehicle.
   :correct: c
   :feedback_a: Python cannot reliably tell if you are trying to divide by 0 until it is executing your program (e.g., you might be asking the user for a value and then dividing by that value - you cannot know what value the user will enter before you run the program).
   :feedback_b: This is a problem with the formal structure of the program.  Python knows when there is a missing parenthesis by looking at the code without running it.
   :feedback_c: This will produce the wrong answer because the programmer implemented the solution incorrectly.  This is a semantic error.

   Which of the following is a semantic error?


.. mchoice:: mc1o
   :answer_a: The programmer.
   :answer_b: The compiler / interpreter.
   :answer_c: The computer.
   :answer_d: The teacher / instructor.
   :correct: a
   :feedback_a: You must fully understand the problem so the you can tell if your program properly solves it.
   :feedback_b: The compiler and / or interpreter will only do what you instruct it to do. It does not understand what the problem is that you want to solve.
   :feedback_c: The computer does not understand your problem. It just executes the instructions that it is given.
   :feedback_d: Your teacher and instructor may be able to find most of your semantic errors, but only because they have experience solving problems.  However it is your responsibility to understand the problem so you can develop a correct solution.


   Who or what typically finds semantic errors?

