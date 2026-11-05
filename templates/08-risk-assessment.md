# Risk Assessment

Use it to decide **what to test first and how deeply**. Rate each risk, multiply, test the top of the list first.

## Scales
| Score | Impact (if it goes wrong) | Likelihood (that it goes wrong) |
|---|---|---|
| 1 | Cosmetic, nobody notices | Rare: stable, simple, well tested code |
| 2 | Annoying, workaround is easy | Unlikely |
| 3 | Feature broken, workaround exists | Possible: new or changed code |
| 4 | Core flow blocked, money or data wrong | Likely: complex, many integrations |
| 5 | Security breach, legal exposure, large financial loss | Almost certain: known fragile area, past defects |

**Rating = impact x likelihood.** 15 to 25 Critical, 8 to 14 High, 4 to 7 Medium, 1 to 3 Low.

## Register
| # | Risk | Impact | Likelihood | Score | Rating | Test focus | Owner |
|---|---|---|---|---|---|---|---|
| 1 | Customer cannot complete a purchase | 5 | 3 | 15 | Critical | Checkout cases, end-to-end | |
| 2 | Wrong price or total charged | 5 | 2 | 10 | High | Calculation cases, boundaries | |
| 3 | Unauthorised access to another user's data | 5 | 3 | 15 | Critical | Session, access control, URL tampering | |
| 4 | Layout breaks on small screens | 2 | 3 | 6 | Medium | Responsive checks | |

## Questions that surface risks
- What would make the news, or cost money, or break a law if it failed?
- What changed most recently, and what depends on it?
- Where were the last defects found?
- What do users do most often? What do attackers try first?
- What have we not been able to test (devices, data, third parties)? An untested area is a risk.
