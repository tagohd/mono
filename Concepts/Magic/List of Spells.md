---
alias: spells
---

%%
sudoMajor:: New document feat. lots of Dataview and some new spells (mostly stolen from D&D)
Sudosays:: I'm not going to include all the spells in the Changes.
Priority:: 5
#majorChange 
%%

The stronger the spell, the more [[Mana]] required, and thus larger tears in the veil separating reality from the [[Mana Plane]].

Except for [[Destroy Legendary Artifact]] and [[Reverse Fate]], all of these were copied directly from the Dungeons & Dragons Player's Handbook, 5th Edition. So, references to dice rolls, saving throws, etc. might not necessarily translate into MONO.

Only spells that are actually possible are listed in the tables below. Theoretical spells are listed in their own table.

# Cantrips
These are spells that anyone can cast as they deal minimal damage to the veil between planes. Maybe most people aren't even aware that they're magic.

```dataview
TABLE WITHOUT ID link(file.link,spellName) AS "Name", spellSchool AS "Category", spellDescription AS "Description", spellComponents AS "Components", isForbidden AS "Forbidden?"
FROM #Spells/Cantrips 
WHERE !isTheoretical
SORT spellName
```

# Minor Spells
Commonly taught to beginner mages, but slightly more powerful than cantrips.

```dataview
TABLE WITHOUT ID link(file.link,spellName) AS "Name", spellSchool AS "Category", spellDescription AS "Description", spellComponents AS "Components", isForbidden AS "Forbidden?"
FROM #Spells/Minor
WHERE !isTheoretical
SORT spellName
```

# Intermediate Spells
Difficult to handle, but more powerful.

```dataview
TABLE WITHOUT ID link(file.link,spellName) AS "Name", spellSchool AS "Category", spellDescription AS "Description", spellComponents AS "Components", isForbidden AS "Forbidden?"
FROM #Spells/Intermediate
WHERE !isTheoretical
SORT spellName
```

# Major Spells
Extremely dangerous. Only skilled mages should attempt to cast these spells.

```dataview
TABLE WITHOUT ID link(file.link,spellName) AS "Name", spellSchool AS "Category", spellDescription AS "Description", spellComponents AS "Components", isForbidden AS "Forbidden?"
FROM #Spells/Major 
WHERE !isTheoretical
SORT spellName
```

# Forbidden Spells
Spells [[Institute for the Magical Arts & Sciences|IMAS]] has forbidden for any number of reasons (usually obvious). May include spells of any level.

#lun 
lunR::6
%%
Maybe we can add a spell here that James and AL used to become immortal?
%%

```dataview
TABLE WITHOUT ID link(file.link,spellName) AS "Name", spellLevel AS "Level", spellSchool AS "Category", spellDescription AS "Description", isTheoretical AS "Theoretical?"
FROM #Spells 
WHERE isForbidden
SORT spellName
```

# Theoretical Spells
No one has ever attempted to cast these, but they may be possible under the right circumstances. Even so, IMAS may forbid its members from researching these spells.

```dataview
TABLE WITHOUT ID link(file.link,spellName) AS "Name", spellLevel AS "Level", spellSchool AS "Category", spellDescription AS "Description", isForbidden AS "Forbidden?"
FROM #Spells 
WHERE isTheoretical
SORT spellName
```

# All Spells

```dataview
TABLE WITHOUT ID link(file.link,spellName) AS "Name", spellClass as "Class", spellLevel AS "Level", spellSchool as "Category", spellDescription AS "Description", spellComponents AS "Components", isForbidden AS "Forbidden?", isTheoretical as "Theoretical?"
FROM #Spells AND -#refdoc
SORT isTheoretical, spellLevel, spellName
```

#refdoc #concepts #magic #Spells 