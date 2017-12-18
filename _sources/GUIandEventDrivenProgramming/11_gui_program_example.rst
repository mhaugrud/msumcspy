..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: gui-10-
   :start: 1


A Finite State Machine
======================

A state machine is a system that can be in one of a few different states. We draw a state diagram 
to represent the machine, where each state is drawn as a circle or an ellipse. Certain events occur 
which cause the system to leave one state and transition into a different state. These state 
transitions are usually drawn as an arrow on the diagram.

This idea is not new: when first turning on a cellphone, it goes into a state which we could call 
"Awaiting PIN". When the correct PIN is entered, it transitions into a different state - "Ready to use". 
Then we could lock the phone, and it would enter a "Locked" state, and so on.

A simple state machine that we encounter often is a traffic light. Here is a state diagram which shows 
that the machine continually cycles through three different states, which we’ve numbered 0, 1 and 2.

.. image:: Figures/fsm_traffic_lights.png
   :alt: Traffic Lights

|

We are going to build a program that uses a turtle to simulate the traffic lights. There are three 
lessons here. The first shows off some different ways to use our turtles. The second demonstrates how we 
would program a state machine in Python, by using a variable to keep track of the current state, and a 
number of different if statements to inspect the current state, and take the actions as we change to a 
different state. The third lesson is to use events from the keyboard to trigger the state changes.


.. code-block:: python

    import turtle

    def draw_housing(t):
        """ Draw a nice housing to hold the traffic lights """
        t.pensize(3)
        t.color("black", "darkgrey")
        t.begin_fill()
        t.forward(80)
        t.left(90)
        t.forward(200)
        t.circle(40, 180)
        t.forward(200)
        t.left(90)
        t.end_fill()

    def main():
        def advance_state_machine():
            nonlocal state       # allow assignments stmts to variable from main
            if state == 0:       # Transition from state 0 to state 1
                tess.forward(70)
                state = 1
                tess.fillcolor('orange')
            elif state == 1:     # Transition from state 1 to state 2
                tess.forward(70)
                state = 2
                tess.fillcolor('red')
            else:                    # Transition from state 2 to state 0
                tess.forward(-140)
                state = 0
                tess.fillcolor('green')
            
        wn = turtle.Screen()
        wn.title("Tess becomes a traffic light!")
        wn.bgcolor("lightgreen")
        tess = turtle.Turtle()

        draw_housing(tess)

        tess.penup()
        # Position tess onto the place where the green light should be
        tess.forward(40)
        tess.left(90)
        tess.forward(50)
        # Turn tess into a big green circle
        tess.shape("circle")
        tess.shapesize(3)
        tess.fillcolor("green")

        # A traffic light is a kind of state machine with three states,
        # Green, Orange, Red.  We number these states  0, 1, 2
        # When the machine changes state, we change tess' position and
        # her fillcolor.

        # This variable holds the current state of the machine
        state = 0

        # Bind the event handler to the space key.
        wn.onkey(advance_state_machine, "space")
        wn.listen()                      # Listen for events

    main()

.. note::
   Nesting ``advance_state_machine`` within ``main`` allows it to see the variables it needs. However, 
   to assign a new value to one of those variables requires and extra step. ``nonlocal`` enables us 
   to give ``state`` a new value in the function and have that change reflected in ``main``.

