---
pageTitle: Use as a library | Zeus GraphQL TypeScript generator
metaDesc: The Zeus GraphQL TypeScript generator also supports use as a library letting you generate TypeScript and JavaScript from GraphQL definition.
link: library
title: Use as a library
order: 5
category: Basics
---

# Use as a library | Zeus GraphQL TypeScript generator

### Generate Code

This will be rarely used, but here you are! Generate Typescript and Javascript from GraphQL definitions

```typescript
import { TreeToTS } from 'graphql-zeus';
import { Parser } from 'graphql-js-tree';

const schemaFileContents = `
type Query{
    hello: String!
}
schema{
    query: Query
}
`;

const typeScriptDefinition = TreeToTS.resolveTree(Parser.parse(schemaFileContents));
```

### Dynamically Fetch Schema

This is useful when you need your schema fetched from your GraphQL endpoint in-code

```typescript
import { Utils } from 'graphql-zeus';

Utils.getFromUrl('https://faker.graphqleditor.com/a-team/olympus/graphql').then((schemaContent) => {
  // Use schema content here
});
```
