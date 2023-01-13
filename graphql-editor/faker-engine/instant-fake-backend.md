---
pageTitle: Instant mock backend | GraphQL Playground
metaDesc: All your projects have an out-of-the-box instantly deployed mock backend. Use it as a GraphQL Playground and test your schema using real values.
---

# Instant Mock backend

To use and test a fake backend navigate to GraphQL Cloud via the top menu or (CTRL + K). It should automatically deploy your fake backend or warn you if something is incorrect with your schema.&#x20;

This mock backend is deployed out of the box, however it can also be configured. The following options are configurable:

* Faker JS values
* User-defined values. The mock backend will choose a random value/values - for an array from the defined values

<figure><img src="../../.gitbook/assets/mock backend prod.gif" alt=""><figcaption></figcaption></figure>

### Using Faker backend in your frontend apps

To use faker backend inside frontend apps. Please make requests to&#x20;

`https://faker.graphqleditor.com/YOUR_NAMESPACE/YOUR_PROJECT/graphql`
