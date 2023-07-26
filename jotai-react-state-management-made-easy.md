---
author: src/data/forestry/content/authors/michal.md
first_category: React JS
second_category: TypeScript
third_category: ''
feature_image: "/uploads/default_feat.png"
createdAt: 2022-05-18T18:00:00Z
title: 'Jotai: React state management made easy'
short_description: A look at the benefits of using an atomic React state management
  library like Jotai

---
React state management enjoys a rich ecosystem of libraries with a new one seemingly popping up every few months, if not even more often. While that might seem confusing from the outside, with so many options to choose from, the choice is actually quite simple. It boils down to either sticking with Redux despite its flaws or following the latest trends, looking for that one new library that works just like you want. One of the newest ones is the atomic state management library called Jotai.

## Three approaches to state management

The different types of state management solutions in React can be broken down into three categories. Well there is also a native solution that’s built-in, the React Context API. It lets you pass data through the tree via a `provider` and `consumer` without the need for passing it manually through each level of components. This does have some use cases, particularly if you have something that is rarely changed and just want to make it accessible to another part of your React component tree, without bothering with third party libraries. Though using it for anything more complex than that will leave you with a ton of nested context all over the tree, which isn’t optimal to say the least. So aside from some basic applications you’ll likely need to pick one of these:

* **Flux-based**: Based on Facebook’s Flux architecture, these libraries follow the centralized, global store approach. Data is made accessible to components by subscribing to a single source, the global data store and only updated by triggering actions. Examples include Redux, the oldest and most widely used library (which is bemoaned for lots of boilerplate) or something like Zustand which uses simplified Flux principles.
* **Proxy-store**: This approach wraps a state object in a proxy, so you deal with it and not the object itself and you can subscribe to a part of that state from anywhere in the tree. The proxy pattern does not require a specific action to be fired, like the flux approach does, and will automatically detect what part of the state is used in the component and subscribe to just updates to that part. The best known examples are Valtio and Mobx.
* **Atomic**: Unlike the others where state is stored outside the React tree in a top-down approach, here the state is stored internally inside the tree. Atoms are updatable and subscribable units of state. You can build state by combining them and renders are based on atom dependency. This saves you from unnecessary re-renders of the other approaches and results in a boilerplate-free API where shared state has the same basic functions as Hooks (ie. `useState` and `useAtom`) That makes it really easy to get a hang of for anyone with some experience with Hooks and since they have been with us for a while, I would guess that wouldn't be that rare. The two atomic libraries are Recoil and Jotai.

## Jotai vs Recoil

The atomic approach is fairly new in comparison to the good old Redux, but looks to be here to stay. Little wonder since the benefits it provides over the more tried and tested approaches are really substantial. Now as far as the atomic state management libraries go, the two main ones are Jotai and Recoil. The latter was released in 2020 by Facebook, which shows that even the originator of Flux has realized that a different approach to state management might be better. While Jotai is newer (released in June 2021) and does not have a tech behemoth behind it, it does have a few interesting advantages.

* **it's smaller**: Jotai has a smaller core API, it’s bundle size is just 3.3 kb compared to 14 for Recoil and for the most part it boils down to `provider`, `atom`, and `useAtom`. There are other additional features but this should provide the basic idea of the approach: as lean as possible.
* **it's simpler**: Jotai is less boilerplate as it is less opinionated, it has no string keys or selectors as atoms function as both selectors and basic atoms. While Recoil does have robust documentation, as you can expect from a Facebook backed library, Jotai is much easier to learn and quicker and simpler to write. It's also TypeScript focused, fully compatible with it and comes with Typings pre-installed.
* **handier**: While keeping everything as small and simple as possible Jotai does already have a pretty big chest of official integrations for managing pieces of state with some additional functionalities ([redux](https://jotai.org/docs/integrations/redux), zustand, valtio, xstate, immer, react-query etc.) A number of these were proposed in GitHub issues so even if it doesn't have the one you need yet, you can probably expect a bunch to be added fairly soon.

## Here to stay

While some might prefer to stick with Redux for the sake of continuity or familiarity it's clear that the dynamically growing field of state management libraries for React does offer a lot of interesting and beneficial solutions we can use. In any case atomic state management is a game changer and solves a lot of the issues that have become so painfully familiar over the years. Even if you don't want to jump ship yet, it's good to familiarize yourself with Jotai and Recoil as they’re likely here to stay and will become more popular as more and more people see the advantages they provide. As for choosing between them it does depend on preference and particular use case. Recoil does have some functionalities that Jotai does not have yet (Snapshots for an example) on the other hand Jotai is much smaller and easier to get into. So if you’re accustomed to something like Redux, one small glance at Jotai and how simple and transparent its code is should be pretty enticing and might be enough to bring you over.