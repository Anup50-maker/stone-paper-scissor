<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->
### Stone-Paper-Scissor
This project implements how does the code compute the decision making using FSM
## How it works

The design uses four main states to control the game:
State Name         Binary Code         Description
S_IDLE             	000                Waiting for the start signal.
S_EVALUATE          001                Evaluates the moves of both players.
S_RESULT            010                Displays the result (Winner, Tie, or Invalid).
S_RESET             011                Resets the game back to the idle state.

## How to test

# INPUTS:
Signal	      Width           	Description
clk	          1-bit	            Clock signal for synchronous state transitions.
reset	        1-bit	            Asynchronous reset to return to S_IDLE.
p1_move	      2-bit            	Player 1 move: 00=Stone, 01=Paper, 10=Scissors, 11=Invalid.
p2_move	      2-bit	            Player 2 move: 00=Stone, 01=Paper, 10=Scissors, 11=Invalid.
start       	1-bit	            Triggers evaluation of moves.
mode	        1-bit	            Debug mode toggle (optional).

# OUTPUTS:
Signal	      Width	            Description
winner	      2-bit	            00=Tie, 01=Player 1 wins, 10=Player 2 wins, 11=Invalid move.
state	        3-bit	            Current FSM state for debugging and visualization.
debug	        3-bit	            Shows recent moves and internal signals for debug.

## Example Test Cases:

P1 Move     	P2 Move	         Expected Winner
00 (Stone)	  10 (Scissors)	   01 (Player 1 wins)
01 (Paper)	  00 (Stone)	     01 (Player 1 wins)
10 (Scissors)	01 (Paper)	     01 (Player 1 wins)
00 (Stone)	  00 (Stone)	     00 (Tie)
11 (Invalid)	01 (Paper)	     11 (Invalid)

## External hardware

This project does not require any external components but can be tested using the results from led
