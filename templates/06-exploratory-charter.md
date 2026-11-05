# Exploratory Testing Charter

**Format:** *Explore* a target *with* resources *to discover* information.

> A charter gives a session a mission without scripting the steps. Timebox it (45 to 90 minutes), take notes as you go, and report what you tried, not only what you found.

## Charter: <short name>
**Explore** <the area, for example the checkout flow>
**with** <the resources: unusual input, a second browser profile, the Back button, developer tools>
**to discover** <the information wanted: missing validation, ways to reach protected pages, state that gets stuck>

| | |
|---|---|
| Tester | |
| Date and timebox | |
| Build / environment | |

## Session notes
| Idea tried | Result |
|---|---|
| <what you did> | <what happened: good, bad, odd> |

## Defects raised
- <BUG-nnn: title>

## Risks and questions raised
Things that worry you or need an answer from the product owner, even if nothing failed.

## Follow-up ideas not yet run
What you would try next.

---
### Idea prompts for web applications
- Inputs: empty, whitespace, very long, negative, decimals, emoji, script text, SQL text, right-to-left text.
- State: Back and Forward buttons, refresh in the middle of a flow, two tabs, logout in one tab, session expiry.
- Addresses: open an inner page directly, change an id in the URL, unknown address, add a query string.
- Rules: empty cart, duplicate submit, double click, order with the maximum quantity.
- Users: different roles, a user without permission, a locked or expired account.
- Devices: narrow screen, zoom 200%, keyboard only, high-contrast mode.
