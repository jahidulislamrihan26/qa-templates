# Test Plan: <release or feature>

Version <1.0>, <date>. Read together with the [test strategy](01-test-strategy.md).

## 1. Items under test
<Application, build or version, environment address. If there is no version number, name the date of execution.>

## 2. Features to be tested
| Feature | Requirement | Test cases |
|---|---|---|
| <Login> | REQ-01 | TC-001 to TC-014 |
| <Cart> | REQ-05 | TC-030 to TC-037 |
| <Checkout> | REQ-06 | TC-038 to TC-047 |

## 3. Test data
| User / data | Purpose |
|---|---|
| <standard user> | Baseline, expected-correct behaviour |
| <locked user> | Must be refused |
| Boundary data | <empty, whitespace, very long text, negative numbers, special characters> |

## 4. Schedule and effort
State clearly whether these are estimates or hours actually logged.

| Activity | Estimated effort |
|---|---|
| Analysis and requirement derivation | |
| Test case design | |
| Execution | |
| Exploratory sessions | |
| Defect reporting | |
| Reporting | |

## 5. Roles
| Role | Responsibility |
|---|---|
| Test lead | Strategy, plan, release recommendation |
| Tester | Design, execution, defect reporting |
| Developer | Triage and fix defects |
| Product owner | Confirm intended behaviour |

## 6. Open questions for the product owner
List behaviour that is unclear. Each one is either a defect or a requirement gap, and the answer changes a test result.
1. <Should X happen or Y?>

## 7. Suspension and resumption
Testing stops when <environment down, login broken for the main test user>. It resumes when <condition>.

## 8. Risks
| Risk | Effect | Mitigation |
|---|---|---|
| <test environment unstable> | <delays> | <smoke test before each run> |

## 9. Sign-off
| Role | Name | Date |
|---|---|---|
| Test lead | | |
| Product owner | | |
