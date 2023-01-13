---
pageTitle: StuccoJS Subscriptions | Zeus GraphQL TypeScript generator
metaDesc: Zeus GraphQL TypeScript generator docs. Generating types for the Stucco Subscription library requires only adding a simple flag to the CLI.
link: plugins/stucco
title: Stucco
order: 3
category: Plugins
---

# StuccoJS Subscriptions | Zeus GraphQL TypeScript generator

Zeus can generate types for the Stucco Subscription library by adding the `--stuccoSubscriptions` flag to the CLI. All types in `data` are then inherited from the Zeus query.

```
$ zeus schema.graphql ./  --stuccoSubscriptions
```

```typescript
stuccoSubscriptions(
  (apiFetchResult) => [apiFetchResult.url],
  'https://my.backend/graphql',
)({ drawCard: { Attack: true } }).on((args) => args.drawCard.Attack);
```
