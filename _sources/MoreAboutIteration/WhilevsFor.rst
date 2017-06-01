..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: iter-7-
   :start: 1

Choosing between ``for`` and ``while``
-------------------------------------

``for`` loops are simpler but ``while`` loops provide more control. 

Use a ``for`` loop if you know the maximum number of times that you'll    need to execute the body.  For example, if you're traversing a list of elements, or can formulate a suitable call to ``range``, then choose the ``for`` loop.

So any problem like "iterate this weather model run for 1000 cycles", or "search this list of words", "check all integers up to 10000 to see which are prime" suggest that a ``for`` loop is best.

By contrast, if you are required to repeat some computation until some condition is met, as we did in the randomly walking turtle problem, you'll need a ``while`` loop.

As we noted before, the first case is called **definite iteration** --- we have some definite bounds for what is needed.   The latter case is called **indefinite iteration** --- we are not sure how many iterations we'll need --- we cannot even establish an upper bound!


As a general rule, use a ``for`` loop whenever possible. This is because it is much more work to manage a ``while`` loop. You must properly initialize, test, and modify the loop control variable. If you fail to do any these activities properly, the while loop will not work. In a for loop all these tasks are handled automatically.



.. note::

  This workspace is provided for your convenience.  You can use this activecode window to try out anything you like.

  .. activecode:: scratch_07_03




