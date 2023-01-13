---
pageTitle: Examples | Stucco GraphQL server
metaDesc: Stucco GraphQL server basics - a simple hello world GraphQL schema example with one string field resolver. Copy-paste the code and test it yourself.
---

# Examples | Stucco GraphQL server

This example shows a simple GraphQL schema with one string field resolver:

## schema.graphql
```graphql
type Query{
    hello: String
}
schema{
    query: Query
}
```
## stucco.json
```json
{
    "resolvers":{
        "Query.hello":{
            "resolve":{
                "name": "lib/hello"
            }
        }
    }
}
```
## hello.js
```typescript
export function handler(input){
    return "Hello world"
}
```


When the following query is executed:

<pre class="language-graphql" data-title="GraphQL query"><code class="lang-graphql"><strong>{
</strong>    hello
}</code></pre>

It should yield this response:

```json
{
    "hello": "Hello world"
}
```

