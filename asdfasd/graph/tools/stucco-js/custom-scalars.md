---
pageTitle: Custom scalars | Stucco GraphQL server
metaDesc: Stucco GraphQL server has a built-in resolver function for custom scalars. By default, it will process scalars used in your schema to ensure type safety.
---

# Custom scalars | Stucco GraphQL server

Scalars used in your schema can be returned after being processed by a custom resolver function first. This is optional and by default, they are returned without a type check.

```json
{
    "scalars":{
        "CUSTOM_SCALAR_NAME":{
            "parse":{
                "name": "PATH_TO_RESOLVER"
            },
            "serialize":{
                "name": "PATH_TO_RESOLVER"
            }
        }
    }
}
```
