# Vague guarantee signal — dev spec
Site: nomadinternet.com · Priority 10 · Medium · Effort: Low (0.5-2 days)

## Problem
A confidence-related heading exists but offers no explicit terms, making the promise unconvincing at the point of purchase.

## Evidence (from the live site)
> A section heading reads “SHOP WITH CONFIDENCE”.

## Current state
notes: Confidence-related heading exists but no explicit terms.

## Required change
notes: Expand the confidence section to state a concrete guarantee, such as a money-back or satisfaction policy, with clear terms visible near the checkout CTA.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Expand the confidence section to state a concrete guarantee, such as a money-back or satisfaction policy, with clear terms visible near the checkout CTA.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_guarantee_signal` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
