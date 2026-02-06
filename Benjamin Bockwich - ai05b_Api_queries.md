# API Query Building Assignment
---

## USGS Earthquake Queries

### Query 1: [Strongest recent earthquakes, magnitude 6.0+]
**URL:**
```
[https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson&minmagnitude=6.0&limit=5&orderby=magnitude]
```

**Parameters used:**
- `format`: [set to `geojson` for readable JSON output.]
- `minmagnitude`: [set to `6.0` to filter for only strong earthquakes.]
- `orderby`: [set to `magnitude` to sort the results from largest to smallest.]
- `limit`: [set to `5` to only show the top 5 results.]

**Result:** [A JSON object ("FeatureCollection") containing the 5 strongest earthquakes recently recorded worldwide, sorted by magnitude.]

---

### Query 2: [Earthquakes in Hawaii (Geographic Region)]
**URL:**
```
[https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson&minlatitude=18&maxlatitude=23&minlongitude=-160&maxlongitude=-154&limit=10]
```

**Parameters used:**
- `format`: [set to `geojson` for readable JSON output.]
- `minlatitude` / `maxlatitude`: [sets the north/south boundaries for the Hawaii region.]
- `minlongitude` / `maxlongitude`: [sets the east/west boundaries for the Hawaii region.]
- `limit`: [restricts the list to the 10 most recent events in this area.]

**Result:** [A JSON object containing the 10 most recent seismic events located specifically around the Hawaiian islands.]

---

### Query 3: [Large earthquakes from the year 2023 (Date Range)]
**URL:**
```
[https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson&starttime=2023-01-01&endtime=2023-12-31&minmagnitude=7.0]
```

**Parameters used:**
- `format`: [set to `geojson` for readable JSON output.]
- `starttime`: [sets the beginning of the search range to Jan 1,2023.]
- `endtime`: [sets the end of the search range to Dec 31, 2023.]
- `minmagnitude`: [filters for only major earthquakes (7.0 or higher).]

**Result:** [A JSON object listing the major earthquakes (7.0+) that occurred during the calendar year 2023. (Note: The `metadata.count` field in the JSON will tell you exactly how many happened).]

---

## Open Library Queries

### Query 4: [Search for "Frankenstein" by title]
**URL:**
```
[https://openlibrary.org/search.json?title=frankenstein&limit=3]
```

**Parameters used:**
- `title`: [searches specifically within book titles for "frankenstein".]
- `limit`: [restricts the results to just the top 3 matches to keep the data clean.]

**Result:** [A JSON object where `docs` contains details for the book "Frankenstein" (likely Mary Shelley's version first), including author names and publish years.]


### Query 5: [Books by Jane Austen (Specific Fields)]
**URL:**
```
[https://openlibrary.org/search.json?author=jane+austen&fields=title,first_publish_year&limit=5]
```

**Parameters used:**
- `author`: [filters results to show only books written by Jane Austen.]
- `fields`: [limits the JSON output to only show the `title` and `first_publish_year` (removes extra clutter).]
- `limit`: [shows only 5 results.]

**Result:** [A clean JSON list containing only the titles and publication years of 5 Jane Austen books.]

### Query 6: [Search for Python Programming books (Subject)]
**URL:**
```
[https://openlibrary.org/search.json?subject=python+programming&limit=5]
```

**Parameters used:**
- `subject`: [searches for books tagged with the subject "python programming".]
- `limit`: [restricts the output to 5 books.]

**Result:** [A JSON object listing 5 books related to Python coding, including their cover IDs, authors, and titles.]