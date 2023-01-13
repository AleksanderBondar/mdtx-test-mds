---
pageTitle: Variables | Zeus GraphQL TypeScript generator
metaDesc: In Zeus GraphQL TypeScript generator performing queries with GraphQL variables is as simple as using the useZeusVariables function and also ensures type safety
link: graphql/variables
title: 
order: 2
category: GraphQL
---

# Variables | Zeus GraphQL TypeScript generator

It's simple to perform queries with variables by using the `useZeusVariables` function. It also forces you to be type-safe.

```typescript
import { Gql, $ } from './zeus';

const addCardResult = await Gql('mutation')(
  {
    addCard: [
      {
        card: $('card'),
      },
      {
        id: true,
        description: true,
        name: true,
        Attack: true,
        skills: true,
        Children: true,
        Defense: true,
        cardImage: {
          bucket: true,
          region: true,
          key: true,
        },
      },
    ],
  },
  {
    variables: {
      Attack: 2,
      Defense: 3,
      description: 'Lord of the mountains',
      name: 'Golrog',
    },
  },
);
```

## TypedDocumentNode + Apollo Client useMutation examples

The following example demonstrates usage with Apollo. Other clients should work similarly.

```tsx
import { typedGql } from './zeus/typedDocumentNode';
import { $ } from './zeus';
import { useMutation } from '@apollo/client';

const myMutation = typedGql('mutation')({
  cardById: [{ cardId: $('cardId', 'String!') }, { name: true }],
});

const Main = () => {
  const [mutate] = useMutation(myMutation);
  // data response is typed
  return (
    <div
      onClick={() => {
        // this are typesafe vars
        mutate({
          variables: {
            cardId: 'du1hn298u1eh',
          },
        });
      }}
    >
      Click
    </div>
  );
};
```
