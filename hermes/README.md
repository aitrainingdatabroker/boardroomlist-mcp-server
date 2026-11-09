# BoardroomList for Hermes

Adds the public, read-only [BoardroomList](https://boardroomlist.com) MCP server and one skill that tells the agent
how to use it. Ask which director, VP, SVP or C-suite roles are open at the 500 largest US companies, filtered by
function, work mode, city or state, minimum posted salary or how recently the role appeared. Each result comes with
a link to the role page on boardroomlist.com.

- **Server:** `https://boardroomlist.com/api/mcp` (Streamable HTTP, no key, no sign-in)
- **Disclosure:** every tool call goes to boardroomlist.com. The tools only read published role listings and write nothing. No local commands are run, and there is no telemetry beyond ordinary server logs. Nothing else is installed: configuration and a skill only. The tool list is served by the remote server at runtime and is not covered by the pinned commit.
- **Skill:** `skills/boardroomlist-senior-roles`

More links: [home](https://boardroomlist.com), [browse roles](https://boardroomlist.com/roles), [how it works](https://boardroomlist.com/how-it-works).
