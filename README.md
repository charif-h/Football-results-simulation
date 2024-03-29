# Football-results-simulation
This project simulates the results of football leagues and cup. This version simulate the european Champions league. 

Th idea started by a trial to find a simple equation capable to give a realistic estimation of a football match result. Without machine learning or trained model, just a mathematical formula that uses the fifa ranking points of each team, to give an estimation of the number of goals each team might score against the other.

After succeeding a more or less realistic football match result, I extended th project to see how would it do for an entire Competition.
It was challenging because I had to use many ordering, and other mathematical stuff. Some problems that have been treated in this project:
- Divide a competition to multiple steps with different systems (knock out, league, ...).
- Distributing N teams in M groups:
  - In a random way.
  - with respect to teams ranking (dividing teams to multiple levels, were two teams from the same level should not be in the same group).
  - with respect to the results of a team in the precedent step of the competition.
- generating matchs of each couple of teams within a group, respecting that all teams of the group have to play a the same time, and that a team can't play two matchs at the same day.

# How to use it
For the moment, I decided to make the whole project in one Html file that contains all CSS and JS codes, which make the file too much long and complicated (may be I change my mind later). I just wanted to be easy to execute. So all you need is just to copy the html file and execute it in your borwser.


The simulator uses JS classes, such as:

## The class Team
The class team has the following fields:
- **id**: unique identifier of the team (number).
- **name**:  a short name of the team to display on the board during matchs.
- **fullName**: the full long name of the team.
- **credit**: is the most important feature that determines the power of the team, it is usually taken from the fifa ranking **I have to add a link here**.
- **shirt**: the color of the team's tee-shirt.
- **shrt**: *should have been short* is the color of the short of the team, but as short is a reserved term in JS, I removed the *'o'*.
- **groups**: is an array of values that help in grouping teams according to different criteria. In some leagues teams of the same group should or should not play against each other. This is different from the *pool* as we will see later, but *groups* is used for exemple to say that two clubs belong to the same country, or that two countries teams belong to the same continent.

An exemple of creating an object of the class *Team*:
```
new Team(1 ,"Bay" ,"FC Bayern München", 134.0, "red","red" ,["GER"])
```
In this exemple we add a new club team where the short name is *Bay*, the full name of the club is *FC Bayern München*, the credit of the club (its power) is *134.0*, the team wear *red* shirt and short, and it is in the group of *GER* (german teams).

### Methods of Team class

#### clearTempGroups
For some reasons we can attribute the team to termporary groups. This function allows to remove all termporary groups from the team.

#### ToDom
ToDom method allows to plot the team within an html element.

## The class poolTeam
Represents the team of a pool in a competition. It has the following features:
- **team**: of type *Team*.
- **wins**: number of won matchs by the team 
- **nulls**: number of null matchs of the team
- **defeats** : number of defeats of the team
- **goalsFor** : total of goals scored by the team in all his pool matchs
- **homeGoals** : number of goals scored at home (this is useful in some cases for ranking teams)
- **goalsAgainst**: number of goals scored against ths team 
- **rank**: the rank of the team within the pool.

## The class Match
This class represents a match between two teams.
The constructor takes the 4 variables.
- **team1** of type *Team*, represents the host team.
- **team2** of type *Team*, represents the visitor team.
- **HandW** of type *boolean*, when **true** then it is a two-legged home and away game (the home team gets more advantages in this case for playing at home), when **false** then it is one game match played in a third party playground, so the home team will not take any advantages for playing home.
- **extra** of type *boolean*, determines if extra-time will be applied in case of equality. Note that equanlity in case of two-legged games is computed in function of the results of the two matchs together.
- **host_moments** / **visitor_moments** : an array of moments of team's goals. For exemple the array [32, 75] means that the team would score two goals in this match at 32nd and 75th minutes.
- **endsAt**: usually 90, which means that the match takes 90 minutes, it would become 120 if much has extra time, and more if match arrives to penalities.
- **winner**: the nmae of the winner team, or null in case of draw. This is used because in some cases the team might win the current match but looses in the sum of both matchs.
- **hfinal_score** / **vfinal_score**:
- **minute**: the current minute of the match.
- **registered**:
- **matchId**: 

# Champions league simulation:

**つづく**
