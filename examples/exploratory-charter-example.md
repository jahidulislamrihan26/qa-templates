# Charter: How is a login proven?

*A filled-in example of the [exploratory charter template](../templates/06-exploratory-charter.md), from the [manual-testing-saucedemo](https://github.com/jahidulislamrihan26/manual-testing-saucedemo/blob/main/docs/03-exploratory-charters.md) repository.*

**Explore** the session, cookies and addresses
**with** browser developer tools and a second, clean browser profile
**to discover** whether an account can be reached without its password.

## Session notes
| Idea tried | Result |
|---|---|
| Inspect the cookie set after login | `session-username=standard_user`: plain username, not HttpOnly, not Secure, lives about 10 minutes |
| Copy that cookie into a fresh browser, open the products page | Shop opens with no password (**BUG-013**, Critical) |
| Same with another user's name | Works; only the locked-out user is turned away |
| HTTP address | Redirects (301) to HTTPS (good) |
| Response headers | No HSTS, CSP, X-Content-Type-Options, frame protection or Referrer-Policy (**BUG-018**) |
| Script text in a product address | Not executed (good) |

## Risks and questions raised
Any user could impersonate another by changing one cookie; if the server does not check, the same is true for orders and personal data in a real shop.

## Why this is a good charter
It names a **mission** (can an account be reached without its password?), not a list of clicks. The notes record what was tried including the things that were fine, so the reader knows what was covered.
