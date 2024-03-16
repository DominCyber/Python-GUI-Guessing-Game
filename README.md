# Python-GUI-Guessing-Game
# Python GUI Guessing Game
## Objective
The Python GUI Guessing Game is intended to demonsrate programming use case methodology. This project includes the following steps: Summary and Customer Request, Analysis, Pseudocode Design, and Testing. This hands-on experience aim to establish Python programming variables, statements, and arguments techniques in an impactful manner (interactive GUI).

### Skills Learned
-Proficiency in  Python programming variables, statements, and arguments techniques
-Exercise critical thinking to address customer use cases into an object oriented language
-Convey use case into pseudocode for better visualization of code
-Familiarization with Python modules (import random)
-Familiarization with Python for potential malicious use
  
### Tools Used
-Python 3.2
-Geany Compiler

## Steps

### Summary and Customer Request
Customer requests a GUI modification to an existing terminal-based guessing game.

### Analysis
-The GUI modification is to include:
-labelled entry field for user inputs, computer responses
-buttons for guessing and a new game
-buttons are to be disabled after game loss

### Pseudocode Design
-Import GUI operations from the EasyFrame module, as well as the random module
-Define class to compute GUI, using EasyFrame as a passed variable
-compute initial class function, declaring the first parameter of the class, self, as well as 	the title string variable
-declare pseudorandom variable array
-declare count variable for attempts made by user
-declare string variable for greeting
-compute greeting dimensions in GUI display
-compute title for user input
-declare define user input integer field
-compute next guess prompting button for user
-compute next game prompt button for user
-compute guess function, declaring first parameter of the class
-declare count variable for attempts made by user
-declare variable to retain pseudorandom number
-IF/ELIF/ELSE statement where user input variable equals pseudorandom 	n		 number
-compute print string that displays number of attempts
-ELIF statement where user input is less than pseudorandom number
-compute print string as input being too small
-ELSE statement 
-compute print string as input being too large
-compute new game function declaring first parameter of the class
-declare pseudorandom variable array
-declare count variable for attempts made by user
-declare string variable for greeting
-compute greeting label string
-compute pseudorandom number value to 0
-compute next button functionality to baseline
-compute main function
-process main program class into a loop
-IF statement declaring the main function as the primary function
-TRY-WHILE-EXCEPT statement computing program closure

### Implementation
import random
from breezypythongui import EasyFrame
class GuessingGame(EasyFrame):
    def __init__(self):
        EasyFrame.__init__(self, title = "Guessing Game")
        self.myNumber = random.randint(1, 100)
        self.count = 0
        greeting = "Guess a number between 1 and 100."
        self.hintLabel = self.addLabel(text = greeting, row = 0, column = 0, sticky = "NSEW", columnspan = 2)
        self.addLabel(text = "Your guess", row = 1, column = 0)
        self.guessField = self.addIntegerField(0, row = 1, column = 1)
        self.nextButton = self.addButton(text = "Next", row = 2, column = 0, command = self.nextGuess)
        self.newButton = self.addButton(text = "New game", row = 2, column = 1, command = self.newGame)
    def nextGuess(self):
        self.count += 1
        guess = self.guessField.getNumber()
        if guess == self.myNumber:
            self.hintLabel["text"] = "You've guessed it in " + \
                                     str(self.count) + " attempts!"
            self.nextButton["state"] = "disabled"
        elif guess < self.myNumber:
            self.hintLabel["text"] = "Sorry, too small!"
        else:
            self.hintLabel["text"] = "Sorry, too large!"
    def newGame(self):
        self.myNumber = random.randint(1, 100)
        self.count = 0
        greeting = "Guess a number between 1 and 100."
        self.hintLabel["text"] = greeting
        self.guessField.setNumber(0)
        self.nextButton["state"] = "normal"
def main():
    GuessingGame().mainloop()
if __name__ == "__main__":
    try:
        while True:
            main()
    except KeyboardInterrupt:
        print("\nProgram closed.")
        
### Testing

  <img src="https://imgur.com/msTollL" />



drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

*Ref 1: Network Diagram*
