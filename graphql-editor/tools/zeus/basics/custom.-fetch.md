---
pageTitle: Custom fetch | Zeus GraphQL TypeScript generator
metaDesc: With the Zeus GraphQL TypeScript generator you can use Thunder to have total control of the fetch function without any risk of losing the result type.
link: custom-fetch
title: Custom fetch
order: 7
category: Basics
---

# Custom fetch | Zeus GraphQL TypeScript generator

Zeus `Thunder` gives total control of the fetch function and you won't lose the result type. ⚡️

```typescript
import { Thunder } from './zeus';

// Create thunder fetch client with endpoint, options and response handlers
const thunder = Thunder(async (query) => {
  const response = await fetch('https://faker.graphqleditor.com/a-team/olympus/graphql', {
    body: JSON.stringify({ query }),
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
    },
  });

  if (!response.ok) {
    return new Promise((resolve, reject) => {
      response
        .text()
        .then((text) => {
          try {
            reject(JSON.parse(text));
          } catch (err) {
            reject(text);
          }
        })
        .catch(reject);
    });
  }

  const json = await response.json();

  return json.data;
});

// Call thunder client with type-safe arguments, fields and get type-safe result type
const listCardsAndDraw = await thunder('query')({
  cardById: [
    {
      cardId: 'sdsd',
    },
    {
      description: true,
    },
  ],
  listCards: {
    name: true,
    skills: true,
    attack: [
      { cardID: ['s', 'sd'] },
      {
        name: true,
      },
    ],
  },
  drawCard: {
    name: true,
    skills: true,
    Attack: true,
  },
});
```
