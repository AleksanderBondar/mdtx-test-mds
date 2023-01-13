---
pageTitle: Generate gql | Zeus GraphQL TypeScript generator
metaDesc: Use our Zeus GraphQL TypeScript generator functions to easily generate a gql string with the use of just one simple GraphQL query.
link: graphql/gql
title: Gql string
order: 4
category: GraphQL
---

# Generate gql | Zeus GraphQL TypeScript generator

Use the `Zeus` function to generate a gql string

```typescript
import { Zeus } from './zeus';

const stringGql = Zeus('query', {
  listCards: {
    name: true,
    skills: true,
    Attack: true,
  },
});

// stringGql value:
// query{listCards{name skills Attack}}
```
