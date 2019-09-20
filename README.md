
# Using Nested Loops - Lab

## Introduction
In this lab, you'll practice using nested loops to iterate over nested data structures and create new collections. To do this, you'll be using data from a soccer match to practice our nested loops.

## Objectives
You will be able to:
* Use nested loops to iterate through nested data structures

## Instructions

Use nested loops and the below object, `soccer_match`, to complete the following prompts and get the desired return values.

Each object's structure is identical, but make sure to have a good idea of what that structure looks like before getting started. 


```python
soccer_match = [
  { "home_team": True,
    "away_team": False,
    "country": "France",
    "num_passes": 484,
    "passes_completed": 423,
    "fouls_committed": 16,
    "colors": ["blue", "white", "red"],
    "players": [
      {
        "name": "Hugo LLORIS",
        "captain": True,
        "shirt_number": 1,
        "position": "Goalie"
      },
      {
        "name": "Benjamin PAVARD",
        "captain": False,
        "shirt_number": 2,
        "position": "Defender"
      },
      {
        "name": "Raphael VARANE",
        "captain": False,
        "shirt_number": 4,
        "position": "Defender"
      },
      {
        "name": "Samuel UMTITI",
        "captain": False,
        "shirt_number": 5,
        "position": "Defender"
      },
      {
        "name": "Paul POGBA",
        "captain": False,
        "shirt_number": 6,
        "position": "Midfield"
      },
      {
        "name": "Antoine GRIEZMANN",
        "captain": False,
        "shirt_number": 7,
        "position": "Forward"
      },
      {
        "name": "Kylian MBAPPE",
        "captain": False,
        "shirt_number": 10,
        "position": "Forward"
      },
      {
        "name": "Ousmane DEMBELE",
        "captain": False,
        "shirt_number": 11,
        "position": "Forward"
      },
      {
        "name": "Corentin TOLISSO",
        "captain": False,
        "shirt_number": 12,
        "position": "Midfield"
      },
      {
        "name": "Ngolo KANTE",
        "captain": False,
        "shirt_number": 13,
        "position": "Midfield"
      },
      {
        "name": "Lucas HERNANDEZ",
        "captain": False,
        "shirt_number": 21,
        "position": "Defender"
      }
    ],
  },
  { "home_team": False,
    "away_team": True,
    "country": "Australia",
    "num_passes": 390,
    "passes_completed": 332,
    "fouls_committed": 19,
    "colors": ["green", "gold"],
    "players": [
      {
        "name": "Mathew RYAN",
        "captain": False,
        "shirt_number": 1,
        "position": "Goalie"
      },
      {
        "name": "Mark MILLIGAN",
        "captain": False,
        "shirt_number": 5,
        "position": "Defender"
      },
      {
        "name": "Mathew LECKIE",
        "captain": False,
        "shirt_number": 7,
        "position": "Forward"
      },
      {
        "name": "Robbie KRUSE",
        "captain": False,
        "shirt_number": 10,
        "position": "Forward"
      },
      {
        "name": "Andrew NABBOUT",
        "captain": False,
        "shirt_number": 11,
        "position": "Forward"
      },
      {
        "name": "Aaron MOOY",
        "captain": False,
        "shirt_number": 13,
        "position": "Midfield"
      },
      {
        "name": "Mile JEDINAK",
        "captain": True,
        "shirt_number": 15,
        "position": "Midfield"
      },
      {
        "name": "Aziz BEHICH",
        "captain": False,
        "shirt_number": 16,
        "position": "Defender"
      },
      {
        "name": "Joshua RISDON",
        "captain": False,
        "shirt_number": 19,
        "position": "Defender"
      },
      {
        "name": "Trent SAINSBURY",
        "captain": False,
        "shirt_number": 20,
        "position": "Defender"
      },
      {
        "name": "Tom ROGIC",
        "captain": False,
        "shirt_number": 23,
        "position": "Midfield"
      }
    ]
  }
]
```


