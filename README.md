Sarah Nasser

sarahnasser576@gmail.com

-----------------------------------
Explanation of my program and how to use it:

The program first asks the user whether they want to play TicTacToe on a 3x3 or 4x4 grid. Then, the program asks the user how many rounds they want to play. Afterwards the program plays a game of TicTacToe for the number of rounds chosen by the user between them and the computer player on either grid. The computer player randomly chooses its moves, and the user will be expected to follow the other rules for input, which includes picking a number between 1 and 9 (inclusive) or between 1 and 16 (inclusive) depending on the grid they chose. My program, however, handles mistakes users might do when it comes to input, and all other instructions are stated in the code. At the end of all the rounds, the program states who won the most number of rounds.

Decisions I made while writing my code:

First I created the class TicTacToe. This class plays a game of Tic Tac Toe on a 3x3 or 4x4 grid, depending on user input. In this class, I instantiated an object of the class TicTacToe3x3 called game1 and an object of the class TicTacToe4x4 called game2. In the main method, I wrote a Scanner input that asks the user which grid they want. If the user chooses the 3x3 grid, I called the playGame() method of the TicTacToe3x3 class onto the object game1. Otherwise, if the user chooses the 4x4 grid or does not give valid input (i.e. the user types anything that is not precisely"3x3" or "4x4"), I called the playGame() method of the TicTacToe4x4 class onto the object game2.

