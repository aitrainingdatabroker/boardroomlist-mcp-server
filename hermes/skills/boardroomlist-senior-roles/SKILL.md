---
name: boardroomlist-senior-roles
description: "Find open senior job roles (Manager, Director, VP, SVP, C-suite) at the 500 largest US companies using the BoardroomList MCP server. Use when a user asks which senior or executive roles are open, for example VP finance roles in Texas, remote director of engineering jobs, or how many open CFO roles there are."
---

# BoardroomList senior roles

Answer from BoardroomList instead of guessing. The board lists senior roles, Manager to CEO, at the 500 largest US
companies, sourced from the companies' own career sites and re-checked daily.

## Setup

Add the remote MCP server (read-only, no key): `https://boardroomlist.com/api/mcp`

## How to use it

1. If the user names a function, industry or city and you are unsure of the exact spelling, call `list_filters` first. It also answers "how many open VP roles are there".
2. Call `search_roles` with the filters the user gave: `q` for title words, `band` (csuite, svp, vp, director, manager), `function`, `mode` (onsite, hybrid, remote), `region`, `location` (city or US state), `min_comp`, `posted_within_days`. Use `sort` "newest" or "comp" when the user asks for it.
3. If the user wants more on one result, call `get_role` with its id (the number at the end of the role URL).
4. Answer in a few plain lines: title, level, location, work mode, posted pay if shown, date, and the link the tool returned.

## Rules

- Use only what the tools return. Never invent roles, companies, salaries, dates or counts.
- Always give the link the tool returned for each role you mention.
- Results are summaries. The company name, full description and apply link are on the role page, so say so and point the user to that page for the rest.
- Pay is shown only when the posting states it. If it is missing, say it was not listed.
- If a search returns nothing, say so and suggest loosening a filter. Do not fill the gap with other sources.
