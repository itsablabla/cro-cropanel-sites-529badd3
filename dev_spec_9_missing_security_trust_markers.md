# Missing security trust markers — dev spec
Site: nomadinternet.com · Priority 9 · High · Effort: Medium (2-5 days)

## Problem
No visible security badges, encryption mentions, or trust seals appear where users enter address and payment details, increasing submission anxiety.

## Evidence (from the live site)
> (see report)

## Current state
notes: No visible security badges, encryption mentions, or trust seals in the digest where users enter address and payment details.

## Required change
notes: Add recognizable security badges and a short privacy reassurance line directly beside the coverage-check form to reduce submission anxiety.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add recognizable security badges and a short privacy reassurance line directly beside the coverage-check form to reduce submission anxiety.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_security_trust_markers` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
