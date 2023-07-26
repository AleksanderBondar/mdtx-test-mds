---
author: src/data/forestry/content/authors/michal.md
first_category: React JS
second_category: Web
third_category: ''
feature_image: "/uploads/default_feat.png"
createdAt: 2022-06-05T22:00:00Z
title: Unstated Next vs Redux, which is better for managing state in React
short_description: A look at why always sticking with Redux might not be the best
  idea

---
State management in React, despite being a key aspect of development and having a ton of useful tools and libraries, is still not solved, or even close to that. Most have stuck with Redux over the years, but the ever growing number of new state management libraries suggests there is a lot of space for improvement. Over the years React has dropped in a lot of help, like the Context API or Hooks. While this was initially seen by some as the end of Redux, that has not materialized to say the least, and Redux remains the most widely used state management tool.

## Everyone uses Redux

Redux has been the much maligned and yet still most widely used state management tool ever since it came out victorious from the so called flux wars, a period when various libraries based on Facebook’s Flux architecture vied for the title of the top state management solution in React. That turned out to be Redux as it overshadowed the other libraries. Over the years however, there have been a lot of complaints about it, mostly relating to boilerplate and performance issues as Redux is not meant to be quick or simple, its purpose is being predictable, i.e. making it easy to see state updates.

In fact a lot of the complaints are a product of its wide adaptation as it has led to overuse. Since Redux focuses on making it easy to read state updates not every app even needs it (or might be better off with a different state management library) On top of that because of the whole ‘single source of truth’ approach a lot of people tend to just stick everything in their app into Redux which isn't the best idea either. Additionally as Redux is the go to solution for state management it means you are somewhat forced to use it and it does have a learning curve and some issues that might not be to everyone's liking, especially those used to Object Oriented Programming.

## How is Unstated Next better?

On the other hand some newer libraries have chosen to make full use of the new tools provided by React. One of them is Unstated Next which was basically built on top of the React Context API. It's a spiritual successor to Unstated and its main focus is keeping everything as simple and small as possible. How? It relies on simply using React and the tools it provides like Hooks and Context to the fullest, while also providing the useful addition of Containers. These are just like components, but only for state. You simply put a piece of state into a Container, other components can subscribe to it and any change to the state in the Container triggers a rerender of the subscribed components. Let’s look at a simple comparison with Redux:

* **smaller and faster**: Unstated-Next pretty much boils down to built-in React functionalities and componentizing everything, which makes it a number of times smaller as well as significantly faster than Redux.
* **way simpler**: There's almost no learning curve, it will take you maybe 5 minutes if you know how to use `useState`, `useContext` and custom Hooks (which lets be real, you do if you’re using React) Additionally the containers also make it easier to get around everything.
* **written in Typescript**: Typescript support out of the box means type-checking and less need for testing
* **built around containers**: This means less boilerplate and simply relying on the Context API under the hood. It also makes integrating with any react library a simple process by doing it one component at a time.

## Overuse is not a good idea

Many saw the addition of Hooks as something that will make Redux obsolete (or maybe were eager for an opportunity to ditch it) The thought was that the `useContext` and `useReducer` hooks would be used for state management instead of using a global state container like Redux. This has not materialized and it remains the go to tool for state management. It even has its own Hooks API now making use of the new things React has provided. While Redux is much maligned for the above mentioned reasons it isn't bad, it's simply overused and relied on too heavily due to being so widely adopted for so long. Instead of complaining about having to use Redux with all its issues we should instead focus on figuring out when we can use alternatives like Unstated Next which will fit our project better. The React state management ecosystem is constantly changing so we don't have to ditch one tool for the other. We can simply keep on relying on Redux when/if needed and try to get on with some newer solutions which can be better in other cases. Additionally although Hooks have not made Redux obsolete some new thing always can, so its good to keep an eye out for that!