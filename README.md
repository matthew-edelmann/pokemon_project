# pokemon_project

## Problem: With the new Pokemon games that came out in November 2022, I want to find out which new pokemon would do the best competitively

### Introduction:

So my intention in this project was to find the best pokemon in the new games. To do this we need to scrape the entire Pokedex. We need the entire stats of the every pokemon as well as there element types and move set. We will use this to analyze and predict which new pokemon will do well competitively.

### Gathering Data:

To gather the data I needed the stats, types, and moveset of every pokemon as well as which pokemon have won a tournament. To collect the data I used beautifulsoup4 and webscrapped from https://pokemondb.net/pokedex/stats/combo. This website has all the pokemon and their stat totals.

### Cleaning data:

The cleaning process wasn't complicated as all it involved was putting the stats in the correct format. 

### Making a logistic regression model:

So the first model I created was a logistic regression model. I used a logistic regression model because it is good to give a probability to a binary question. In this case, the binary is 0 if a pokemon had never won a tournament and a 1 if they have won.

Running the model I incorporated the stat values as well as dummy variables for each pokemon type combonation. I created polynomial features and created the model using a train test split on all the pokemon before generation 9. The model accounted for 93% of the variation in the data and was neither overfit nor underfit. 

The model found the following. The top 5 contenders are Chien-Pao, Great Tusk, Cetitan, Roaring Moon, and Wugtrio. 2 of these are legendary pokemon (Chien-Pao and Roaring Moon) and 2 seem shockingly similar to older pokemon (Great Tusk with Donphan and Wugtrio with Dugtrio). All of these have a 99% chance of eventually winning a tournament.

The 5 worst pokemon of the new generation, based on the model, are Scovillian, Greavard, Rellor, Charcadet, and Tarountula. 4 of these 5 pokemon are the first stage of an evolutionary line. This is in line of what we can expect.

### Making a NLP model using the moveset of the pokemon:

Here I took the moveset of each pokemon and ran it through an NLP model to see if it could pick up which pokemon would do well based on the moves. First off, I found the moves that were most commonly found in champion pokemon. Here is what I found:

![image](https://user-images.githubusercontent.com/67232494/211168682-fcaec778-4b06-402a-9591-363328cf46cc.png)

Now that I had that I tried to make a model with it. Unfortunatly, the models could not accurately predict which pokemon would do well based on their moveset.

### Conclusion:

While I couldn't make a meaningful model based on the pokemon moves, I can based on the pokemons stats and types. We see that base stat total is the most important stat for determining a successful pokemon and that many of the new pokemon have a 99% chance of eventually winning an official tournament with Chien-Pao being considered the best pokemon of the new generation

