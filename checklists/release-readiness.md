# Release Readiness Checklist

Answer each line with Yes, No or N/A (with a reason). Any "No" on a Critical line blocks the release until a named person accepts the risk in writing.

## Quality (Critical)
- [ ] No open Critical defect in a customer flow.
- [ ] Open Major defects are within the agreed limit and each has a decision (fix, defer, accept).
- [ ] The main purchase / sign-up / payment flow passes end to end in the target browsers.
- [ ] Security basics checked: login cannot be bypassed, protected pages need a session, no sensitive data in errors.
- [ ] Money and data are correct: totals, taxes, stored values.

## Coverage
- [ ] Every requirement has at least one executed test case; no gaps in the traceability matrix.
- [ ] All Critical and High test cases executed; Not Run cases are listed with reasons.
- [ ] Regression suite (automated) is green on the release build.
- [ ] Accessibility: automated scan clean and keyboard-only walk of the main flow done.
- [ ] Performance: load test at expected traffic meets the targets; known capacity limit documented.

## Environment and data
- [ ] Tested on a production-like environment; differences are written down.
- [ ] Test data cleaned up; no test accounts or test orders left in production.
- [ ] Monitoring and alerts are in place for the new release.

## Process
- [ ] Release notes list changes and known issues.
- [ ] Rollback plan exists and was tried.
- [ ] Summary report issued with an explicit recommendation (go, conditional go, no-go).
- [ ] Sign-off by the product owner and the test lead.
