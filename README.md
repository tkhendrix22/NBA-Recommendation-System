# NBA-Recommendation-System

<img width="1402" alt="Screen Shot 2022-12-12 at 3 24 42 AM" src="https://user-images.githubusercontent.com/113871039/207134256-d608f645-8637-4394-903a-1698542607bc.png">

# Overview
This project analyzes existing data about various players in the nba currently as well as players who are retired and have played in the past. We use this data in order to develop a predictive model that can determine what features are most important when trying to understand what players are most similar to each other using advanced stats. This data gave us advanced stats on how each player impacted the floor beyond just the box score numbers. After utilizing the process of exploratory data analysis, I created several models to eventually reach the model with the highest and most appropriate score.

# Business Problem
It is well known that building a championship team in the NBA is probably the hardest amongst all the other well known sports in the country. When your team has a player that can takeover the entire game, it is the ultimate advantge on a nightly basis. However, what do you do when that player decides to leave your team? Scouts and front office executives have been dealing with this issue, especially in the modern age starting from when LeBron James made his big decision. It can be crucial to a team when a star player has decided to leave and you are stuck with the problem of trying to replace that player. This recommendation system is built to tell scouts which players are the most similar to each other stats wise to give scouts a better idea of who to target when a problem like this arises.  

# Data Understanding
The data that I used for this project comes from a dataset from FiveThirtyEight titled, 'The Best NBA Players, According To RAPTOR' and also a data set from Kaggle titled 'NBA season Stats'. This source is comprised of advanced stats that go beyond the box score and takes into effect the pace of the game, spacing, and the offensive and defensive nuances of the game. This gives stats of all players dating all the way back to 1977. Data was fairly clean so didn't have to do much to the data set. 

Column | Description
-------|---------------
`player_name` |	Player name
`player_id` |	Basketball-Reference.com player ID
`season` |	Season
`season_type` |	Regular season (RS) or playoff (PO)
`team` |	Basketball-Reference ID of team
`poss` |	Possessions played
`mp` |	Minutes played
`raptor_box_offense` |	Points above average per 100 possessions added by player on offense, based only on box score estimate
`raptor_box_defense` |	Points above average per 100 possessions added by player on defense, based only on box score estimate
`raptor_box_total` |	Points above average per 100 possessions added by player, based only on box score estimate
`raptor_onoff_offense` |	Points above average per 100 possessions added by player on offense, based only on plus-minus data
`raptor_onoff_defense` |	Points above average per 100 possessions added by player on defense, based only on plus-minus data
`raptor_onoff_total` |	Points above average per 100 possessions added by player, based only on plus-minus data
`raptor_offense` |	Points above average per 100 possessions added by player on offense, using both box and on-off components
`raptor_defense` |	Points above average per 100 possessions added by player on defense, using both box and on-off components
`raptor_total` |	Points above average per 100 possessions added by player on both offense and defense, using both box and on-off components
`war_total` |	Wins Above Replacement between regular season and playoffs
`war_reg_season` |	Wins Above Replacement for regular season
`war_playoffs` |	Wins Above Replacement for playoffs
`predator_offense` |	Predictive points above average per 100 possessions added by player on offense
`predator_defense` |	Predictive points above average per 100 possessions added by player on defense
`predator_total` |	Predictive points above average per 100 possessions added by player on both offense and defense
`pace_impact` |	Player impact on team possessions per 48 minutes

<img width="925" alt="Screen Shot 2022-12-12 at 2 35 23 PM" src="https://user-images.githubusercontent.com/113871039/207137833-bfd5b827-c556-4349-a212-f55b000e9030.png">
Can see that PPG are a lot more prevalent in the guard and forward positions rather than the center positions. This could be because the game has changed a lot from big men being the focal point to now an after thought on offense. 

<img width="964" alt="Screen Shot 2022-12-09 at 6 43 38 AM" src="https://user-images.githubusercontent.com/113871039/207138599-16805a95-34ea-4edf-bace-76d037490bf2.png">
Can see here that effective field goal percentage is shwon to increase once again in the forward positions. Any efg% over 50% is a great percentage. This could also be because wings are now the main important position on teams that include players who can score on all three levels - at the basket, 2P and 3P. Players like Giannis Antetokounmpo are the outliers here that make the graph spike in the forward positions because of how effective he can score at any position. 

# Modeling
## Best model
<img width="789" alt="Screen Shot 2022-12-12 at 3 27 40 PM" src="https://user-images.githubusercontent.com/113871039/207147636-620f86a0-8994-4f74-8ecc-2c16e8cafef0.png">

The Decision Tree model output the best results when determining which stats are most important for predicting that position which will tell front office executives and scouts what to focus on. 

# Recommendation System

The recommendation system that was built took the cosine similarity from one players stat vector and compared it to all the other current players stat vector and took the one with the highest similarity to show which player has the most similar stats. The system seems pretty accurate in which each player you type gives an output of someone who is very similar. The player that really surpised me was the comparison to Steph Curry. The output was a player named PJ Tucker who is not the same player when using the eye test. However, the stats show that they have similar shooting splits which is exactly what I wanted to show in case a player like Steph curry decides to leave, this gives the recommendation on how to focus on in case there is a need to replace that star player. 

# Observations/Conclusions

While my machine learning classification project proved that it can correctly predict the features that are most important in a players position, we have no information on how a players salary comes into play. In other words, players who get paid more usually play more.

Furthermore, an additional limitation to our project is that because salary was not taken into effect, we cant see if replacing a star player can save a team money in the long run. Being that the NBA has a salary cap, it makes it that much harder to build a team that can compete for a title. 

Another limitation of our project is that we do not know the team stats and coaching strategies. Some coaching strategies allow for players to sag off on defense because they're guarding a weaker player and things of that sort which may look like the player is bad of defense when hes really not. Just a few things to consider when taking stats into account is that they eye test is something that cannot be measured. 
