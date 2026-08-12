# Generic value proposition — dev spec
Site: nomadinternet.com · Priority 2 · High · Effort: Low (0.5-2 days)

## Problem
The homepage headline claims reliability and nationwide coverage but does not explain what the product is or why it is better than alternatives.

## Evidence (from the live site)
> Reliable Internet That Works Anywhere in the U.S.
> Internet That Just Works

## Current state
h1: Reliable Internet That Works Anywhere in the U.S.; notes: Headline is generic and does not specify product type or unique benefits.

## Required change
h1: Unlimited Wireless Internet for RVs, Rural Homes & Travelers; notes: Rewrite hero headline and subcopy to explicitly state that Nomad sells unlimited-data wireless internet for RVs, rural homes, and travelers, and lead with a concrete benefit such as no contracts or no hard data caps.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Rewrite hero headline and subcopy to explicitly state that Nomad sells unlimited-data wireless internet for RVs, rural homes, and travelers, and lead with a concrete benefit such as no contracts or no hard data caps.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_generic_value_proposition` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
