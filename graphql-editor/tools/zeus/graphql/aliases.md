---
pageTitle: Aliases | Zeus GraphQL TypeScript generator
metaDesc: The Zeus GraphQL TypeScript generator also supports declaring aliases in queries, which lets you access properties in a fully type-safe way.
link: graphql/aliases
title: Aliases
order: 3
category: GraphQL
---

# Aliases | Zeus GraphQL TypeScript generator

Zeus supports declaring aliases

```graphql
const aliasedQueryExecute = await chain('query')({
  listCards: {
    __alias: {
      atak: {
        attack: [
          { cardID: ['1'] },
          {
            name: true,
            description: true,
          },
        ],
      },
    },
  },
});
```

Response:

```json
{
  "listCards": [
    {
      "atak": [
        {
          "name": "Zelma",
          "description": "Central"
        }
      ]
    }
  ]
}
```

Now you can access properties type-safe like this:

```javascript
aliasedQueryExecute.listCards.map((c) => c.atak);
```
