..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: strings-13-
   :start: 1

.. index:: L-System

L-Systems
---------

This section describes a much more interested example of string iteration and the accumulator pattern.  Even 
though it seems like we are doing something that is much more complex, the basic processing is the same as was 
shown in the previous sections.

In 1968 Astrid Lindenmayer, a biologist, invented a formal system that
provides a mathematical description of plant growth known as an
**L-system**.  L-systems were designed to model the growth of biological
systems.  You can think of L-systems as containing the instructions for how
a single cell can grow into a complex organism.  L-systems can be used to
specify the **rules** for all kinds of interesting patterns.  In our case, we are going to use them to specify 
the rules for drawing pictures.

The rules of an L-system are really a set of instructions for transforming
one string into a new string.  After a number of these string transformations
are complete, the string contains a set of instructions.  Our plan is to let these instructions direct a turtle
as it draws a picture.

To begin, we will look at an example set of rules:

========  =====================
A         Axiom
A -> B    Rule 1 Change A to B
B -> AB   Rule 2 Change B to AB
========  =====================

Each rule set contains an axiom which represents the starting point in the transformations that will follow.  
The rules are of the form::

        left hand side -> right hand side
        
where the left hand side is a single symbol and the right had side is a sequence of symbols.  You can think of 
both sides as being simple strings. The way the rules are used is to replace occurrences of the left hand side 
with the corresponding right hand side.

Now let's look at these simple rules in action, starting with the string A::

    A
    B      Apply Rule 1 to A
    AB     Apply Rule 2 to B
    BAB    Apply Rule 1 to A, Rule 2 to B
    ABBAB  Apply Rule 2 to B, Rule 1 to A, Rule 2 to B

Notice that each line represents a new transformation for entire string.  Each character that matches a 
left-hand side of a rule in the original has been replaced by the corresponding right-hand side of that 
same rule.  After doing the replacement for each character in the original, we have one transformation.

So how would we encode these rules in a Python program?  There are a couple
of very important things to note here:

#. Rules are very much like if statements.
#. We are going to start with a string and iterate over each of its characters.
#. As we apply the rules to one string we leave that string alone and create
   a brand new string using the accumulator pattern.  When we are all done with the original we replace it
   with the new string.

Let's look at a simple Python program that implements the example set of rules described
above.

.. activecode::  string_lsys

    import turtle

    def applyRules(c):
        if c == 'A':
            return 'B'   # Rule 1
        elif c == 'B':
            return 'AB'  # Rule 2
        else:
            return c     # no rules apply so keep the character

    def processString(oldStr):
        newstr = ""
        for ch in oldStr:
            newstr = newstr + applyRules(ch)
        return newstr

    def createLSystem(timesToRepeat,axiom):
        startString = axiom
        endString = ""
        for i in range(timesToRepeat):
            endString = processString(startString)
            startString = endString
        return endString


    def main():
        instr = createLSystem(4, "A")
        print(instr)


    main()

Try running the example above with different values for the ``timesToRepeat``
parameter.  You should see that for values 1, 2, 3, and 4, the strings generated follow the
example above exactly.

One of the nice things about the program above is that if you want to
implement a different set of rules, you don't need to re-write the entire
program. All you need to do is re-write the applyRules function.

Suppose you had the following rules:

=========  =======================
X          Axiom
X -> XYFL  Rule 1 Change X to XYFL
Y -> YF    Rule 2 Change Y to YF
=========  =======================

.. admonition:: Modify the program ...

   What kind of a string would these rules create?  Modify the program above to implement this new set of rules.

This L-system uses symbols that will have special meaning when we use them later with the turtle to draw a picture.

====  ===================================
F     Go forward by some number of units
L     Turn left by some degrees
====  ===================================


Pretty simple so far.  As you can imagine this string will get pretty long
with a few applications of the rules.  You might try to expand the string a
couple of times on your own just to see.

The last step is to take the final string and turn it into a picture.  Let's
assume that we are always going to go forward by 5 units.  In
addition we will also assume that when the turtle turns left we'll
turn by 90 degrees.  Now look at the string ``XYFLYFFL``.  You might try to
use the explanation above to show the resulting picture that this simple string represents.  At this point, 
it's not a very exciting drawing, but once we expand it a few times it will get a lot more interesting.

To create a Python function to draw a string we will write a function called
``drawLsystem``  The function will take three parameters:

* An string that contains the results of expanding the rules above.
* An angle to turn (for example 90)
* A distance to move forward (for example 5)

.. sourcecode:: python

    def drawLSystem(instructions,angle,distance):
        t = turtle.Turtle()
        t.speed(0)       # make turtle draw quickly
        for cmd in instructions:
            if cmd == 'F':
                t.forward(distance)
            elif cmd == 'L':
                t.left(angle)
            # ignore other characters

.. admonition:: Extend the program ...

   - Place the drawLsystem function between the createLSystem and main functions in the above activecode
   - In the main function, call the drawLSystem function with the string produced by createLSystem, and values mentions above for angle and distance
   - Try rather large values (greater than 30) for the timesToRepeat argument when calling createLSystem