```python
# __SOLUTION__ 
soccer_match = [
  { "home_team": True,
    "away_team": False,
    "country": "France",
    "num_passes": 484,
    "passes_completed": 423,
    "fouls_committed": 16,
    "colors": ["blue", "white", "red"],
    "players": [
      {
        "name": "Hugo LLORIS",
        "captain": True,
        "shirt_number": 1,
        "position": "Goalie"
      },
      {
        "name": "Benjamin PAVARD",
        "captain": False,
        "shirt_number": 2,
        "position": "Defender"
      },
      {
        "name": "Raphael VARANE",
        "captain": False,
        "shirt_number": 4,
        "position": "Defender"
      },
      {
        "name": "Samuel UMTITI",
        "captain": False,
        "shirt_number": 5,
        "position": "Defender"
      },
      {
        "name": "Paul POGBA",
        "captain": False,
        "shirt_number": 6,
        "position": "Midfield"
      },
      {
        "name": "Antoine GRIEZMANN",
        "captain": False,
        "shirt_number": 7,
        "position": "Forward"
      },
      {
        "name": "Kylian MBAPPE",
        "captain": False,
        "shirt_number": 10,
        "position": "Forward"
      },
      {
        "name": "Ousmane DEMBELE",
        "captain": False,
        "shirt_number": 11,
        "position": "Forward"
      },
      {
        "name": "Corentin TOLISSO",
        "captain": False,
        "shirt_number": 12,
        "position": "Midfield"
      },
      {
        "name": "Ngolo KANTE",
        "captain": False,
        "shirt_number": 13,
        "position": "Midfield"
      },
      {
        "name": "Lucas HERNANDEZ",
        "captain": False,
        "shirt_number": 21,
        "position": "Defender"
      }
    ],
  },
  { "home_team": False,
    "away_team": True,
    "country": "Australia",
    "num_passes": 390,
    "passes_completed": 332,
    "fouls_committed": 19,
    "colors": ["green", "gold"],
    "players": [
      {
        "name": "Mathew RYAN",
        "captain": False,
        "shirt_number": 1,
        "position": "Goalie"
      },
      {
        "name": "Mark MILLIGAN",
        "captain": False,
        "shirt_number": 5,
        "position": "Defender"
      },
      {
        "name": "Mathew LECKIE",
        "captain": False,
        "shirt_number": 7,
        "position": "Forward"
      },
      {
        "name": "Robbie KRUSE",
        "captain": False,
        "shirt_number": 10,
        "position": "Forward"
      },
      {
        "name": "Andrew NABBOUT",
        "captain": False,
        "shirt_number": 11,
        "position": "Forward"
      },
      {
        "name": "Aaron MOOY",
        "captain": False,
        "shirt_number": 13,
        "position": "Midfield"
      },
      {
        "name": "Mile JEDINAK",
        "captain": True,
        "shirt_number": 15,
        "position": "Midfield"
      },
      {
        "name": "Aziz BEHICH",
        "captain": False,
        "shirt_number": 16,
        "position": "Defender"
      },
      {
        "name": "Joshua RISDON",
        "captain": False,
        "shirt_number": 19,
        "position": "Defender"
      },
      {
        "name": "Trent SAINSBURY",
        "captain": False,
        "shirt_number": 20,
        "position": "Defender"
      },
      {
        "name": "Tom ROGIC",
        "captain": False,
        "shirt_number": 23,
        "position": "Midfield"
      }
    ]
  }
]
```

## Countries: A list of strings

In the cell below, iterate over the `soccer_match` list to create a new list with the name of the country for each team. 


```python
# iterate over the soccer_match list to create a new list with the name of the country for each team
countries = []
# code goes here
```


```python
# __SOLUTION__ 
# iterate over the soccer_match list to create a new list with the name of the country for each team
countries = []
# code goes here
for team in soccer_match:
    countries.append(team['country'])
countries
```




    ['France', 'Australia']



## Colors: Another list of strings!

In the cell below, iterate over the `soccer_match` list to create a new list with the colors for each team this should be only one list containing strings for each of the country's colors.


```python
# iterate over the soccer_match list to create a new list with the colors for each team
# this should be only one list containing strings for each of the country's colors
colors = []
# code goes here
```


```python
# __SOLUTION__ 
colors = []
# code goes here
for team in soccer_match:
    for color in team['colors']:
        colors.append(color)
colors
```




    ['blue', 'white', 'red', 'green', 'gold']



## Players: A list of dictionaries

This time, iterate over the `soccer_match` list to create a new list with the players from each team. `players` should be a single list containing the dictionaries for each of the country's players.


