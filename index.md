[[They Died, Unrecognized, for Britain]]
# Hello 👋

Welcome to the wondrous world of SilverBullet. A world that once you discover and appreciate, you’ll never want to leave.

You can go ahead and delete this placeholder content in a second, but before you do, let me quickly show you around.

cf. https://b.27p.de/qt/00002-silverbullet-query-examples/
https://silverbullet.md/Space%20Lua/Integrated%20Query

### Open Tasks

${template.each(
query[[
  from index.tag 'task' where not table.includes(itags, 'meta')
  and not done
]],
templates.taskItem
)}

### (done Tasks)

${template.each(
query[[
  from index.tag 'task' where not table.includes(itags, 'meta')
  and done
]],
templates.taskItem
)}

## recent queries
(_order by Created_)
${query[[from p = index.tag "page" 
where p.created:startsWith("2026") 
order by p.created desc limit 15 
select templates.pageItem(p)
]]}
(_ordr by Modified_)

- [[index-silverbullet]] index-silverbulletndex-silverthorn)
- [[Mary Pat]]

## Poetry

${query[[from p = index.tag "page" 
where p.created:startsWith("poetry") 
limit 5 order by desc
select templates.pageItem(p)
]]}

## forum

${query[[from p = index.tag "page" 
where p.name:startsWith("forum") 
limit 5 order by desc
select templates.pageItem(p)
]]}
  - [[entries/2026-05-03]]
## scripts
- [[script-for-word-count]]
- [[script-for-word-count-2]]
## projects
- [[Shai Held — On Love, and Judaism  The On Being Project]]
- [[michael_taylor-1]]
- 
```template
{{wordCount(readPage(@page.name))}}
```
also use “stats...” from menu

## task queries

Hint: Check dd-MM-yyyy - maybe its yyyy-MM-dd

### Overdue Tasks

${template.each(
query[[
  from index.tag 'task' where deadline < os.date('%yyyy-%MM-%dd')
  and not done
]],
templates.taskItem
)}

### Open Tasks

${template.each(
query[[
  from index.tag 'task' where not table.includes(itags, 'meta')
  and not done
]],
templates.taskItem
)}

### (done Tasks)

${template.each(
query[[
  from index.tag 'task' where not table.includes(itags, 'meta')
  and done
]],
templates.taskItem
)}

## Tasks Daily

${template.each(
query[[
  from index.tag 'task'
  where not done and table.includes(itags, "daily")
]], 
templates.taskItem
)}

## recent queries

- Most recent journal [[entries/2026-05-22]]
(_order by Created_)

${query[[from p = index.tag "page" 
where p.created:startsWith("2026") 
order by p.created desc limit 5 
select templates.pageItem(p)
]]}
(_ordr by Modified_)
- query created in May (descending order)

${query[[from p = index.tag("page") 
where p.created:startsWith("2026-06")
order by p.lastModified desc 
limit 5
select templates.pageItem(p)
]]}

${query[[from p = index.tag "page" 
where p.created:startsWith("2026-05")
order by p.lastModified desc
limit 5
select templates.pageItem(p)
]]}
