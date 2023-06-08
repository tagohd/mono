---
alias: spells
---

The stronger the spell, the more [[Mana]] required, and thus larger tears in the veil separating reality from the [[Mana Plane]].

# Cantrips
These are spells that anyone can cast as they deal minimal damage to the veil between planes. Most people aren't even aware that they're magic.

```dataview
TABLE WITHOUT ID file.link AS "Name", spellDescription AS "Description", spellComponents AS "Components"
FROM "Concepts/Magic/Spells"
WHERE spellCategory = "Cantrip" AND !(isForbidden OR isTheoretical)
SORT spellName
```

# Minor Spells
Commonly taught to beginner mages, but slightly more powerful than cantrips.

```dataview
TABLE WITHOUT ID file.link AS "Name", spellDescription AS "Description", spellComponents AS "Components"
FROM "Concepts/Magic/Spells"
WHERE spellCategory = "Minor" AND !(isForbidden OR isTheoretical)
SORT spellName
```

# Intermediate Spells
Difficult to handle, but more powerful.

```dataview
TABLE WITHOUT ID file.link AS "Name", spellDescription AS "Description", spellComponents AS "Components"
FROM "Concepts/Magic/Spells"
WHERE spellCategory = "Intermediate" AND !(isForbidden OR isTheoretical)
SORT spellName
```

# Major Spells
Extremely dangerous. Only skilled mages should attempt to cast these spells.

```dataview
TABLE WITHOUT ID file.link AS "Name", spellDescription AS "Description", spellComponents AS "Components"
FROM "Concepts/Magic/Spells"
WHERE spellCategory = "Major" AND !(isForbidden OR isTheoretical)
SORT spellName
```

# Forbidden Spells
Spells [[Institute for the Magical Arts & Sciences|IMAS]] has forbidden for any number of reasons. May include spells of any level.

```dataview
TABLE WITHOUT ID file.link AS "Name", spellDescription AS "Description", spellCategory AS "Level"
FROM "Concepts/Magic/Spells"
WHERE isForbidden
SORT spellName
```

# Theoretical Spells
No one has ever attempted to cast these, but they may be possible under the right circumstances. Even so, IMAS may forbid its members from researching these spells.

```dataview
TABLE WITHOUT ID file.link AS "Name", spellDescription AS "Description", spellCategory AS "Level"
FROM "Concepts/Magic/Spells"
WHERE isForbidden
SORT spellName
```

# All Spells

```dataview
TABLE WITHOUT ID file.link AS "Name", spellCategory AS "LEVEL", spellDescription AS "Description", spellComponents AS "Components"
FROM "/Concepts/Magic/Spells"
```