```python
players = []
# code goes here
```


```python
# __SOLUTION__ 
players = []
# code goes here
for team in soccer_match:
    for player in team['players']:
        players.append(player)
players
```




    [{'name': 'Hugo LLORIS',
      'captain': True,
      'shirt_number': 1,
      'position': 'Goalie'},
     {'name': 'Benjamin PAVARD',
      'captain': False,
      'shirt_number': 2,
      'position': 'Defender'},
     {'name': 'Raphael VARANE',
      'captain': False,
      'shirt_number': 4,
      'position': 'Defender'},
     {'name': 'Samuel UMTITI',
      'captain': False,
      'shirt_number': 5,
      'position': 'Defender'},
     {'name': 'Paul POGBA',
      'captain': False,
      'shirt_number': 6,
      'position': 'Midfield'},
     {'name': 'Antoine GRIEZMANN',
      'captain': False,
      'shirt_number': 7,
      'position': 'Forward'},
     {'name': 'Kylian MBAPPE',
      'captain': False,
      'shirt_number': 10,
      'position': 'Forward'},
     {'name': 'Ousmane DEMBELE',
      'captain': False,
      'shirt_number': 11,
      'position': 'Forward'},
     {'name': 'Corentin TOLISSO',
      'captain': False,
      'shirt_number': 12,
      'position': 'Midfield'},
     {'name': 'Ngolo KANTE',
      'captain': False,
      'shirt_number': 13,
      'position': 'Midfield'},
     {'name': 'Lucas HERNANDEZ',
      'captain': False,
      'shirt_number': 21,
      'position': 'Defender'},
     {'name': 'Mathew RYAN',
      'captain': False,
      'shirt_number': 1,
      'position': 'Goalie'},
     {'name': 'Mark MILLIGAN',
      'captain': False,
      'shirt_number': 5,
      'position': 'Defender'},
     {'name': 'Mathew LECKIE',
      'captain': False,
      'shirt_number': 7,
      'position': 'Forward'},
     {'name': 'Robbie KRUSE',
      'captain': False,
      'shirt_number': 10,
      'position': 'Forward'},
     {'name': 'Andrew NABBOUT',
      'captain': False,
      'shirt_number': 11,
      'position': 'Forward'},
     {'name': 'Aaron MOOY',
      'captain': False,
      'shirt_number': 13,
      'position': 'Midfield'},
     {'name': 'Mile JEDINAK',
      'captain': True,
      'shirt_number': 15,
      'position': 'Midfield'},
     {'name': 'Aziz BEHICH',
      'captain': False,
      'shirt_number': 16,
      'position': 'Defender'},
     {'name': 'Joshua RISDON',
      'captain': False,
      'shirt_number': 19,
      'position': 'Defender'},
     {'name': 'Trent SAINSBURY',
      'captain': False,
      'shirt_number': 20,
      'position': 'Defender'},
     {'name': 'Tom ROGIC',
      'captain': False,
      'shirt_number': 23,
      'position': 'Midfield'}]



## Captains: Another list of dictionaries!

Iterate over the `soccer_match` list to create a new list with the captains from each team.
This should be a single list containing the dictionaries for each of the country's captains.


```python
captains = None
# code goes here
```


```python
# __SOLUTION__ 
captains = []
# code goes here
for team in soccer_match:
    for player in team['players']:
        if player['captain']:
            captains.append(player)
captains
```




    [{'name': 'Hugo LLORIS',
      'captain': True,
      'shirt_number': 1,
      'position': 'Goalie'},
     {'name': 'Mile JEDINAK',
      'captain': True,
      'shirt_number': 15,
      'position': 'Midfield'}]



## Home Team Players: A third list of dictionaries

Iterate over the `soccer_match` list to create a new list with the players from ONLY the home team.


```python
home_team_players = []
# code goes here
```


