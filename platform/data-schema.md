# Foozi Data Schema

This document defines the core data entities used across the Foozi platform.

These entities power the API, prediction models and frontend pages.

---

# Core Entities

The platform uses several core entities.

Competition  
Team  
Player  
Match  
Match Event  
Standing  
Statistic  

---

# Competition

Represents a football competition.

Example

Bundesliga  
Premier League  
Champions League  

Fields

id  
name  
country  
season  
logo  

Example

{
  "id": "bundesliga",
  "name": "Bundesliga",
  "country": "Germany",
  "season": "2025/26"
}

---

# Team

Represents a football club.

Fields

id  
name  
competition  
country  
stadium  
logo  

Example

{
  "id": "bayern",
  "name": "Bayern Munich",
  "competition": "bundesliga",
  "stadium": "Allianz Arena"
}

---

# Player

Represents an individual player.

Fields

id  
name  
team  
position  
nationality  
age  

Example

{
  "id": "jamal-musiala",
  "name": "Jamal Musiala",
  "team": "bayern",
  "position": "Midfielder"
}

---

# Match

Represents a scheduled or finished match.

Fields

id  
competition  
home_team  
away_team  
date  
stadium  
status  

Example

{
  "id": "bayern-vs-dortmund-2026",
  "competition": "bundesliga",
  "home_team": "bayern",
  "away_team": "dortmund",
  "date": "2026-03-20"
}

---

# Match Event

Represents events during a match.

Examples

goal  
assist  
yellow card  
substitution  

Fields

match_id  
minute  
event_type  
player  

Example

{
  "match_id": "bayern-vs-dortmund-2026",
  "minute": 37,
  "event_type": "goal",
  "player": "harry-kane"
}

---

# Standing

Represents league table data.

Fields

competition  
team  
position  
matches_played  
goal_difference  
points  

Example

{
  "competition": "bundesliga",
  "team": "bayern",
  "position": 1,
  "points": 58
}

---

# Statistic

Represents statistical metrics.

Examples

expected goals  
shots  
possession  

Fields

entity_type  
entity_id  
stat_name  
value
