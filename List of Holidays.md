# All Holidays
>[!note]
>By major, I mean holidays on which you would expect schools and businesses to be closed (or at least paying their employees overtime).

```dataview
TABLE date AS "Date", isMajor AS "Major?"
FROM "Holidays"
SORT date
```

#refdoc #Holiday #general 