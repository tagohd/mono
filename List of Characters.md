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
Height:
Weight:
Chest:
Waist:
Hips:
Inseam:
Orientation:
Personality:
MainGoal:
References:
AppearanceNotes:
OtherNotes:
SortOrder:
```

For the sake of birthdates, I'm just going to pretend the game takes place in 2020 (which is when I first had the idea for MONO; 'rona doesn't exist in this game, though). It might not actually take place then, but if everyone's born in 199X or whatever, it makes it kinda hard to distinguish who's older than whom. Also for the sake of convenience, age is calculated relative to Luke's 17th birthday.[^age] Again, the game doesn't necessarily begin on his birthday (but it doesn't NOT begin on his birthday), it's just a simplification.

[^age]: It used to be calculated from the current date, but I don't want them to keep aging because who knows how long this will take.

# All
```dataview
TABLE WITHOUT ID Category, link(file.link,Name) AS "Name", round((date(2020-10-22) - DOB).years, 1) AS "Age", Gender, Species, Role
FROM "Characters" WHERE Name
SORT SortOrder
```

## Statistics
### Metric
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Height AS "Height (cm)", Weight AS "Weight (kg)", Chest AS "Chest (cm)", Waist AS "Waist (cm)", Hips AS "Hips (cm)", Inseam AS "Inseam (cm)"
FROM "Characters" WHERE Name
SORT SortOrder
```

#### For Drawing
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Height AS "Height (cm)", Weight AS "Weight (kg)", Chest*0.375 AS "Chest (cm)", Waist*0.375 AS "Waist (cm)", Hips*0.375 AS "Hips (cm)", Inseam AS "Inseam (cm)"
FROM "Characters" WHERE Name
SORT SortOrder
```

### Customary
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", round(Height/2.54, 1) AS "Height (in)", round(Weight*2.205, 1) AS "Weight (lbs)", round(Chest/2.54, 1) AS "Chest (in)", round(Waist/2.54, 1) AS "Waist (in)", round(Hips/2.54, 1) AS "Hips (in)", round(Inseam/2.54, 1) AS "Inseam (in)"
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