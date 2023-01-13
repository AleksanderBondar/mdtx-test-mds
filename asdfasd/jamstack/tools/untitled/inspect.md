---
pageTitle: Inspect resolvers | GraphQL CLI Docs
metaDesc: GraphQL CLI Docs - Find unimplemented resolvers, use one command to inspect the resolvers and find which are not in the stucco file but do exist in the schema.
---

# Inspect resolvers | GraphQL CLI Docs

This command is used to detect resolvers that are not in `stucco.json` file but they do exist in `schema.graphql` file.

```
gecli inspect
```

Result
```
⠋ Checking for non existing non-scalar resolvers
 There is no resolver for "Document.source" inside stucco.json
 There is no resolver for "ExternalSource.clientData" inside stucco.json
✔ Checking for non existing non-scalar resolvers
```