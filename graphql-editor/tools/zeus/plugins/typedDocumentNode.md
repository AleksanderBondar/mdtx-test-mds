---
pageTitle: Typed Document Node | Zeus GraphQL TypeScript generator
metaDesc: Zeus GraphQL TypeScript generator docs. Use a simple flag to generate builders for Typed Document Node, a type-safe query for popular GraphQL clients.
link: plugins/typedDocumentNode
title: TypedDocumentNode
order: 4
category: Plugins
---

# Typed Document Node | Zeus GraphQL TypeScript generator

```
npm i @graphql-codegen/typed-document-node
```

Zeus can generate builders for [`TypedDocumentNode`](https://www.graphql-code-generator.com/plugins/typed-document-node), a type-safe query representation understood by most GraphQL clients (including Apollo, URQL etc) by adding the `--typedDocumentNode` or `--td` flag to the CLI.

## Generate Type-Safe Zeus Schema And TypedDocumentNode query builders

```
$ zeus https://yourschema.com/graphql ./  --typedDocumentNode
# typedDocumentNode.ts file with typed document node builders is now in the output destination
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
