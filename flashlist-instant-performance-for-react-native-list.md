---
author: src/data/forestry/content/authors/michal.md
first_category: React Native
second_category: TypeScript
third_category: ''
feature_image: "/uploads/default_feat.png"
createdAt: 2022-07-17T22:00:00Z
title: 'FlashList: instant performance for React Native list'
short_description: FlashList by Shopify is a performance focused solution for lists
  in React Native

---
Needing to dynamically render a collection of data is obviously something you encounter regularly in software development. In React Native lists can be a bit of a pain and there's a number of ways you can handle them. The big break came with version 0.43 and the arrival of SecondList and more importantly FlatList components, which basically replaced ListView as the go-to solution and FlatList has since been the basic way of handling lists in React Native as you can find out by checking out any tutorial on the subject. That said, React Native 0.43 came out a while ago, April 2017 to be exact, and it's about time for something new to come along and offer us some new ideas, namely FlashList by Shopify.

## ListView->FlatList->FlashList?

While the old way of rendering lists was using ListView with the arrival of FlatList we got a lot of improvements in terms of performance and developer experience. The API was very straightforward so those familiar with ListView could transition easily. You also didn't need to format the data anymore and could just pass it to an array and get to rendering straight away. The basic functionalities boil down to three props: `data`, `renderItem` and `keyExtractor`. The first one is unsurprisingly an array of data used to make the list, the second is (also unsurprisingly) a function responsible for rendering a component for an individual item in the data and the third one is to extract a unique key for a given item. With that handled you’re ready to go, but FlatList also had a number of optional props in case you needed more.

## Instant performance

FlashList isn't shy about what it aims to be, the tagline says it all ‘Swap from FlatList in seconds'. We get the same approach we saw with the introduction of FlatList, a focus on making the swap as easy as possible and offering additional props for configuration to make it worthwhile.  That swap is made easy by using FlatLists API, all it requires is changing the name of the component. The big selling point isn't that though and that's the big change from previous solutions. For FlashList the key improvement is in the performance boost you get with it.

It doesn't just use the same props as FlatList it also maximizes performance by doing rendering under the hood and even offers additional props to optimize it even further depending on what your project needs. The focus on performance should do wonders for users on older devices where any improvements in that regard have far more of an impact, particularly those on older Android devices where slower load times are especially noticeable.  Here are the key features:

* **swap easy**: as simple as just changing the name of the component
* **instant performance**: five times more FPS in UI Thread and ten times more FPS in JS Thread
* **memory efficient scaling**: FlashList doesn't recreate items during scrolling which makes it more efficient especially for long heavy lists with various use cases.
* **additional configuration**: While FlashLight does have FlaLine props, it's not limited to that and has a number of extra props you can configure to make it even faster

The use cases for Flashlight are pretty obvious and if you’ve worked with bigger lists on React Native all those points about performance should sound pretty enticing. If not get your old Android phone out and check out how it does with them (spoiler: poorly) The transition to it is a non-issue and it even gives you additional props to work with. If you’re planning on using it for work though I would wait a little bit, so that they can iron out all the kinks for various use cases (you can check out the issues on GitHub to keep an eye out on some of those) Still the main selling point is performance and that should be more than enough to lure people in and when it works without issues it is clearly superior to FlatList and would be a worthy successor, to put it bluntly.