# Duplicate forms with identical submit — dev spec
Site: nomadinternet.com · Priority 6 · Medium · Effort: Low (0.5-2 days)

## Problem
Duplicate forms with identical CONTINUE submit buttons on multiple pages create a redundant or confusing step in the funnel.

## Evidence (from the live site)
> (see report)

## Current state
cta: CONTINUE; notes: Two forms with the same CONTINUE submit button on multiple pages.

## Required change
cta: Single form visible at a time or differentiated submit labels; notes: Ensure only one form is visible at a time in the primary path, or differentiate the submit labels to clarify which form the user is interacting with.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Ensure only one form is visible at a time in the primary path, or differentiate the submit labels to clarify which form the user is interacting with.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_duplicate_forms_with_identical_submit` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
