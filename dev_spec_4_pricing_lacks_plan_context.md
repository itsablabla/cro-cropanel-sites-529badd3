# Pricing lacks plan context — dev spec
Site: nomadinternet.com · Priority 4 · High · Effort: Low (0.5-2 days)

## Problem
Prices appear as bare dollar figures without plan names, features, or differentiators, so visitors cannot judge which option fits them or why it is worth the cost.

## Evidence (from the live site)
> $99.95 /month
> $129.95 /month
> $0.00 (one-time)
> $99.99 (one-time)

## Current state
notes: Prices appear as bare dollar figures without plan names, features, or differentiators.

## Required change
notes: Pair each price with a plan name, headline feature, and a one-line benefit (e.g., 'Best for full-time RVers — truly unlimited data') so the offer is self-explanatory above the fold.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Pair each price with a plan name, headline feature, and a one-line benefit (e.g., 'Best for full-time RVers — truly unlimited data') so the offer is self-explanatory above the fold.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_pricing_lacks_plan_context` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