The instance variabkes in the class TicTacToe3x3 are rowsColumns, humanWins, and computerWins. rowsColumns is a two-dimensional array with three rows and three columns that represents the TicTacToe grid. humanWins represents the number of rounds the human player won, and computerWins represents the number of rounds the computer player won. In the constructor of this class, I initialized humanWins to 0 and computerWins to 0. This is before the first round even starts. I then wrote the playGame() method. This method plays a game of Tic Tac Toe between the human player and computer player. In playGame(), I wrote the instructions and a Scanner input that asks the user how many rounds they want to play. I used a variable numberRounds to keep track of the user's input. I wrote a try catch structure because the user might type a non-integer value for their input. In the try block, I initialized numberRounds to the user input. The catch block, which catches the possible InputMismatchException, reminds the user to type an integer value for the number of rounds before exiting the program in failure. I also used a variable currentRound to keep track of the current round the user is playing with the computer. Finally, I declared the variable winner, which I later used to store the winner of the TicTacToe game and determine whether the winner is determined yet. All the squares of the grid have to be blank at the beginning of the game, so I used an enhanced for loop and Arrays.fill() method to make all the elements of rowsColumns blank. Next I wrote a while loop, which contains most of the gameplay. The conditional for this while loop is that currentRound <= numberRounds. This conditional ensures that the number of rounds that the game plays is same as the number of rounds the user wants to play. Inside this while loop, I declared a variable numberEmptySpaces, which represents the number of blank spaces in the grid, and initialized it to the integer value 9. I also declared a variable gameResultsMade and initialized it to the boolean value false. This boolean variable keeps track of whether a round ended, whether a conclusion can be made as to who won the round and whether there is a draw. It ensures that the program ends the round at the perfect time. After creating these two variables, I printed the currentRound for user-friendly purposes. I also created two variables humanChoice and computerChoice to keep track of the human player's and computer player's moves. The human player's move is determined by an integer value from 1 to 9 (inclusive) that the user types, and the computer player's move is determined by a randomized numerical value from 1 to 9 (inclusive). I included a try-catch structure regarding humanChoice because the human player might type something that is not an integer. In the try block, I initialized humanChoice to the user's integer input, and the catch block catches the possible InputMismatchException and reminds the user to type an integer between 1 and 9 (inclusive) before exiting the program in failure. I decided to let the human player make their move first and the computer player make their move second. I wrote a while loop that ensures that if the human player writes invalid input (meaning that they write anything that is not a number from 1 to 9 (inclusive)) or tries to write in a spot in the grid that has already been taken by either player, then they get extra chances in their turn to type valid input. Before this while loop, I declared a variable validHumanMove and initialized it to the boolean value false. This boolean variable indicates whether the human player wrote valid input. The conditional statement of my while loop is !validHumanMove, ensuring that not only does the human player get enough chances but they also do not get another chance after giving valid input. In the while loop, I wrote a conditional statement stating that if the human player gives valid input, and if the integer value they give is between 0 and 9 (inclusive), then the value of validHumanMove should be updated to true, terminating the while loop and not giving the human player another chance. I then included an else statement that takes into account instances in which the human player writes an integer value that is not between 1 and 9 (inclusive), and instances in which the human player attempts to replace an O or X on the grid with an X. If the human player chooses an integer value that is less than 1 or greater than 9, I printed a reminder for them to write a number between 1 and 9 (inclusive). If the human player tries to write an X in a space that already has an O or X, I printed a reminder that the spot has already been taken and that they should try again. In the conditional of the while loop checking that the user input is valid, one of the things I needed to do was to check that the human player did not try to write an X in a spot that was not already taken. To do this, I called the method makeHumanMove with the parameter humanChoice. In this method, I wrote conditional statements corresponding each space of the grid to an integer from 1 to 9 (inclusive) and writing X in the spaces the human player chooses as long as those spaces are blank. makeHumanMove also returns true or false regarding whether the human player gave valid input and did not attempt to write an X in a spot that has already been taken. To give the human player another chance when either of these two problems occur, I updated the value of humanChoice to the next user input. After this while loop, I decremented numberEmptySpaces by 1. After the human player's turn, I printed out the grid for user-friendly purposes by printing the value returned by the method drawGrid, which takes in the parameter rowsColumns and constructs and returns the grid. I then wrote code to decide the winner of the round and then terminate the round if there is a winner or draw. Both the human player's move or computer player's move can be the final turn that causes a draw or a conclusion about the winner, so I also had to rewrite this code after the computer player's turn. In this section of my code, I checked whether the method printGameResults, which takes winner, numberEmptySpaces, humanWins, and computerWins as parameters, returns true. If it returns true, I can update the value of gameResultsMade to true and break out of the while loop, terminating the round. In the printGameResults method, I updated the value of winner to the value returned by the method decideWinner, which takes in the parameters rowsColumns and numberEmptySpaces. decideWinner can return four String values indicating the round results and whether they can be determined yet. If the human player wins the round, the method returns "human." If the computer player wins the round, the method returns "computer." If there is a draw, the method returns "draw." If neither of these three cases take place, the method returns "none," incidicating that round results cannot be determined yet and that the round needs to go on. In printGameResults, I then wrote a big conditional determining whether the round can be ended. This conditional checks whether either the human player or computer player won the round or whether there is a draw. Inside this conditional statement, I wrote three conditionals checking these three possible results of the round. If the value of winner is equal to "human," I need to update the number of wins the human player has. I did this by updating the value of humanWins to the integer value returned by the method updateHumanWins. updateHumanWins, which takes humanWins as its parameter, increments humanWins by 1. I also printed that the human player won. If the value of winner is equal to "computer," I need to update the number of wins the computer player has. To do this, I updated the value of computerWins to the integer value returned by the method updateComputerWins, which takes computerWins as its parameter. This method increments computerWins by 1. I also printed that the computer player won. The third conditional checks whether the value of winner is equal to "draw." If this conditional is true, there is no need to update humanWins or computerWins, and I also printed that there is a draw. Inside the big conditional and after the three smaller conditionals, I returned true, indicating that the game results can be determined. Outside of the big conditional, I returned false to indicate that game results cannot be determined yet. In this while loop containing the check with the printGameResults made, after checking whether the round can be terminated, I dealt with the computer player's turn. The while loop deciding whether the computer player does not attempt to write an O in a space already taken and whether they should have another chance to choose a spot in their turn has almost the same logic as the similar while loop doing this with the human player's turn instead. One of the few differences is that in the while loop for the computer player's turn, I did not need to take into account the case in which the computer player chooses an integer that is not between 1 and 9 (inclusive). This is because the computer player's move is stated explicitly in the code to be a randomized integer value in this range. The other difference between the two while loops is that in the conditional statement checking that the computer player chose a valid move, I called the method makeComputerMove with the parameter computerChoice. This method has almost the same logic as makeHumanMove, the only difference being that the computer player writes O's in the grid, not X's. After this while loop (after the computer player's turn), I decremented numberEmptySpaces by 1 and printed the grid. As in the part of my code dealing with the human player's turn, I wrote the same logic that decides whether to end the round, determines the winner, and updates humanWins and computerWins when necessary. I needed to check for all that after the human player's turn and the computer player's turn. At the end of a round, I needed to increment currentRound by 1 (going on to the next round if there is one). I also needed to update all the spots in rowsColumns to blank spaces, in order words resetting the grid to get ready if there is a next possible round (if the value of currentRound is now equal to the value of numberRounds). After all the rounds (after the while loop that runs only if currentRound is less than or equal to numberRounds), I needed to compare humanWins and computerWins to decide who won most of the rounds and whether the number of rounds each player won is equal. I wrote three conditional statements. If humanWins is greater than computerWins, I printed that the human player won most of the rounds. If computerWins is greater than humanWins, I printed that the computer player won most of the rounds. In the else statement, which deals with the case in which humanWins and computerWins are equal, I printed that the human player won the same number of rounds as the computer player.

The logic in the TicTacToe4x4 class is very similar except for a few differences:
- The two dimensional grid array in TicTacToe4x4 has 4 columns and 4 rows.
- Valid user input in this class is that the user types an integer between 1 and 16 (inclusive).
- The computer player's move in this class is between 1 and 16 (inclusive).
- The logic for putting X's and O's and for determining the winner is very similar except that the program now has to deal with 16 numbers instead of 9 and 16 slots instead of 9.
