# BUG-013: Login can be bypassed by forging an unsigned session cookie

*A filled-in example of the [bug report template](../templates/04-bug-report.md). It is a real finding on a public practice shop; the full report with its evidence is in the [manual-testing-saucedemo](https://github.com/jahidulislamrihan26/manual-testing-saucedemo/blob/main/defects/BUG-013.md) repository.*

| Field | Value |
|---|---|
| Severity | Critical |
| Priority | High |
| Module | Security |
| Origin | Found in test |
| Status | Open |
| Found in | https://www.saucedemo.com, Chrome, 2026-11-05 |
| Test user / data | none (no password is needed, that is the defect) |
| Failed test cases | TC-065, TC-066 |

## Steps to reproduce
1. Open a fresh private window on https://www.saucedemo.com (not logged in).
2. In the browser tools add a cookie for `www.saucedemo.com`: name `session-username`, value `standard_user`, path `/`.
3. Open https://www.saucedemo.com/inventory.html.

## Expected result
Redirected to the login page. A session must be proven with a password and be an unguessable, signed value with `HttpOnly` and `Secure` set.

## Actual result
The shop opens as `standard_user` with no password. The same works for `problem_user` (and any other username); only `locked_out_user` is turned away. The cookie holds the plain username, `HttpOnly` is false, `Secure` is false, `SameSite` is Lax, lifetime about 10 minutes.

## Evidence
Screenshot of the products page shown to a browser that never logged in (`forged-cookie-access.png`).

## Impact
Anyone who knows or guesses a username can act as that user, and any script on the page can read the cookie. In a real shop this exposes orders and personal data.

## Why this is a good report
- The title says **what is wrong**, not where.
- The steps need no knowledge of the product and start from a clean state.
- Expected and actual are both written, with the exact cookie values.
- The impact is in plain words, which is what justifies Critical.
