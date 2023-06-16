%%
Priority:: 2
sudoMajor:: Wanted to make sure you've seen that I've added species and other information for all characters.
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

For the sake of birthdates, I'm just going to pretend the game takes place in 2020 (which is when I first had the idea for MONO; 'rona doesn't exist in this game, though). It might not actually take place then, but if everyone's born in 199X or whatever, it makes it kinda hard to distinguish who's older than whom. Also for the sake of convenience, age is calculated relative to Luke's 17th birthday.[^age] Again, the game doesn't necessarily begin on his birthday (but it doesn't NOT begin on his birthday), it's just a simplification.

[^age]: It used to be calculated from the current date, but I don't want them to keep aging because who knows how long this will take.

# All
```dataview
TABLE WITHOUT ID Category, link(file.link,Name) AS "Name", round((date(2020-10-22) - DOB).years, 1) AS "Age", Gender, Species, Role
FROM #character 
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

```dataview
TABLE dateformat(DOB, "yyyy-MM-dd") AS "DOB" from #character SORT DOB
```

#general #refdoc 