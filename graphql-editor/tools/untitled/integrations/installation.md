---
pageTitle: Integration installation | GraphQL CLI Docs
metaDesc: GraphQL CLI Docs - Integrations can be installed via GraphQL Editor or by simply using an npm package name and providing a resolver path to node_modules path.
---

# Integration installation | GraphQL CLI

Installation is done via GraphQL Editor or by just using an npm package name and providing a resolver path to the node\_modules path. The other way is to simply install it via GraphQL Editor:

package.json
```json
{
  "dependencies": {
    "gei-crud": "0.0.2"
  }
}
```


stucco.json
```json
{
  "resolvers": {
    "Query.objects": {
      "resolve": {
        "name": "node_modules/gei-crud/lib/Query/objects"
      },
      "data": {
        "model": {
          "value": "Pizza"
        }
      }
    }
  }
}
```

