# TOOLS.md

## Composio — External Service Integrations

I have access to **Composio** tools for connecting to the user's external services (Gmail, Slack, GitHub, etc.).

> ⚠️ **IMPORTANT: Composio is delivered via MCP, not as a native skill.**
> The tools are NOT in `openclaw skills list`.
> They ARE accessible via `openclaw mcp list` → look for `composio` or `supergateway`.
> **Always check MCP first** when any external service integration is requested.

### How to Discover and Use Composio Tools

**Step 1 — Verify MCP is available:**
```
openclaw mcp list
```
Look for `composio` in the output. If it appears, Composio tools are available.

**Step 2 — Find the right tool:**
Use `COMPOSIO_SEARCH_TOOLS` (available via the composio MCP) to find actions for a service.
Example: searching "gmail send" will show `GMAIL_SEND_EMAIL` and related tools.

**Step 3 — Handle first-time connection:**
If the service isn't connected yet, the tool call will fail with a "not connected" error. When this happens:
1. Call `COMPOSIO_MANAGE_CONNECTIONS` to generate an OAuth link for that service
2. Send the link to the user: _"To use Gmail, please connect your account first: [link]"_
3. Wait for the user to complete OAuth (they'll come back and say they're done, or just repeat their request)
4. Retry the original tool call

**Step 4 — Execute the task:**
Once connected, just call the tool normally. Composio handles all the auth token management.

### When to Use Composio

✅ **Use Composio when:**
- User asks me to do something with an external OAuth service (send email, create Jira ticket, post to Slack, etc.)
- The task requires authentication through the user's personal account
- The service is in the supported list below (or I can check via `COMPOSIO_SEARCH_TOOLS`)

❌ **Do NOT use Composio for:**
- Local file operations → use native file tools
- Web search → use `web_search`
- Code editing or terminal commands → use `exec`
- Anything I can do with my built-in tools
- Unknown services — check with `COMPOSIO_SEARCH_TOOLS` first before assuming it's available

### Supported Services (Known Good)

**Email:** Gmail, Outlook
**Calendar:** Google Calendar
**Chat & Communication:** Slack, Discord, Microsoft Teams, WhatsApp, Telegram
**Storage:** Google Drive
**Spreadsheets:** Google Sheets
**Dev Tools:** GitHub, GitLab, Jira, Linear, Bitbucket, Sentry
**Productivity:** Notion, Asana, Trello, ClickUp, Airtable
**CRM:** Salesforce, HubSpot, Pipedrive, Attio
**E-commerce:** Shopify

This is not exhaustive — Composio supports 1000+ apps. If a user asks about a service not listed, search for it with `COMPOSIO_SEARCH_TOOLS` before saying it's unsupported.

### Important Rules

- **Don't suggest Composio unprompted.** If user says "remind me to buy groceries" — that's a local reminder, not a Google Calendar event (unless they specifically ask to put it on their calendar).
- **One OAuth flow at a time.** Don't overwhelm the user with multiple "connect this" links. Handle one service per interaction.
- **Be specific about what's happening.** Don't say "I'll use my integrations" — say "I'll send that via your Gmail" or "I'll create a Jira ticket."
- **If a tool fails after connection**, check the error message. Common issues: permission scope too narrow, token expired (ask user to reconnect).
- **Never expose internal tool names** to the user. Say "send an email" not "call GMAIL_SEND_EMAIL".
