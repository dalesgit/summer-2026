[[assets/bishops-province8-mokuleia-full-moon.jpg]]

```dataview
TABLE dateformat(file.mtime, "dd.MM.yyyy HH:mm") AS "Last created"
FROM ""
SORT file.ctime DESC
LIMIT 25   
```

${query[[from p = index.tag "page" 
where p.created:startsWith("2026") 
order by p.created desc limit 5
select templates.pageItem(p)
]]}
