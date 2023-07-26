---
author: src/data/forestry/content/authors/michal.md
first_category: Web
second_category: Mobile
third_category: Backend
feature_image: "/uploads/ts.png"
createdAt: 2022-05-17T22:00:00.000+00:00
title: 'TypeScript: the solution for web, mobile and backend development'
short_description: A look at the advantages of using TypeScript for developing different
  types of apps

---
JavaScript has been around for a long while and has become somewhat of a controversial topic in the dev community, some love it, some hate it. Many of those highly critical of JavaScript are probably referring to its pre-2015 state as the language and its entire ecosystem is in a completely different and much better place now. Still, whether you’re a fan of JavaScript or not, it's good to have an idea about alternatives and new variations just in case they offer some key improvements. One of those is TypeScript, a superset of JavaScript which adds static typing.

The main gripe with JavaScript is that the early versions had a lot of traps for programmers and sadly, unlike say Python, those relics can not be discarded with a new version by ignoring backward compatibility and starting with a clean slate. That’s because of the fact that each browser, or rather the company behind it, is a vendor and as such JavaScript has to support everything. Now with all the different mobile platforms this has only compounded the issue. So any change that would do away with some old relic in the language would have to not only be done at the same time and with accordance with all the vendors, it would also probably cause a ton of issues for half the internet still basing some of their code on those old relics. This means that while not everyone might like JavaScript we’re probably stuck with it for the foreseeable future.

## Why TypeScript?  
  
Various improvements to JavaScript made it faster and that led to the appearance of Node.js, a backend implementation. This in turn showed that when working on larger and more complex things, code maintenance keeps becoming a bigger and bigger issue. JavaScript being a dynamically typed language is quick to write and that is a big advantage that jumps out at anyone starting to work on a project. TypeScript being a strongly typed language requires a bit more effort, but makes it easier to read and understand code. This is an even bigger advantage, but one far more that’s noticeable down the road, either with maintenance or especially when it comes to inheriting code. The biggest advantage is that static typing means errors are detected at compilation and not on runtime. This saves a lot of time and effort, usually spent during testing and makes the platform do a bit of work for the programmers, by catching errors for them. As such while JavaScript is perfect for small things like a simple web page with barely any logic behind it, TypeScript is simply way better for anything bigger or more complex.

## For web, mobile and backend

Additionally as TypeScript is a superset of JavaScript all JavaScript code is valid TypeScript code, which means anything written in JavaScript that outgrows it, can be easily transferred to TypeScript. While these might seem like simple quality of life advantages for a developer, they’re actually vital when it comes to working in teams. Whether a team is inheriting some old JavaScript code, changing the scope of a project or getting reassigned to a different branch of it, Typescript will be a real help to make that process much easier and smoother (and most importantly actually possible!). To make that more apparent we can look at how Typescript is used for web, mobile and backend development:

* **web**: React is a tried and tested solution for JavaScript and so TypeScript as well. React Hooks with static typing and type transformations makes for a powerful combination that really streamlines the code. Alternatively you can use Next.js, a framework built on top of React and Node.js which comes with type definitions and has a bunch of features like simplified routing and image optimization to make things faster and easier.

* **mobile**: React Native provides you with a great out of the box solution for hybrid app development. Additionally the main gripe with it, the lack of built-in testing functions, is solved by TypeScript catching errors on compilation. Alternatively you can opt for native development for each platform where using TypeScript will still be a big help especially if you want one team work on implementations for both iOS and Android.

* **backend**: The most popular backend use case for Typescript is serverless functions, in which case Node.js really shines, as it is designed to run on a single thread and can run well even in those environments, when computing resources are limited. Similarly in case of microservices its event driven architecture makes it perfect for Nets.js a TypeScript based framework often called the 'Angular of backend'. GraphQL is also greatly useful here as it uses its type system to describe data fields, preventing over and under-fetching, which makes it a natural fit with TypeScript.

## Versatility, efficiency and interchangeability

Obviously there a numerous other libraries and frameworks available, but this should provide some insight into how versatile the language is. It also makes everything interchangeable: a mobile developer can fill in for a web developer and vice versa without much issue.  Work and communication between developers is also much easier than when working with dynamically typed languages, where everyone comes up with individual solutions others have to be brought into. Perhaps most importantly one team can handle everything instead of needing separate teams for mobile, web and backend.

* **versatile**: almost all libraries are now written in TypeScript which makes integration much easier

* **interchangeable**: interdisciplinary developers which can help or even replace each other when needed

* **cost efficient**: one team can handle every aspect of the project. with no need for separate teams for web and mobile development the costs are significantly lower

## Teamwork
  
TypeScript obviously isn't universally loved and you can easily find those who do not like it for a number of reasons, they might find it too restrictive, think static typing is bothersome and unnecessary or they just might like loose typing. Others might find it too close to JavaScript which is disliked by a lot of developers, to put it mildly. However TypeScript does have clear advantages especially when dealing with big or complex projects and to be honest, personal preference should take a back seat to better teamwork in those cases anyway.