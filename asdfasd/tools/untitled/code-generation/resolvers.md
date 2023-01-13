---
pageTitle: Specify resolvers in a repo | GraphQL CLI Docs
metaDesc: GraphQL CLI Docs - Learn how to specify resolvers in a repository by using the CLI to either add them via a command or manually into the schema.
---

# Specify resolvers in a repo | GraphQL CLI

To specify resolvers in a repo use the CLI to add those with a command or manually edit the stucco.json file.

### Adding a resolver

```
npx gecli resolver
```

This above command will interactively ask you about what resolver code you want to create.

### Adding manually

Given that the `schema.graphql` in your repository looks something like this:

schema.graphql
```graphql
type Query{
    hello: String!
}

schema {
    query: Query
}
```

You can specify the resolver as follows. As you see the `name` is the path to a generated or `js` file.

stucco.json
```javascript
{
    "resolvers": {
        "Query.bundle": {
            "resolve": {
                "name": "lib/Query/hello"
            }
        }
    }
}
```


hello.js
```typescript
export const handler = () => "world"
```
