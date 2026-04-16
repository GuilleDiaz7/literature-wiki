# Wiki Health Dashboard

> Live Dataview queries for tracking gaps in the wiki.
> Requires the [Dataview](https://github.com/blacksmithgu/obsidian-dataview) plugin.

---

## Works with no translator identified

Works where the translator is missing or could not be found in the source.

```dataview
TABLE author, translator, original_language
FROM "wiki/works"
WHERE type = "work" AND contains(translator, "not specified")
SORT author ASC
```

---

## Works with no publisher

```dataview
TABLE author, title
FROM "wiki/works"
WHERE type = "work" AND (publisher = "" OR !publisher)
SORT author ASC
```

---

## Works with no publisher URL

```dataview
TABLE author, publisher, title
FROM "wiki/works"
WHERE type = "work" AND (publisher_url = "" OR !publisher_url) AND publisher != ""
SORT publisher ASC
```

---

## Publishers by number of works

```dataview
TABLE length(rows) AS "Works in wiki"
FROM "wiki/works"
WHERE type = "work" AND publisher != ""
GROUP BY publisher
SORT length(rows) DESC
```

---

## Works with no human position

```dataview
TABLE author, title
FROM "wiki/works"
WHERE type = "work"
SORT last_updated DESC
```

> Note: "The Human's Position" section content cannot be queried by Dataview (it's body text, not frontmatter). Use this list as a checklist and fill positions manually.

---

## Works with only one source

```dataview
TABLE author, title, sources_count
FROM "wiki/works"
WHERE type = "work" AND sources_count = 1
SORT author ASC
```

---

## Recently updated works

```dataview
TABLE author, title, last_updated
FROM "wiki/works"
WHERE type = "work"
SORT last_updated DESC
LIMIT 10
```
