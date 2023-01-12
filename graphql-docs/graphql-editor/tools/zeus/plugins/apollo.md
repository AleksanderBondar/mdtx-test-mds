---
link: plugins/apollo
title: Apollo
order: 1
category: Plugins
---

# Apollo

From Zeus version 5.1.3 onwards Apollo should be used with graphql-typed-document-node

```
npm i @graphql-codegen/typed-document-node
```

## Generate Type-Safe Zeus Schema And Apollo Client Type-Safe Hooks

```
$ zeus schema.graphql ./  --typedDocumentNode
# apollo.ts file with typed hooks is now in the output destination
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
