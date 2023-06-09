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
Age:
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

# Main
## Appearance
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Age, Species, Gender, AppearanceNotes AS "Notes", References
FROM #character WHERE Category = "Main"
SORT SortOrder
```

## Personality
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Role, Orientation, Personality, MainGoal AS "Goal", OtherNotes AS "Notes"
FROM #character WHERE Category = "Main"
SORT SortOrder
```

## Details
### [[Sam Ward]]


### [[Case Weston]]
- He shows up near the end of Act I, first as an antagonist and later as a love interest?
	- Maybe it's one-sided. However, Luke *does* have two hands...
- Nicholas D. Wolfwood. He's Nicholas D. Wolfwood. #Cite/TV/Trigun98 [tvRefType:: Trigun/Character]
	- He's not a wolf, though. That would be too obvious.
- Probably just a bit older than Luke, maybe 19

%%
question:: What species is Case?
%%

# Supporting
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Role, Age, Species, Gender, Personality, MainGoal AS "Goal", References
FROM #character WHERE Category = "Supporting"
```

## Details
### [[The Emperoress]]
- The one actually pulling all the strings
- The bigender/genderfluid master of CURSED AL
	- Many believe they're two separate people
- Possibly the same as [[The Dragon]]?

%%
question:: Is The Emperoress secretly Edna?
%%

### [[The Dragon]]
- You'd think this is the true main antagonist, but she's actually [[(12) December 2020 Chat Logs#^8a0296|super chill]]
- Tragically in love with Pauline, the horse #Cite/Movie/Shrek [movieRefType:: Shrek/Character]

### [[Luke's Noble Steed|Pauline]]
- Luke's noble steed
- A bay mare
- Just an ordinary horse

### [[Ma & Pa Campbell]]
- Luke's loving parents

# Other?
```dataview
TABLE WITHOUT ID link(file.link,Name) AS "Name", Role, Age, Species, Gender, Personality, MainGoal AS "Goal", References
FROM #character WHERE Category = "Side"
```
## Details
### [[Boring Straight Greg]]
- Diversity hire, not to be confused with the significantly cooler [[Bering Strait Grigori]]

### [[Bering Strait Grigori]]
- Helps James run the [[Plata]] Mine Museum
- He's a bear, in *both* senses of the word

### [[Steve the Royalty-Free Skeleton]]
- just a normal skeleton. nothing to see here. #Cite/Game/Undertale [gameRefType:: Undertale/Character]

#general #refdoc #unanswered-questions