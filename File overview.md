# Changes
Delete the tags when you've read the changes and they'll disappear from the tables. Or maybe we could have the tags #unseenBySudo and #unseenByLun, and we delete our respective tags when we've seen the changes?

## Changes Lun Should Really Look At (Major Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Sudo's Changes"
FROM #majorChange and #unseenByLun 
SORT file.mtime DESC
```

## Changes Sudo Should Really Look At (Major Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Sudo's Changes", Lunsays as "Lun's Changes"
FROM #majorChange and #unseenBySudo 
SORT file.mtime DESC
```

## Changes Lun Should Probably Look At (Minor Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Sudo's Changes"
FROM #minorChange and #unseenByLun 
SORT file.mtime DESC
```

## Changes Sudo Should Probably Look At (Minor Changes)
```dataview
TABLE file.mday as "Last Changed", Lunsays as "Lun's Changes"
FROM #minorChange and #unseenBySudo 
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
