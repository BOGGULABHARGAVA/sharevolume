# Application


## Summary
Your assigned company: Caterpillar Inc. (CAT), CIK 0000018230.

Fetch https://data.sec.gov/api/xbrl/companyconcept/CIK0000018230/dei/EntityCommonStockSharesOutstanding.json (set a descriptive User-Agent per SEC guidance).
Read `.entityName`. Filter `.units.shares[]` for entries whose `fy` > "2020" and
includes a numeric `val`.
Save `data.json` with this structure:
`{"entityName": "Caterpillar Inc.", "max": {"val": ..., "fy": ...}, "min": {"val": ..., "fy": ...}}`
where `max` and `min` refer to the highest and lowest `.val`. Break ties however you like.

Render a visually appealing `index.html` where:
- `<title>` and `<h1>` must include the live `entityName`.
- The max/min figures are clearly marked with these IDs:
  `share-entity-name`,
  `share-max-value`, `share-max-fy`,
  `share-min-value`, `share-min-fy`.

If the page is opened as `index.html?CIK=0001018724` (or any other 10-digit CIK),
`fetch()` from the SEC endpoint for that CIK using any proxy, e.g. AIPipe,
replace every ID listed above and the title and H1 without reloading the page.

Also commit the attachment uid.txt as-is.


## Features
This application implements the following requirements:
- Each required file exists on GitHub\n- uid.txt matches the attached uid.txt\n- LICENSE contains the MIT License text\n- data.json exists and is valid JSON\n- data.json has 'entityName' field matching 'Caterpillar Inc.'\n- data.json has 'max' object with 'val' (number) and 'fy' (string) fields\n- data.json has 'min' object with 'val' (number) and 'fy' (string) fields\n- data.json max.fy and min.fy are both > '2020'\n- data.json max.val is greater than or equal to min.val\n- index.html exists\n- index.html <title> contains the entityName from data.json\n- index.html <h1 id='share-entity-name'> contains the entityName from data.json\n- index.html contains element with id='share-max-value' displaying max.val\n- index.html contains element with id='share-max-fy' displaying max.fy\n- index.html contains element with id='share-min-value' displaying min.val\n- index.html contains element with id='share-min-fy' displaying min.fy\n- index.html fetches data.json using fetch('https://data.sec.gov/api/xbrl/companyconcept/CIK0000018230/dei/EntityCommonStockSharesOutstanding.json')\n- index.html supports ?CIK= query parameter to fetch alternate company data\n- index.html dynamically updates all elements when ?CIK= is provided\n


## Usage
1. Open the GitHub Pages URL in your browser
2. The application will automatically load and display the required functionality
3. For parameterized features, use query parameters (e.g., `?url=...`, `?token=...`)


## Setup
This is a static HTML application hosted on GitHub Pages. No build process required.


To run locally:
