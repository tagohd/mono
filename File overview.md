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

%%I would like for this to not be self-referential, but whatever. (Why can't this be more like LaTeX?)%%

# 2 Focus
Files that need urgent attention (this is mostly just for quick access)
```dataview
TABLE focusComment as "What Needs Work", Sudosays, Lunsays
WHERE focus
```

# 3 Changes
>[!tip]
>Delete the tags when you've read the changes and they'll disappear from the tables. Or maybe we could have the tags #unseenBySudo and #unseenByLun, and we delete our respective tags when we've seen the changes? (I am using an "and" in the queries, so you really only have to delete the "unseen" tag.)

>[!tip]
>Nothing saying you can't have multiple instances of the same tag in the same document. Maybe you made both major and minor changes to the same note?
>>[!note] We'd need new Dataview fields, though, or it will show all your comments in both tables.
>>How about sudoMajor, sudoMinor, lunMajor,  lunMinor, and trivial?

## 3.1 Changes Lun Should Really Look At (Major Changes)
>[!question] What's a major change?
>To me, it's more to do with how much I think you need to see it than how much actually changed. They're frequently *big* changes, or they involve questions I'd like you to answer. Or maybe there's just a new song :)
>
>To paraphrase Potter Stewart, "You'll know one when you see one."

>[!tip]
>You can add a "Priority" field to specify suggested read order. Note that not assigning a priority will cause those files to sort *ahead* of ones that do have a priority. (But if one file has a priority and the others don't, I'll probably figure it out.)

```dataview
TABLE file.mday as "Last Changed", sudoMajor as "Sudo's Changes", Priority, Sudosays, Lunsays
FROM #majorChange and #unseenByLun
SORT Priority, file.mtime DESC
```

## 3.2 Changes Lun Should Probably Look At (Minor Changes)
>[!question] What's a minor change?
>This is also subjective, but I think it does have more to do with "amount changed" than Major Changes do. Examples: Specified how old a character is, created a new (stub) note, added information to a note that was already present in another note. They're *kinda* important, but if it can be easily summarized here in the overview, it's probably a minor change.

```dataview
TABLE file.mday as "Last Changed", sudoMinor as "Sudo's Changes", Sudosays, Lunsays
FROM #minorChange and #unseenByLun 
SORT file.mtime DESC
```

## 3.3 Changes Sudo Should Really Look At (Major Changes)
```dataview
TABLE file.mday as "Last Changed", lunMajor as "Lun's Changes", Priority, Lunsays, Sudosays
FROM #majorChange and #unseenBySudo 
SORT Priority, file.mtime DESC
```

## 3.4 Changes Sudo Should Probably Look At (Minor Changes)
```dataview
TABLE file.mday as "Last Changed", lunMinor as "Lun's Changes", Lunsays, Sudosays
FROM #minorChange and #unseenBySudo 
SORT file.mtime DESC
```

## 3.5 Trivial Changes
>[!question] What's a trivial change?
>They're not unimportant, per se, but you don't need to open the note to see what changed. Fixing typos, changing links, adding new tags. Things of that sort.

```dataview
TABLE file.mday as "Last Changed", trivial as "Changes Made", Sudosays, Lunsays
FROM #trivialChange 
SORT file.mtime DESC
```

# 4 Files with Music
```dataview
TABLE songTitle as "Title", songRemarks as "Remarks"
FROM #contains-music 
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