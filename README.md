# QA Templates

[![CI](https://github.com/jahidulislamrihan26/qa-templates/actions/workflows/ci.yml/badge.svg)](https://github.com/jahidulislamrihan26/qa-templates/actions/workflows/ci.yml) Part of the [SQA portfolio](https://github.com/jahidulislamrihan26/sqa-portfolio).

Practical, ready-to-use templates and checklists for software testing: the same document structures used in the portfolio projects, with the project-specific content removed and guidance added. Copy a file, fill it in, and you have a professional-looking test document.

## Templates
| File | Use it to |
|---|---|
| [01 Test strategy](templates/01-test-strategy.md) | Say how and why you test, once per product |
| [02 Test plan](templates/02-test-plan.md) | Plan one release: scope, data, roles, risks, sign-off |
| [03 Test case](templates/03-test-case.md) and [CSV](templates/03-test-cases.csv) | Write cases anyone can run and judge |
| [04 Bug report](templates/04-bug-report.md) | Report a defect so it gets fixed (includes a checklist) |
| [05 Test summary report](templates/05-test-summary-report.md) | Give a decision-maker the answer in one page |
| [06 Exploratory charter](templates/06-exploratory-charter.md) | Run a timeboxed exploratory session, with idea prompts |
| [07 Traceability matrix](templates/07-requirements-traceability-matrix.csv) | Show every requirement is covered |
| [08 Risk assessment](templates/08-risk-assessment.md) | Decide what to test first |

## Checklists
| File | Covers |
|---|---|
| [Accessibility](checklists/accessibility.md) | WCAG 2.1 AA basics, with keyboard and screen-reader sections an automated scan cannot replace |
| [API testing](checklists/api-testing.md) | Contract, validation, authentication, security, robustness, data hygiene |
| [Web security basics](checklists/web-security-basics.md) | Sessions, access control, input, headers, errors: a tester-level first look |
| [Performance testing](checklists/performance-testing.md) | Test types, method, how to read results carefully |
| [Release readiness](checklists/release-readiness.md) | A go / no-go list |

## Worked examples
Real, filled-in documents from the portfolio projects:
- [A bug report](examples/bug-report-example.md) (a Critical login bypass), with notes on why it is a good report.
- [An exploratory charter](examples/exploratory-charter-example.md) with session notes.

## See them used
The templates came from real projects:
- [manual-testing-saucedemo](https://github.com/jahidulislamrihan26/manual-testing-saucedemo): strategy, plan, 87 test cases, traceability, charters, 20 defect reports and a summary report.
- [api-testing-newman-openapi](https://github.com/jahidulislamrihan26/api-testing-newman-openapi): API test plan, coverage report and defect reports.
- [k6-performance-testing](https://github.com/jahidulislamrihan26/k6-performance-testing): performance test plan and summary report.
- [playwright-ui-automation-pom](https://github.com/jahidulislamrihan26/playwright-ui-automation-pom): UI automation linked to the manual cases.

## Principles behind the templates
1. **Write for the reader who will read nothing else.** Every report starts with the decision.
2. **Evidence over opinion.** Steps, screenshots, numbers.
3. **State what was not tested.** A gap you name is useful; a gap you hide is a surprise later.
4. **Priority comes from risk.** Impact times likelihood, not whatever is easiest to test.

## Use and licence
Free to use and adapt under the [MIT licence](LICENSE).

## Related projects
Worked projects that use these documents:
- [manual-testing-saucedemo](https://github.com/jahidulislamrihan26/manual-testing-saucedemo): test strategy, plan, 87 cases and 20 defect reports on a web shop.
- [api-testing-newman-openapi](https://github.com/jahidulislamrihan26/api-testing-newman-openapi): API test suite built on an OpenAPI spec, proven by mutation testing.
- [k6-performance-testing](https://github.com/jahidulislamrihan26/k6-performance-testing): load, stress and soak testing with SQL data checks.
- [playwright-ui-automation-pom](https://github.com/jahidulislamrihan26/playwright-ui-automation-pom), [cypress-e2e-saucedemo](https://github.com/jahidulislamrihan26/cypress-e2e-saucedemo) and [selenium-pytest-saucedemo](https://github.com/jahidulislamrihan26/selenium-pytest-saucedemo): UI automation of the same site in three tools.
- [sqa-portfolio](https://github.com/jahidulislamrihan26/sqa-portfolio): the hub that links everything.
