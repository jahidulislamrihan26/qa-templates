# Test Strategy: <product name>

| | |
|---|---|
| Version | 1.0 |
| Date | <date> |
| Product / system under test | <name and address or build> |
| Author | <name> |

> The strategy says HOW the team will test and WHY. It changes rarely. The [test plan](02-test-plan.md) says WHAT, WHEN and WHO for one release.

## 1. Objective
One or two sentences: the question testing must answer for stakeholders. Example: "Is the checkout safe to release, and what are the risks if not?"

## 2. Approach
| Technique | Where it is used |
|---|---|
| Requirements-based testing | Every requirement has at least <n> test cases |
| Equivalence partitioning and boundary values | <forms, filters, limits> |
| Negative testing | <invalid input, missing data, wrong permissions> |
| Exploratory testing | <charters, timeboxes> |
| Risk-based prioritisation | See section 4 |
| Automation | <what is automated and what stays manual, and why> |

## 3. Scope
**In scope:** <features, browsers, devices, data>

**Out of scope:** <what is excluded and who covers it, if anyone>

## 4. Risk-based prioritisation
Priority = impact x likelihood. Test the highest first.

| Risk | Impact | Likelihood | Rating | Test focus (case ids) |
|---|---|---|---|---|
| <customer cannot pay> | Very high | Medium | **Critical** | <TC-0xx to TC-0yy> |
| <wrong totals> | Very high | Low | **High** | |
| <layout glitch> | Low | Medium | Low | |

## 5. Entry and exit criteria
- **Entry:** <environment ready, build deployed, test data available, smoke test passes>
- **Exit:** <all Critical and High cases run, every failure logged with evidence, summary report issued>
- **Release rule:** <for example: no open Critical defect and at most N open Major defects>

## 6. Defect management
- **Severity** (technical impact): Critical (core flow impossible, data or money wrong, security hole), Major (feature broken, workaround exists), Minor (cosmetic or low impact).
- **Priority** (business urgency): High, Medium, Low.
- Every defect has steps, expected result, actual result and evidence ([bug report template](04-bug-report.md)).
- Origin is recorded when it matters (for example: found in production, found in test, known issue).

## 7. Test environment and data
| Item | Value |
|---|---|
| Browsers and versions | |
| Devices and screen sizes | |
| Test accounts | |
| Test data and how it is reset | |

## 8. Deliverables
<Test plan, test cases, traceability matrix, defect reports, summary report, automation code.>

## 9. Assumptions, constraints and limitations
- <anything not available: browsers, devices, assistive technology, production-like data>
- <be explicit about what will NOT be verified, so nobody assumes it was>
