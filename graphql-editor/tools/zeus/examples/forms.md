---
pageTitle: Zeus forms | GraphQL TypeScript generator
metaDesc: Zeus GraphQL TypeScript generator docs - forms. To use Zeus with forms make sure to use its generated ValueTypes to ensure type-safety when using mutations.
link: forms
title: Forms
order: 1
category: Examples
---

# Zeus forms | GraphQL TypeScript generator

To use Zeus with forms you should make use of its generated ValueTypes. When submitting a form using a mutation It is much easier and type-safe to do it using `ValueTypes`.

Having the following schema:

```graphql
type Mutation {
  createUser(user: CreateUser!): String
}

input CreateUser {
  firstName: String!
  lastName: String!
  age: Int
  username: String!
}
```

You can use `ValueTypes['CreateUser']` as params for submit form function

```typescript
const submitForm = (values: ValueTypes['CreateUser']) => {
  // ..,rest of the code, validation
  return Chain('https://yourschemaurl.com/graphql', {
    headers: {
      Authorization: 'yourtoken',
    },
  })('mutation')({
    createUser: [{ user: values }, true],
  });
};
```
