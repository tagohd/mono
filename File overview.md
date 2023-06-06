# Changes
Delete the tags when you've read the changes and they'll disappear from the tables.

## Changes You Should Really Look At (Major Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Changes Made"
FROM #majorChange 
SORT file.mtime DESC
```

## Changes You Should Probably Look At (Minor Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Changes Made"
FROM #minorChange 
SORT file.mtime DESC
```

## Trivial Changes
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Changes Made"
FROM #trivialChange 
SORT file.mtime DESC
```

# All
```dataview
TABLE file.mday AS "Last changed", Lunsays, Sudosays
FROM -#minorChange and -#majorChange and -#trivialChange
WHERE file.mtime >= date(today) - dur(2 days)
SORT file.mtime DESC
```