```python
# __SOLUTION__ 
home_team_players = []
# code goes here
for team in soccer_match:
    if team['home_team']:
        for player in team['players']:
            home_team_players.append(player)
home_team_players
```




    [{'name': 'Hugo LLORIS',
      'captain': True,
      'shirt_number': 1,
      'position': 'Goalie'},
     {'name': 'Benjamin PAVARD',
      'captain': False,
      'shirt_number': 2,
      'position': 'Defender'},
     {'name': 'Raphael VARANE',
      'captain': False,
      'shirt_number': 4,
      'position': 'Defender'},
     {'name': 'Samuel UMTITI',
      'captain': False,
      'shirt_number': 5,
      'position': 'Defender'},
     {'name': 'Paul POGBA',
      'captain': False,
      'shirt_number': 6,
      'position': 'Midfield'},
     {'name': 'Antoine GRIEZMANN',
      'captain': False,
      'shirt_number': 7,
      'position': 'Forward'},
     {'name': 'Kylian MBAPPE',
      'captain': False,
      'shirt_number': 10,
      'position': 'Forward'},
     {'name': 'Ousmane DEMBELE',
      'captain': False,
      'shirt_number': 11,
      'position': 'Forward'},
     {'name': 'Corentin TOLISSO',
      'captain': False,
      'shirt_number': 12,
      'position': 'Midfield'},
     {'name': 'Ngolo KANTE',
      'captain': False,
      'shirt_number': 13,
      'position': 'Midfield'},
     {'name': 'Lucas HERNANDEZ',
      'captain': False,
      'shirt_number': 21,
      'position': 'Defender'}]



## Away Team Forwards: Yup, a list of dictionaries

Iterate over the `soccer_match` list to create a new list with the information for each of the away team players whose `position` is `"Forward"`.


```python
away_team_forwards = []
# code goes here
```


```python
# __SOLUTION__ 
away_team_forwards = []
# code goes here
for team in soccer_match:
    if team['away_team']:
        for player in team['players']:
            if player['position'] == 'Forward':
                away_team_forwards.append(player)
away_team_forwards
```




    [{'name': 'Mathew LECKIE',
      'captain': False,
      'shirt_number': 7,
      'position': 'Forward'},
     {'name': 'Robbie KRUSE',
      'captain': False,
      'shirt_number': 10,
      'position': 'Forward'},
     {'name': 'Andrew NABBOUT',
      'captain': False,
      'shirt_number': 11,
      'position': 'Forward'}]



## Player with the Highest Number

Iterate over the `soccer_match` list and find the player with the highest `shirt_number`.  
Store this player's information in the `player_with_highest_num` variable.


```python
player_with_highest_num = None
# code goes here
```


```python
# __SOLUTION__ 
player_with_highest_num = None
# code goes here
for team in soccer_match:
    for player in team['players']:
        if not player_with_highest_num or player_with_highest_num['shirt_number'] < player['shirt_number']:
            player_with_highest_num = player
player_with_highest_num
```




    {'name': 'Tom ROGIC',
     'captain': False,
     'shirt_number': 23,
     'position': 'Midfield'}



## Player Names: A Cleaned List

Notice that the players oddly have have their last name's in all caps. Create a list of all the names of the players in this match. Be sure to make sure their first and last names are properly capitalized (first letter upper case, proceeding letters lower case), as opposed to how they are currently formatted.


```python
player_names = []
# code goes here
```


```python
# __SOLUTION__ 
player_names = []
# code goes here
for team in soccer_match:
    for player in team['players']:
        player_names.append(player['name'].title())
player_names
```




    ['Hugo Lloris',
     'Benjamin Pavard',
     'Raphael Varane',
     'Samuel Umtiti',
     'Paul Pogba',
     'Antoine Griezmann',
     'Kylian Mbappe',
     'Ousmane Dembele',
     'Corentin Tolisso',
     'Ngolo Kante',
     'Lucas Hernandez',
     'Mathew Ryan',
     'Mark Milligan',
     'Mathew Leckie',
     'Robbie Kruse',
     'Andrew Nabbout',
     'Aaron Mooy',
     'Mile Jedinak',
     'Aziz Behich',
     'Joshua Risdon',
     'Trent Sainsbury',
     'Tom Rogic']



## Summary

In this lab, you practiced using nested loops to iterate through a nested data structure using data from a soccer match. Nested data structures can be quite complicated and it can become difficult to access more nested data. With nested loops, you are able to dynamically access this nested data and work with it as you would with a flatter data structure. It is important to think about the structure of the data before and while you're working so you know exactly what data you are working with at each level.
