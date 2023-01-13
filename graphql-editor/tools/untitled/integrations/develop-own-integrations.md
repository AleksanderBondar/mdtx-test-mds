---
pageTitle: Develop your integrations | GraphQL CLI Docs
metaDesc: GraphQL CLI Docs - Develop your integrations, integrate them with the projects Stucco, publish them to GraphQL Editor for use in its No-code editor.
---

# Develop your integrations | GraphQL CLI

**Development**

To develop a GraphQL Editor Integration use the `gecli create backend` command to create your project. Then initialize the integration.

**Data format**

integration.ts
```typescript
type IntegrationData = {
  name: string;
  description: string;
  value: string | string[];
  required?: boolean;
};

type IntegrationSpecification = {
  [resolver: string]: {
    name: string;
    description: string;
    data: Record<string, IntegrationData>;
    resolve: { name: string };
  };
};
const integration: IntegrationSpecification = {
  'Query.objects': {
    name: 'List objects',
    description: 'List objects stored in database',
    data: {
      model: {
        name: 'Database model',
        description: 'Specify model name',
        value: 'Object',
        required: true,
      },
      sourceFilterParameters,
    },
    resolve: {
      name: 'lib/Query/objects',
    },
  },
};
```

Later on use the `gecli gei integrate` command to integrate your TypeScript file to the `stucco.json`

**Init**

Init files needed to create the integration from your backend project to be used in GraphQL Editor No-Code editor or as npm package.

**Integrate**

Integrate your files with the project's `stucco.json`

**Publish**

Publish your integration to GraphQL Editor for use in the GraphQL Editor No-Code editor.

**Unpublish**

Unpublish your integration from GraphQL Editor.
