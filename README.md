# Queens-Blood
Card Game: Repository cannot be shared due to class regulations, reach out for more information!

Purpose: This assignment was to create a two player card game where players compete to control rows by placing cards and spreading influence across the board. This game includes changing players, board pawns changing owners, applying unique influence from different cards.

Assumptions:

Players will make their own moves. We only implemented the methods that players can call to make moves and to enforce the rules.
Deck files are given in the same format everytime as a 5x5 char grid.
How to Start: Run the Sanguine file and add this in the config for program arguments: docs/example.deck This runs a sample game with predefined moves. This uses the .docs/example.deck given in the assignment.

Design Key Components:

Model package
This is a passive package that needs to be called on to play a game. It contains all of the game logic, rules, and scoring. It enforces the rules, reacts to player moves, and maintains invariants.
TextualView package
This package converts the model to a String so we can see the game being played. This is a read only package and doesn't change anything in the state.
Sanguine
This is the entry point to play a game. Since 7.3 of the assignment states that we dob't need a controller for this assignment, we just created a game that autoplays and displays results.
For the visualization of this game we chose to stick with the format given in the assignment as seen below where it can be read as REDSCORE CELLS BLUESCORE, where cells can be either name of player (R or B), _, or number of pawns: 2 RR__3 0 0 2__1B 1 0 11_1B 3

Design Key Subcomponents:

Inside the Model package we created four main classes for the game to work
The lowest level is Cell, which is a piece of the board. This manages all cell states and updates when a cell gains influence, changes owner, or has a card on it.
One above is the Board class, which is made up of rows and columns of cells. This manages the game moves such as placing cards, and calling the sub cell class to make needed adjustments to influence or states. This holds the score as well.
The BasicSanguine class holds all the game validation and calls for the board to make changes when it is a legal move.
The card interface is a standalone interface that contains information about the cards.
The SanguineStorm interface allows us to create different game implementations.
Source Organization:

The deck should be found in the docs folder
The code to run the game all lies in src/main/java. It is split into a Model package and a TexualView package
Model pacakge contains the BasicSanguine, Board, Card, Cell, and all other game handling logic.
TextualView package contains the SanguineTextualView to handle viewing as a String
Sanguine is also in this filepath. This is the code entry point.
User Player Interface: For future assignments, we envision that we can design a player interface where the player can see the model but the model doesn't need to interact with the player. The players can then be implemented where a human player would interact through a controller and an AI player that makes decisions programmatically.
