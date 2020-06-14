## Unbeatable AI Tic Tac Toe Game with Advanced Javascript

In this project you will have to create an AI Tic Tac Toe Game like this (you can use your own css to style it like you want):

<div><img src="https://raw.githubusercontent.com/Grois333/Assets-DI-Javascript-Bootcamp/master/Week%204/Day%205/Mini%20Project%202%20(Tic%20Tac%20Toe)/FireShot%20Capture%20134%20-%20Tic%20Tac%20Toe%20-%20di-tic-tac-toe.surge.sh.png" alt="robot project #1" width="800"></div><br/>

</br>

Here is a demo for you to see and play: [Tic Tac Toe Game](http://di-tic-tac-toe.surge.sh/)

</br>

On first you can make your game beatable against the computer, but the real challenge is to make an unbeatable game so you wont be a match against the computer. 


## Some Tips:


#### In your HTML file:
   - You can use tables or divs to create the boxes, make sure to put id's in each one
   - Create 2 buttons to choose between X and 0
   - And create another button at the end that will be displayed when the game ends, it will call a function to restart the game.
   
#### In your JS file (Make sure to use when required the advanced javascript methods that you learned this week):
   - Create an Array to keep track of whats in each box of the board
   - Create 2 variables to get the selected symbol (X or 0)
   - You can use this Array of Array's to check for the winning combinations of the board: 
   ```javascript
   
 const winCombos = [
 
	   [0, 1, 2],
	   [3, 4, 5],
	   [6, 7, 8],
	   [0, 3, 6],
	   [1, 4, 7],
	   [2, 5, 8],
	   [0, 4, 8],
	   [6, 4, 2]
	
]

```
 - Develope the logic in a function to start the game
 - Make an event listener, if the user chooses the X symbol to play, then the AI will be the opposite one
 - You can create the logic in a onother function to make the turns between the user player and AI
 - After the human player turns or the AI turns, check if its a Tie Game if not make next turn to the AI player
 - Also whenever a turn is taken, check if the game has been won
 - Stop the game if the game has been won
 - You can use the reduce method to find all the places index on the board that have been played by the player
 - If no one wins, it will display null for a draw or if it has been won it will display the indexes and which player won

    
   
   </br>




  
------------------------------------------------
  

## Rules :
- **You have until tonight at 11:59pm** to submit your challenge (using your Github account ).
- You will have to submit the link to the **#daily_challenge** Slack group with the following message:  *Daily_challenge - URL LINK TO YOUR ENTRY"* .
- Submissions not following the above rules will not be taken into account and you don't earn your XP.
- Everyday, before starting the course, each one of you will present his daily challenge !

## Good to know :
- Use whatever tools you have as developers (google, friends, slack, programming buddy etc...) but your instructor will not be offering any help with this daily challenge. Just like a developer you must solve a problem and build something that will be challenging. Nobody will hold your hand during the job so we want to experience that by figuring it all out on your own!


## One Last Thing!
**Good luck!**
