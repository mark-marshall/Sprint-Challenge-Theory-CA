### 1. Regular Expressions
Find regexes that match the following. (e.g. find a single regex that matches
both `antelope` and `antelopes`.)

a. Single regex that matches either of these:

    antelope rocks out
    
    antelopes rock out


    ====== ANS ======
    antelopes?\srocks?\sout

b. Regex that matches either of:

    goat
    
    moat

  but not:

    boat


  ====== ANS ======
  [g-m]oat

c. Regex that matches dates in YYYY-MM-DD format. (Year can be 1-4 digits, and
  month and day can each be 1-2 digits). This does not need to verify the date
  is correct (e.g 3333-33-33 can match).

    2000-10-12
  
    1999-1-20
  
    1999-01-20
  
    812-2-10


  ====== ANS ======
  \d{1,4}\-\d{1,2}\-\d{2}

### 2. State Machines

> A useful tool for drawing state machines is [Evan's FSM
> Designer](http://madebyevan.com/fsm/). Add image files 
> showing your state diagrams to this repo to submit.

a. Draw a state machine that corresponds to the following regex:

      ab*c+d?[ef]

  Remember the ε transition can be used to move between states without
  consuming input. 

====== ANS ======
cd State_Diagrams/Regex.png


b. Draw a state machine diagram for the lion and label the transition events that
  cause state transitions.
  
    A lion can be sleeping, eating, hunting, or preening.

====== ANS ======
cd State_Diagrams/Lion.png


You are expected to be able to answer all these questions. Your responses contribute to your Sprint Challenge grade. [Skipping this section *will* prevent you from passing this challenge.]

## Stretch Problems

After finishing your required elements, you can push your work further. These goals may or may not be things you have learned in this module but they build on the material you just studied. Time allowing, stretch your limits and see if you can deliver on the following optional goals:

* The VT-100 terminal (console) outputs text to the screen as it
  receives it over the wire. One exception is that when it receives an
  ESC character (ASCII 27), it goes into a special mode where it looks
  for commands to change its behavior. For example:

      ESC[12;45f
  
  ====== ANS ======
  \e\[\d+\;\d+f

  moves the cursor to line 12, column 45.

      ESC[1m

  changes the font to bold.

  ====== ANS ======
  \e1m

  * Come up with regexes for the two above sequences. The one to set the
    cursor position should accept any digits for the row and column. The
    bold sequence need only accept `1` (and is a trivial regex). (ESC is
    a single character which can be represented with `\e` in the regex.)

  * Draw a state machine diagram for a VT-100 that can consume regular
    character sequences as well as the two above ESC sequences.

> If you're curious, [here are all the VT-100 escape
> sequences](http://ascii-table.com/ansi-escape-sequences-vt-100.php).
> More common these days is a superset of VT-100 called [ANSI escape
> sequences](http://ascii-table.com/ansi-escape-sequences.php). If
> you've ever put colors and stuff in your Bash prompt, this is what you
> used to do it.
>
> One of your instructors was once hired to implement VT-100 emulation
> in an app, and they used a state machine to do it.