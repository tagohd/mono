---
tags: refdoc
---

There, now you can't say it's plagiarism. (I don't think it really works that way.)

%%
Sudosays:: Dataview!!! (I could use some help, though.)
Priority:: 7
#majorChange #unseenByLun 
%%

# Notes
I wish I could structure it in some way such that it only showed the refType for the relevant work and not just all refType fields in the note. And maybe there's some way I could make better use of nested tags? Copying and pasting the Dataview code over and over doesn't seem that efficient.

Also, I don't entirely remember where I was really going with this. I mean, seeing everything I've made a reference to is neat, I guess. Maybe not that useful? I think I wanted to include information about the works themselves on this page. Like what aspects inspired me the most, and my favorite songs if applicable.

Object-oriented approach failed. Example:
```
---
cite:
  workName: "Undertale"
  workType: "Game"
  citeType: "Plot"
cite:
  workName: "Better Call Saul"
  workType: "TV"
  citeType: "Character"
---
```
Query  ``TABLE cite.workName WHERE cite.workType = "Game"`` returns empty set. A separate named object for each citation would obviously be impractical. Another limitation to this approach is that objects can only be defined in the YAML frontmatter, i.e. I can't put the citations in-line.

**Q:** Can we filter the "refType" field somehow, or will it always return a list?

>[!info] Idea
>Instead of "refType", use "gameRefType", "movieRefType", etc.
>Query ``TABLE gameRefType FROM #Cite/Game``
>>[!question] How to sort alphabetically by all Game tags, especially since many files cite to multiple games
>>It *kinda* seems to default to that, actually?

# Games

```dataview
TABLE gameRefType as "Type of Reference"
FROM #Cite/Game 
```

## Chrono Trigger
```dataview
TABLE gameRefType as "Type of Reference"
FROM #Cite/Game/Chrono-Trigger 
```
\^ See, this is the problem I'm talking about. I want to be able to have it just be:

| File (1) | Type of Reference |
|---------|---------------------|
| [[CURSED AL]] | Plot |

But I should probably focus more on, idk, the actual plot? Instead of this.

## Earthbound
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Game/Earthbound 
```
## Hollow Knight
```dataview
TABLE gameRefType as "Type of Reference"
FROM #Cite/Game/Hollow-Knight 
```

## Katana Zero
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Game/Katana-Zero 
```

## Mega Man X
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Game/Mega-Man-X 
```
## Mother 3
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Game/Mother3 
```

## Pokémon
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Game/Pokémon 
```

## Undertale
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Game/Undertale 
```

## West of Loathing
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Game/West-of-Loathing 
```

# Literature

## The Lord of the Rings

```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Lit/LOTR 
```
# Movies

## Marvel Cinematic Universe
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Movie/MCU 
```

## Megamind
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Movie/Megamind 
```

## Shrek
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Movie/Shrek  
```

## Star Wars
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Movie/Star-Wars  
```

## There Will Be Blood
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/Movie/There-Will-Be-Blood  
```

# TV
## Better Call Saul
```dataview
TABLE refType as "Type of Reference"
FROM #Cite/TV/Better-Call-Saul 
```
