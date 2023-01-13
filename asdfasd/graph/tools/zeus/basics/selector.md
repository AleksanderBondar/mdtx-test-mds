---
pageTitle: Selectors | Zeus GraphQL TypeScript generator
metaDesc: In the Zeus GraphQL TypeScript generator you can create type-safe Zeus selection sets useful for reusing across multiple GraphQL queries.
link: selector
title: Selector
order: 1
category: Basics
---

# Selectors | Zeus GraphQL TypeScript generator

### Generate Reusable Selection Sets

In TypeScript Zeus can help make type-safe Zeus selection sets to reuse across queries.

```typescript
import { Selector, Chain } from './zeus';

const chain = Chain('https://faker.graphqleditor.com/a-team/olympus/graphql');

const cardSelector = Selector('Card')({
  name: true,
  description: true,
  Attack: true,
  skills: true,
  Defense: true,
  cardImage: {
    key: true,
    bucket: true,
  },
});

const queryWithSelectionSet = await chain('query')({
  drawCard: cardSelector,
});
```

### Inferring the response type

Sometimes you might like to infer the response type. In that case, it is best to use selectors:

```tsx
import { Selector, InputType, GraphQLTypes } from './zeus';

export const drawCardQuery = Selector("Query"){
  drawCard: {
    Attack: true,
    Children: true,
    id: true,
  },
});

type InferredResponseType = InputType<GraphQLTypes['Query'], typeof drawCardQuery>;
```
