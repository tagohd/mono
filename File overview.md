---
number headings: auto, first-level 1, max 6, contents ^toc, 1.1
---

# 1 Contents ^toc

- [[#1 Contents ^toc|1 Contents]]
- [[#2 Focus|2 Focus]]
- [[#3 Changes|3 Changes]]
	- [[#3.1 Changes Lun Should Really Look At (Major Changes)|3.1 Changes Lun Should Really Look At (Major Changes)]]
	- [[#3.2 Changes Lun Should Probably Look At (Minor Changes)|3.2 Changes Lun Should Probably Look At (Minor Changes)]]
	- [[#3.3 Changes Sudo Should Really Look At (Major Changes)|3.3 Changes Sudo Should Really Look At (Major Changes)]]
	- [[#3.4 Changes Sudo Should Probably Look At (Minor Changes)|3.4 Changes Sudo Should Probably Look At (Minor Changes)]]
	- [[#3.5 Trivial Changes|3.5 Trivial Changes]]
- [[#4 Files with Music|4 Files with Music]]
- [[#5 Unanswered Questions|5 Unanswered Questions]]
- [[#6 Stubs|6 Stubs]]
- [[#7 All|7 All]]

I would like for this to not be self-referential, but whatever. (Why can't this be more like LaTeX?)

# 2 Focus
Files that need urgent attention
```dataview
TABLE focusComment as "What Needs Work"
WHERE focus
```

# 3 Changes
Delete the tags when you've read the changes and they'll disappear from the tables. Or maybe we could have the tags #unseenBySudo and #unseenByLun, and we delete our respective tags when we've seen the changes? (I am using an "and" in the queries, so you really only have to delete the "unseen" tag.)

[Sudo]: I'll leave it up to you to decide what kinds of changes count as major, minor, or trivial. To me, tagging something as a major change means I really want you to look at it/you should look at it first. Minor changes: I only added a couple sentences or explicitly referenced a detail that had previously only been hinted at. Trivial changes: usually just changes to the metadata, adding a link, or placing the note into a new folder. Something that causes the file to show that it was recently modified, but doesn't really affect anything.

## 3.1 Changes Lun Should Really Look At (Major Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Sudo's Changes"
FROM #majorChange and #unseenByLun
SORT file.mtime DESC
```

## 3.2 Changes Lun Should Probably Look At (Minor Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Sudo's Changes"
FROM #minorChange and #unseenByLun 
SORT file.mtime DESC
```

## 3.3 Changes Sudo Should Really Look At (Major Changes)
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Sudo's Changes", Lunsays as "Lun's Changes"
FROM #majorChange and #unseenBySudo 
SORT file.mtime DESC
```

## 3.4 Changes Sudo Should Probably Look At (Minor Changes)
```dataview
TABLE file.mday as "Last Changed", Lunsays as "Lun's Changes"
FROM #minorChange and #unseenBySudo 
SORT file.mtime DESC
```

## 3.5 Trivial Changes
```dataview
TABLE file.mday as "Last Changed", Sudosays as "Changes Made"
FROM #trivialChange 
SORT file.mtime DESC
```

# 4 Files with Music
```dataview
LIST from #contains-music 
```

# 5 Unanswered Questions
```dataview
TABLE question as "Question(s)"
FROM #unanswered-questions 
```

# 6 Stubs
```dataview
LIST FROM #stub 
```
# 7 All
```dataview
TABLE file.mday AS "Last changed", Lunsays, Sudosays
SORT file.mtime DESC
```