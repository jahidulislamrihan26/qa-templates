# Performance Testing Checklist

## Before you start
- [ ] Targets are written down: p95 and p99 response time, error rate, and a per-endpoint target where endpoints differ in cost. A test without a target cannot pass or fail.
- [ ] The traffic mix is realistic (what users actually do), not one URL repeated.
- [ ] You know the test environment and how it differs from production.
- [ ] You do **not** point stress, spike or soak tests at a system you do not own.
- [ ] The load generator has its own resources. If it shares a machine with the system under test, say so and expect unstable capacity numbers.

## Test types and the question each answers
| Test | Question |
|---|---|
| Smoke | Does the script and the system work with one user? |
| Load | Does it meet the targets at expected traffic? |
| Journey | Do real user journeys work, with correct data, at the expected number of concurrent users? |
| Stress | Where does it break, **how** does it fail, and which resource runs out? |
| Spike | Does it survive a sudden surge, and does it recover? |
| Soak | Is it stable for hours: no memory leak, no slow degradation? |

## Method
- [ ] Use an arrival-rate (open) model for load, stress and spike, so slow responses do not reduce the load.
- [ ] Use a user-count (closed) model with think time for journeys.
- [ ] Report percentiles, never only averages.
- [ ] Tag requests by test step, so each load level has its own numbers.
- [ ] Record the system's own CPU, memory and event-loop or queue delay during the test, so you can say **why** it slowed.
- [ ] Correlate data (use ids returned by earlier steps) and check that results are correct under load.
- [ ] After an overload, separate the "backlog draining" period from the "recovered" period.

## Reading results
- [ ] Repeat the stress test several times. If the breaking point moves a lot between runs, report a range and plan with the low end.
- [ ] Check the load generator: dropped iterations or its own CPU at 100% means the numbers are limited by the generator.
- [ ] Write down the environment (hardware, versions) next to the numbers.
- [ ] Give recommendations with evidence (which resource, at which load), not guesses.
