# Assignment 5 - Lists and dictionaries


# Tutorials to review

This assignment uses lists and dictionaries.

Make sure you have reviewed the following topics before starting to work on this assignment. 

Lists: [https://www.py4e.com/lessons/lists](https://www.py4e.com/lessons/lists)
Dictionaries: [https://www.py4e.com/lessons/dictionary](https://www.py4e.com/lessons/dictionary)

## Random numbers

Run the following code to see how random numbers can be generated:

```python
import random
for x in range(10):
  print ( random.randint(1,21) )
```

### Assignment

Two people will play rounds of ['Rocks, paper, scissors'](https://en.wikipedia.org/wiki/Rock%E2%80%93paper%E2%80%93scissors). They each start with $150 in funds. Each round they will bet $10 (winner gets $20, loser nothing, in case of tie they start a new round). 

The strategy of each player is to randomly select 'rocks', 'paper' or 'scissors' independently (each round random). They will stop playing when one of the players runs out of money, or when they have played 25 games.

You may set the initial values of the variables like this:


```python
player1Funds=150
player2Funds=150
bet=10
maxRounds=25
```

Also, create a list of dictionaries to keep track of each game (use a list to record the details in a dictionary). How many games do they play? Print the details (dictionary) of the first 3 games. Details should include the round number, the beginning balance $ of each player, their 'hand' (rocks, paper or scissors), and who won that round.
