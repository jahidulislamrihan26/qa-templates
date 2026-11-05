# Test Case Template

One test case = one thing to check, with steps anyone can follow and a result that can be judged without arguing.

## Fields
| Field | What to write |
|---|---|
| **ID** | Stable, never reused (`TC-001`). Automated tests refer to it. |
| **Requirement** | The requirement it proves (`REQ-01`), so coverage can be shown. |
| **Module** | Area of the product (Login, Cart, Checkout). |
| **Title** | A sentence saying what must be true: "Login is rejected with the wrong password". |
| **Type** | Functional, Negative, Boundary, Security, Usability, Accessibility, Compatibility, Performance. |
| **Priority** | Critical, High, Medium, Low (impact if this fails). |
| **Preconditions** | State needed before step 1 (logged in, cart has one item). |
| **Test data** | Exact values, not "a valid name". |
| **Steps** | Numbered, one action each. |
| **Expected result** | Observable and specific: the message text, the number, the page. |
| **Actual result** | What really happened (filled at execution, with evidence). |
| **Status** | Pass, Fail, Blocked, Not Run. Never leave a result assumed. |
| **Defect** | The defect id when Status is Fail. |
| **Evidence** | Screenshot, video or log name. |

## Worked example
| Field | Value |
|---|---|
| ID | TC-042 |
| Requirement | REQ-06 Checkout information |
| Module | Checkout |
| Title | A postal code with letters and symbols is rejected |
| Type | Boundary |
| Priority | Medium |
| Preconditions | Logged in; one product in the cart; on the checkout information page |
| Test data | First name `Test`, last name `User`, postal code `abc!@#` |
| Steps | 1. Enter the test data. 2. Click Continue. |
| Expected result | A validation error is shown and the order does not continue |
| Actual result | The page moved on to the overview |
| Status | Fail |
| Defect | BUG-002 |
| Evidence | `checkout-invalid-zip-accepted.png` |

## Good habits
- **Test one thing per case.** If a case can fail for two different reasons, split it.
- **Write the expected result before you run it**, never after seeing the result.
- **Cover the unhappy paths:** empty, too long, whitespace, wrong type, wrong permission, double click, Back button.
- **Record what you did not test** as Not Run with the reason. Do not mark it Pass.
- Keep a spreadsheet or CSV with these columns: see [test-cases.csv](03-test-cases.csv) for a ready header.
