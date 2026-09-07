# Shopping Cart — Frontend Product Engineering Case

> Historical Angular shopping experience preserved as a product-journey case study for state, UX correctness, testing and incremental modernization.

## 30-second read

A shopping cart looks simple until state becomes distributed across components, routes, persistence and user actions. This repository is used to reason about **correct user journeys, state transitions and regression safety**.

**Primary question:** can we change the frontend without breaking the journeys users already depend on?

## Core journey

```text
Browse product
     ↓
Add / remove item
     ↓
Cart state
     ↓
Quantity / price updates
     ↓
Checkout transition
     ↓
Validation + error handling
```

## What this demonstrates

- Angular component architecture
- reactive/state-driven UI
- shopping/cart user journeys
- validation and error states
- browser testing
- regression thinking around existing behaviour

The historical implementation uses Angular CLI 11.2.2. The goal is to modernize evidence and engineering practice without rewriting history.

## Run it online

**[Open in GitHub Codespaces](https://codespaces.new/MountainBridge/shopping-cart)** — recommended full-project runtime.

**[Open in StackBlitz](https://stackblitz.com/github/MountainBridge/shopping-cart)** — browser playground for the Angular application; Codespaces is the fallback for historical dependency/runtime issues.

## Run locally

```bash
npm install --legacy-peer-deps
npm start
```

Then open `http://localhost:4200/`.

## Regression scenarios

| Journey | What to verify |
|---|---|
| add item | cart state and totals update correctly |
| remove item | state, count and totals remain consistent |
| change quantity | validation prevents impossible values |
| refresh | persisted state behaves as designed |
| empty cart | empty state is intentional, not an error |
| invalid action | user receives recoverable feedback |
| rapid changes | no stale/overwritten state |

## Interview prompts

1. Where is the source of truth for cart state?
2. How would you test price/quantity invariants?
3. Which user journeys belong in e2e tests?
4. What is the blast radius of changing the state model?
5. How would you instrument a checkout failure?
