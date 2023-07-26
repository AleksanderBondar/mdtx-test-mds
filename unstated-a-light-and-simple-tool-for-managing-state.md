---
author: src/data/forestry/content/authors/michal.md
first_category: React JS
second_category: Frontend
third_category: Web
feature_image: "/uploads/unstated-1.png"
createdAt: 2022-04-18T22:00:00.000+00:00
title: 'Unstated: a light & simple state management library for React'
short_description: A look at how Unstated-next can help us with React state management

---
State management is a bit of a boogeyman when it comes to React, if you ask those who don't want to get into it, that will probably be the reason they’ll give you. State management does become quite a bit of work as your app grows and you often need libraries to help with that. That’s what turns a lot of people off as most devs experienced with React have their top 5 state management libraries if not a top 10. Either that or they simply stuck with Redux and never bothered looking for some other option.

Redux is the most popular library for state management, but far from the only one and some of them are based on one another like Rematch is on Redux, which makes it hard to wonder why it all serves as a major turn off for people who are looking to get into React. The whole thing seems complicated with a lot of learning required to find the right solution and even then you might still have to deal with a lot of boilerplate or need to jump on some other more advanced library built on the one you were using. This creates the often seen view that state management in React is bothersome as you either have to stick with the most commonly used tool (which is widely criticized in the community) or need to engage in a never ending cycle of looking for the newest library with all the additional features and functions. If that sounds like a hassle, fortunately there is one much simpler library that might just be what you’re looking for.

![Unstated logo](/uploads/unstated_logo.png "Unstated")

## Unstated

In React state basically lives on components and that makes it predictable, transparent and easy to work with or test. Even if you’re not familiar with React, a brief look at those components will usually give you a pretty good idea of what they're supposed to do. Continuing with this approach everything, including state, is shared through Context, you pass some state into a Provider component and a Consumer component will receive it. This makes for a simple and efficient solution as it doesnt need to pass through the entire tree and ends up exactly where you want it. While this is great, what if you want to share state across multiple components? Well this is where Unstated comes in, it's all about combining Component State and Context while keeping things simple. It's a really small library comprised of three things:

* **Containers**: these are a class which is basically like components but used only for state. You simply paste a piece of your state into a Container and components can subscribe to the state in it.
* **Subscribers**: components which are used to deliver the state to the components that need it. Any change in the state in the container automatically triggers a re-render of the subscriber components.
* **Providers**: components which hold all of the instances of your containers and allow its children to subscribe to them. They are used at the top level around components that you want to subscribe to a container.

## Unstated-next

As you can see Unstated was a great tool and helped share logic and state in a quick and simple way, something that was sorely missing in React. That said, React later introduced Hooks which basically filled the niche Unstated was in and to be brutally honest kinda made it redundant. The creator of Unstated Jamie Kyle realised that, but also saw another niche for a library and that’s how he came up with the idea for Unstated-next. The niche was that a lot of devs didn't see how to use Hooks to share state and logic so the goal was a spiritual successor to Unstated which would help understand shared state and logic in React by using the same base concept.

* **keep it simple**: Unstated-next just wants you to use React Hooks and Context to their fullest using the same container system Unstated did
* **keep it small**: at around 200 bytes and needing only a few minutes to get a hang on the library is really miniature
* **componentize everything**: having everything in components does wonders for performance and especially testing, integrating with any other React library will also be smooth since you can do it one component at a time

## it's all about React

The key thing about Unstated is that it encourages you to simply use React and just throws in a clever solution like Containers for you to use when needed. When used correctly with Hooks and Context, which are powerful tools by themselves, it will make state management much easier without the need for learning to use some more complicated state management libraries or dealing with lots of boilerplate code. While there are obviously cases where you might need a more complex tool and the minimalistic approach of Unstated-next simply wont be enough it is definitely the way to go if you’re just starting with React or if you just want to keep state management a simple and easy affair.