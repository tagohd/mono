%%
sudoMajor:: Added new information to most characters. Added Dataview.
#majorChange #unseenByLun 
%%

# General Notes
- Every character is queer (except for [[All Characters#Boring Straight Greg|Boring Straight Greg]]) and some sort of furry

Hey, maybe I could use Dataview here, too. Use this metadata:

```
Name:
Category: Main | Supporting | Side
Role:
DOB:
Species:
Gender:
Orientation:
Personality:
MainGoal:
References:
AppearanceNotes:
OtherNotes:
SortOrder:
```

For the sake of birthdates, I'm just going to pretend the game takes place in 2023. It might not actually take place then, but if everyone's born in 199X or whatever, it makes it kinda hard to distinguish who's older than whom.

# Main
## Appearance
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", DOB, round((date(today) - DOB).years, 1) AS "Age", Species, Gender, AppearanceNotes AS "Notes", References
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
TABLE WITHOUT ID link(file.link,Name) AS "Name", DOB, round((date(today) - DOB).years, 1) AS "Age", Species, Gender, AppearanceNotes AS "Notes", References
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
TABLE WITHOUT ID link(file.link,Name) AS "Name", DOB, round((date(today) - DOB).years, 1) AS "Age", Species, Gender, AppearanceNotes AS "Notes", References
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