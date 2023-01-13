---
pageTitle: JavaScript | Zeus GraphQL TypeScript generator
metaDesc: To use Zeus GraphQL TypeScript generator with JavaScript as an autocomplete tool install TS, run the CLI, and transform the result to JS using the tsc command.
link: javascript
title: Javascript
order: 6
category: Basics
---

# JavaScript | Zeus GraphQL TypeScript generator

To use with JavaScript as an autocomplete tool you need to install TypeScript, run the Zeus CLI, and then transform the result to JS using `tsc`

```
$ npm i -D typescript
# OR
# yarn add -D typescript
```

Generate Zeus:

```
$ zeus schema.graphql ./
```

And transform it using Typescript:

```
$ npx tsc ./zeus/*.ts --declaration --target es5 --skipLibCheck
# OR
# yarn tsc ./zeus/*.ts --declaration --target es5 --skipLibCheck
```

This will generate an `out.d.ts` file so that you can have autocompletion.
