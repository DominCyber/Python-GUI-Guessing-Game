# Python GUI Guessing Game
## Objective
The Python GUI Guessing Game is intended to demonsrate programming use case methodology. This project includes the following steps: Summary and Customer Request, Analysis, Pseudocode Design, and Testing. This hands-on experience aim to establish Python programming variables, statements, and arguments techniques in an impactful manner (interactive GUI).

### Skills Learned
-Proficiency in  Python programming variables, statements, and arguments techniques
<p>-Exercise critical thinking to address customer use cases into an object oriented language</p>
<p>-Convey use case into pseudocode for better visualization of code</p>
<p>-Familiarization with Python modules (import random)</p>
<p>-Familiarization with Python for potential malicious use</p>
  
### Tools Used
-Python 3.2
<p>-Geany Compiler</p>

## Steps

### Summary and Customer Request
Customer requests a GUI modification to an existing terminal-based guessing game.

### Analysis
-The GUI modification is to include:
<p>-labelled entry field for user inputs, computer responses</p>
<p>-buttons for guessing and a new game</p>
<p>-buttons are to be disabled after game loss</p>

### Pseudocode Design
-Import GUI operations from the EasyFrame module, as well as the random module
<p>-Define class to compute GUI, using EasyFrame as a passed variable</p>
<p>-compute initial class function, declaring the first parameter of the class, self, as well as 	the title string variable</p>
<p>-declare pseudorandom variable array</p>
<p>-declare count variable for attempts made by user</p>
<p>-declare string variable for greeting</p>
<p>-compute greeting dimensions in GUI display</p>
<p>-compute title for user input</p>
<p>-declare define user input integer field</p>
<p>-compute next guess prompting button for user</p>
<p>-compute next game prompt button for user</p>
<p>-compute guess function, declaring first parameter of the class</p>
<p>-declare count variable for attempts made by user</p>
<p>-declare variable to retain pseudorandom number</p>
<p>-IF/ELIF/ELSE statement where user input variable equals pseudorandom number</p>
<p>-compute print string that displays number of attempts</p>
<p>-ELIF statement where user input is less than pseudorandom number</p>
<p>-compute print string as input being too small</p>
<p>-ELSE statement</p>
<p>-compute print string as input being too large</p>
<p>-compute new game function declaring first parameter of the class</p>
<p>-declare pseudorandom variable array</p>
<p>-declare count variable for attempts made by user</p>
<p>-declare string variable for greeting</p>
<p>-compute greeting label string</p>
<p>-compute pseudorandom number value to 0</p>
<p>-compute next button functionality to baseline</p>
<p>-compute main function</p>
<p>-process main program class into a loop</p>
<p>-IF statement declaring the main function as the primary function</p>
<p>-TRY-WHILE-EXCEPT statement computing program closure</p>

### Implementation
<p>import random</p>
<p>from breezypythongui import EasyFrame</p>
<p>class GuessingGame(EasyFrame):</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;def __init__(self):</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EasyFrame.__init__(self, title = "Guessing Game")</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.myNumber = random.randint(1, 100)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.count = 0</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;greeting = "Guess a number between 1 and 100."</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.hintLabel = self.addLabel(text = greeting, row = 0, column = 0, sticky = "NSEW", columnspan = 2)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.addLabel(text = "Your guess", row = 1, column = 0)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.guessField = self.addIntegerField(0, row = 1, column = 1)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.nextButton = self.addButton(text = "Next", row = 2, column = 0, command = self.nextGuess)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.newButton = self.addButton(text = "New game", row = 2, column = 1, command = self.newGame)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;def nextGuess(self):</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.count += 1</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;guess = self.guessField.getNumber()</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if guess == self.myNumber:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.hintLabel["text"] = "You've guessed it in " + \</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;str(self.count) + " attempts!"</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.nextButton["state"] = "disabled"</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;elif guess < self.myNumber:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.hintLabel["text"] = "Sorry, too small!"</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;else:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.hintLabel["text"] = "Sorry, too large!"</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;def newGame(self):</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.myNumber = random.randint(1, 100)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.count = 0</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;greeting = "Guess a number between 1 and 100."</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.hintLabel["text"] = greeting</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.guessField.setNumber(0)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.nextButton["state"] = "normal"</p>
<p>def main():</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;GuessingGame().mainloop()</p>
<p>if __name__ == "__main__":</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;try:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;while True:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;main()</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;except KeyboardInterrupt:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;print("\nProgram closed.")</p>

### Testing
<img src="https://i.imgur.com/msTollL.jpg" style="width: 85%;" alt="1">
<p><i>Ref 1: Testing initial functionality of the program</i></p>

<img src="https://i.imgur.com/uNqWjQs.jpg" style="width: 85%;" alt="1">
<p><i>Ref 2: Testing the response of a guess that is too small</i></p>

<img src="https://i.imgur.com/CSam3X6.jpg" style="width: 85%;" alt="1">
<p><i>Ref 3: Testing the response of a guess that is too large</i></p>

<img src="https://i.imgur.com/xNfskUW.jpg" style="width: 85%;" alt="1">
<p><i>Ref 4: Test result of finally guessing the pseudorandom number, which displays number of attempts</i></p>

<img src="https://i.imgur.com/Sqy6W97.jpg" style="width: 85%;" alt="1">
<p><i>Ref 5: Second test, testing of new game function</i></p>

<img src="https://i.imgur.com/o6NUGCC.jpg" style="width: 85%;" alt="1">
<p><i>Ref 6: Third Test; random module seems to be biased toward high two-digit numbers</i></p>
