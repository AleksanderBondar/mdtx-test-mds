---
pageTitle: React Query | Zeus GraphQL TypeScript generator
metaDesc: Zeus GraphQL TypeScript generator can also generate type-safe versions of React queries like useQuery, useMutation and others by simply adding a flag to the CLI.
link: plugins/react-query
title: React Query
order: 2
category: Plugins
---

# React Query | Zeus GraphQL TypeScript generator

Zeus can generate type-safe versions of React queries `useQuery`, `useMutation` etc. and React hooks as `useTypedQuery`, `useTypedMutation` etc. by simply adding the `--reactQuery` flag to the CLI. All types of `data` responses are then inherited from the Zeus query. 🚀

```bash
$ zeus schema.graphql ./  --reactQuery
```

```tsx
import { useTypedQuery } from './zeus/reactQuery';

const Main = () => {
  const { data } = useTypedQuery({
    // Get autocomplete here:
    drawCard: {
      name: true,
    },
  });
  // data response is now typed
  return <div>{data.drawCard.name}</div>;
};
```
