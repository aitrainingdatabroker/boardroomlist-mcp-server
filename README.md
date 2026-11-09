# BoardroomList MCP server

A public, read-only [Model Context Protocol](https://modelcontextprotocol.io) server for
[BoardroomList](https://boardroomlist.com), a job board for senior roles, Manager to CEO, at the 500 largest US
companies. Roles are sourced from the companies' own career sites and re-checked daily. The server lets an agent
search those roles by title words, seniority, function, work mode, place, pay and recency, and read one role.

- **Server URL:** `https://boardroomlist.com/api/mcp`
- **Transport:** Streamable HTTP, stateless
- **Authentication:** none
- **Access:** read-only. Nothing is written anywhere.

The data is what BoardroomList publishes on its site. Results are summaries; the company name, full description and
apply link are on the linked role page.

## Tools

| Tool | What it does |
|---|---|
| `search_roles` | Search open senior roles (Manager to C-suite) at the 500 largest US companies by words, seniority band, function, work mode, region, city or state, minimum salary and recency. Returns up to 25 roles a page with title, level, location, posted pay range, date and a link. Limitation: no company names; the role page shows them to members. |
| `get_role` | One role by id (the number at the end of its URL): title, level, function, location, work mode, posted pay, date, industry, a short redacted summary and scope, plus four similar open roles. Limitation: the company, full description and apply link are for members and are on the linked page. |
| `list_filters` | The job functions, seniority bands, industries, top cities and work modes you can filter `search_roles` by, each with its count of open roles. Returns no roles. |
| `search` | Connector-style search over open senior roles. Returns ids for `fetch`. Prefer `search_roles` when you can filter. |
| `fetch` | Connector-style fetch of one role by the id from `search`. Same fields as `get_role`. |

## Add it to your client

Add the server URL `https://boardroomlist.com/api/mcp` as a remote MCP server (Streamable HTTP, no key needed).

## Example questions

- Which VP finance roles are open in Texas?
- Show remote director of engineering roles posted in the last 14 days.
- How many open VP roles are there, and in which functions?
- Tell me more about role 419231.

## Links

- Home: https://boardroomlist.com
- Browse roles: https://boardroomlist.com/roles
- How it works: https://boardroomlist.com/how-it-works
- Contact: https://boardroomlist.com/contact
- Privacy: https://boardroomlist.com/privacy
- Terms: https://boardroomlist.com/terms

## Hermes plugin

The `hermes/` folder holds a Hermes plugin entry (`plugin.json`, `mcp.json`) and one skill,
`boardroomlist-senior-roles`, that tells an agent how to use these tools.
