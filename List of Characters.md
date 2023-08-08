# General Notes
- Every character is queer (except for [[List of Characters#Boring Straight Greg|Boring Straight Greg]]) and some sort of furry

Hey, maybe I could use Dataview here, too. Use this metadata:

```
Name:
Category: Main | Supporting | Side
Role:
DOB:
Species:
Gender:
Pronouns:
Measurements:
  Height:
  Weight:
  Chest:
  Waist:
  Hips:
  Inseam:
Orientation:
Personality:
MainGoal:
Ability:
  STR:
  DEX:
  CON:
  INT:
  WIS:
  CHA:
References:
AppearanceNotes:
OtherNotes:
SortOrder:
```

For the sake of birthdates, I'm just going to pretend the game takes place in 2020 (which is when I first had the idea for MONO; 'rona doesn't exist in this game, though). It might not actually take place then, but if everyone's born in 199X or whatever, it makes it kinda hard to distinguish who's older than whom. Ages given are the characters' ages at the beginning of the story (2020-09-18), Some characters may end up having birthdays as the story progresses.

# All
```dataview
TABLE WITHOUT ID Category, link(file.link,Name) AS "Name", DOB, round((date(2020-09-18) - DOB).years, 1) AS "Age", Gender, Species, Role
FROM "Characters" WHERE Name
SORT SortOrder
```

## Measurements
### Metric
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Measurements.Height AS "Height (cm)", Measurements.Weight AS "Weight (kg)", Measurements.Chest AS "Chest (cm)", Measurements.Waist AS "Waist (cm)", Measurements.Hips AS "Hips (cm)", Measurements.Inseam AS "Inseam (cm)"
FROM "Characters" WHERE Name
SORT SortOrder
```

#### For Drawing
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Measurements.Height AS "Height (cm)", Measurements.Weight AS "Weight (kg)", Measurements.Chest*0.375 AS "Chest (cm)", Measurements.Waist*0.375 AS "Waist (cm)", Measurements.Hips*0.375 AS "Hips (cm)", Measurements.Inseam AS "Inseam (cm)"
FROM "Characters" WHERE Name
SORT SortOrder
```

### Customary
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", round(Measurements.Height/2.54, 1) AS "Height (in)", round(Measurements.Weight*2.205, 1) AS "Weight (lbs)", round(Measurements.Chest/2.54, 1) AS "Chest (in)", round(Measurements.Waist/2.54, 1) AS "Waist (in)", round(Measurements.Hips/2.54, 1) AS "Hips (in)", round(Measurements.Inseam/2.54, 1) AS "Inseam (in)"
FROM "Characters" WHERE Name
SORT SortOrder
```

## Ability Scores
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Ability.STR AS "Strength", Ability.DEX AS "Dexterity", Ability.CON AS "Constitution", Ability.INT AS "Intelligence", Ability.WIS AS "Wisdom", Ability.CHA AS "Charisma"
FROM "Characters" WHERE Name
SORT SortOrder
```

# Main
## Appearance
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", DOB, round((date(2020-10-22) - DOB).years, 1) AS "Age", Species, Gender, AppearanceNotes AS "Notes", References
FROM #character WHERE Category = "Main"
SORT SortOrder
```

## Personality
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Role, Orientation, Personality, MainGoal AS "Goal", OtherNotes AS "Notes"
FROM #character WHERE Category = "Main"
SORT SortOrder
```

# Supporting
## Appearance
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", DOB, round((date(2020-10-22) - DOB).years, 1) AS "Age", Species, Gender, AppearanceNotes AS "Notes", References
FROM #character WHERE Category = "Supporting"
SORT SortOrder
```

## Personality
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Role, Orientation, Personality, MainGoal AS "Goal", OtherNotes AS "Notes"
FROM #character WHERE Category = "Supporting"
SORT SortOrder
```

# Other?
## Appearance
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", DOB, round((date(2020-10-22) - DOB).years, 1) AS "Age", Species, Gender, AppearanceNotes AS "Notes", References
FROM #character WHERE Category = "Side"
SORT SortOrder
```

## Personality
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Role, Orientation, Personality, MainGoal AS "Goal", OtherNotes AS "Notes"
FROM #character WHERE Category = "Side"
SORT SortOrder
```

#general #refdoc 