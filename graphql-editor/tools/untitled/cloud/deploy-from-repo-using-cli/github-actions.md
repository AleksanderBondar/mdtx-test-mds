---
pageTitle: GitHub Actions | GraphQL CLI Docs
metaDesc: GraphQL CLI Docs - Read this simple tutorial to learn how to do a setup for GitHub Actions with GraphQL Editor's shared worker deployment.
---

# GitHub Actions | GraphQL CLI Docs

{% hint style="info" %}
To get GRAPHQL\__EDITOR_TOKEN variable run the_ [_token_](/docs/tools/untitled/cloud/deploy-from-repo-using-cli/github-actions/) _command_
{% endhint %}

```yaml
on:
  push:
    branches:
      - main
jobs:
  build:
    runs-on: ubuntu-latest
    environment: development
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with:
          node-version: '14.x'
          registry-url: 'https://registry.npmjs.org'
      - run: npm install
      - run: >
          npx gecli deploy 
            -e SECRET_VALUE=$SECRET_VALUE 
            -e GRAPHQL_EDITOR_TOKEN=$GRAPHQL_EDITOR_TOKEN
        env:
          SECRET_VALUE: ${{secrets.SECRET_VALUE}}
          GRAPHQL_EDITOR_TOKEN: ${{secrets.GRAPHQL_EDITOR_TOKEN}}
```
