# Connect 4


## Rules of the game

Connect Four is a two-player connection game in which the players first choose a color and then take turns dropping one colored disc from the top into a seven-column, six-row vertically suspended grid. The pieces fall straight down, occupying the lowest available space within the column. The objective of the game is to be the first to form a horizontal, vertical, or diagonal line of four of one's own discs.

##  Objectives

Using the given material, write the algorithms seen in course: MINIMAX and ALPHABETA. Find an heuristic that is easy and fast to compute and the will bring your  AI to victory. 
At the end of the day, a turnament could be organized. Your AI has to run a turn in less than 500 ms.


## Material 

Download the Connect4 archive and unzip to the folder of your choice on your computer. The file contains several source files in Python.
We have implemented two types of players: a human player, who can be instantiated with the class `HumanPlayer`, and an AI, which can be instantiated with the `AIPlayer` class.
Focus on the file `ai_player.py`. This file defines the `AIPlayer` class. 

You can implement as many of methods that are necessary in this class, but it is important to understand:
+ that the constructor of the class (the `__init__` function) must have only the self parameter,
+ that the only method called during the game is `getColumn`.

Therefore, you should not change the name or formal settings of `getColumn`.

 During the game, the method is called with as an effective parameter an instance of the `Board` class that represents the current grid.
In the following section, we describe the interface of this function.
Don't forget to modify the variable name by assigning it your full name. This name will be displayed when your AI will be playing.

In this file, you will be able to implement the different algorithms seen in progress and the associated heuristics.
Before giving it to the teachers, rename this file: `NAME_First name.py`, so that the different files do not don't crash.

### Board class


The `Board` class represents a grid. You don't need to read the code to develop your AI. The columns are numbered from 0 to 6 (included) and the lines from 0 to 5 (included).
A square in the grid can be worth 0 if it is empty, 1 if it is a chip of the first player, -1 if it is a chip of the second player.

You can view a grid using print. The command displays a grid by putting x for the player 1 (value 1) and o for player 2 (value -1).

These are all the operations you can do on a grid:
 + `isFull ()`: returns a Boolean that indicates if all grid boxes are filled.
 + `getRow(row)`: row is an integer between 0 and 5 (included) which indicates the number of the desired line. The function
returns a list representing this line.
+ `getCol(col)`: col is an integer between 0 and 6 (included) which indicates the number of the desired column. The function returns a list representing this column.
+ `getDiagonal(up, shift)`: up is a Boolean that indicates whether you want the diagonal up or down, and shift is the number of the start column (or arrival column if up is False).
+ `getPossibleColumns()`: returns a list with the indices of the columns in which it is possible to play.
+ `getHeight(col)`: returns the height of the col column.
+ `play(player, col)`: returns the line on which the token fell. col is the number of the column in which we drop the token, player is 1 for the first player, -1 for the second.


### How to play?

You can run a graphical interface by running the script `run_ui.py`.
In this script, you can choose which types of players will compete (human or AI). Between lines 13 and 16 of this script, the players are created. By default, player 1 is a random player and player 2 is yourself.

Ideally, replace the random player with your AI, or even have your AI play against itself to prepare the
tournament.