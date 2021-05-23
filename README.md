# Football-results-simulation
This project simulates the results of football leagues and cup. This version simulate the european Champions league. 

For the moment, I decided to make the whole project in one Html file that contains all CSS and JS codes, which make the file too much long and complicated (may be I change my mind later). I just wanted to be easy to execute.

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

## The class Match
This class represents a match between two teams.
The constructor takes the 4 variables.
- **team1** of type *Team*, represents the host team.
- **team2** of type *Team*, represents the visitor team.
- **HandW** of type *boolean*, when **true** then it is a two-legged home and away game (the home team gets more advantages in this case for playing at home), when **false** then it is one game match played in a third party playground, so the home team will not take any advantages for playing home.
- **extra** of type *boolean*, determines if extra-time will be applied in case of equality. Note that equanlity in case of two-legged games is computed in function of the results of the two matchs together.
	