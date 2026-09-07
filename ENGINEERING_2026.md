# 2026 Engineering Evidence

This historical shopping-cart application is retained as product-journey evidence.

## Engineering questions

- How does state move through product discovery and cart interactions?
- What invariants must hold when quantity, price, or inventory changes?
- How are loading, empty, error, and unavailable states represented?
- How would the frontend consume a typed backend contract and emit useful journey telemetry?

Modern portfolio work should extend these product flows with typed contracts, accessibility, automated journey tests, performance evidence, and failure scenarios.

## Reproduce

```bash
npm ci --legacy-peer-deps
npm run build -- --configuration production
npm test -- --watch=false --browsers=ChromeHeadless
```
